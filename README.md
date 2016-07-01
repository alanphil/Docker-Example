## Basic Docker Setup

This project captures the basic configuration files to use Docker and Docker Compose to build a Ruby on Rails project that uses either PostgreSQL or MySQL as the database. 

The master branch is the PostgreSQL version, and mysql branch shows the configuration supporting MySQL. The Docker Compose (docker-compose.yml) configuration creates a container for the Ruby on Rails application and a separate container for the database.

Initial Conditions: Local Linux environment with Docker installed, and Docker Compose also installed.

During initial setup create a local Ruby on Rails application. In that project directory add the Dockerfile, the docker-compose.yml file, and .dockerignore file.

The docker-compose build command creates the image(s) required:

```docker-compose build```

The docker-compose up command will bring up all of the containers defined in the docker-compose YAML file:

```docker-compose up```

Initially had to run the following two commands to setup the database:

```
docker-compose run app rake db:create
docker-compose run app rake db:migrate
```

NOTE: Discovered why the online tutorials all seem to use PostgreSQL instead of MySQL for the database. PostgreSQL is really easy to initially configure with Docker. The trick to easily using MySQL with Docker Compose is to make sure the following line is in the docker-compose YAML file:

```MYSQL_ALLOW_EMPTY_PASSWORD: 'yes'```

If you don't allow an empty password with MySQL on the initial configuration there appears to be a way to set environment variables that will define the root user and password for MySQL. I tried a few ideas but kept getting a failure on the initial database setup with MySQL. Should not be a show stopper for initial development environment.








