

PostgreSQL & PgAdmin & phpPgAdmin powered by compose


the main idea of this project is to set up and deploy PostgreSQLdatabase and its dedicated interface PhpPgAdmin. in addition i have add another container Pgadmin

In order to do so, i used docker and docker-compose,Only the PhpPgAdmin  is  available on the port8888 from the host.




REQUIREMENTS:
In order to follow this project , you must have Docker installed on your computer and  Linux 

TO check whether docker-compose command is working as follows:

$ docker-compose version

Now, create a project directory (let’s say ~/docker/pgdev) as follows:

$ mkdir -p ~/docker/pgdev

Now, navigate to the project directory ~/docker/pgdev as follows:
$ cd ~/docker/pgdev


Now, create a docker-compose.yaml file in the project directory ~/docker/pgdev and type in the following lines in the docker-compose.yaml file.

Now, to start the db and pgadmin services, run the following command:

$ docker-compose up -d

To see how the ports are mapped, run the following command:

$ docker-compose ps

To find the IP address of your Docker host, run the following command:

$ ip

Now, you can easily access phpPgadmin  from your web browser.

Visit http://localhost:8080 from your Docker 
host 

Once you login, you should see the phppadmin dashboard.
you can login and make changes ,add users ..




FOr postgress.
now,you can easily access Padmin 4 from the web browser 
visit http://localhost:5050 from your docker host

Now, to add the PostgreSQL server running as a Docker container, right click on Servers, and then go to Create > Server…
In the General tab, type in your server Name

Now, go to the Connection tab and type in pgsql-server as Host name/address, 5432 as Port, postgres as Maintenance database, admin as Username, secret as Password and check Save password? checkbox. Then, click on Save.

You can also access your PostgreSQL database server from DataGrip IDE or any other SQL IDEs.

In case of DataGrip, click on + from the Databases section and go to Data Source > PostgreSQL.

PostgreSQL driver may not be installed. In that case, click on Download.

The driver should be installed. Now, type in the Docker host IP address 172.22.27.104  (in my case) as the Host, 5432 as the Port, admin as the User, secret as the Password, postgres as the Database and click on Test Connection.

You should see the PostgreSQL database server details if everything works.then click on ok.



Now, to stop the db and pgadmin services, run the following command:

$ docker-compose down

Environments

This Compose file contains the following environment variables:

POSTGRES_USER the default value is postgres
POSTGRES_PASSWORD the default value is ...
PGADMIN_PORT the default value is ...
PGADMIN_DEFAULT_EMAIL the default value is pgadmin4@pgadmin.org
PGADMIN_DEFAULT_PASSWORD the default value is admin


Access to PgAdmin:
URL: http://localhost:5050
Username: pgadmin4@pgadmin.org (as a default)
Password: admin (as a default)

Access to phpPgAdmin:
URL: http://localhost:8080


