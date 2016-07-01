== README

This project captures the basic configuration files to use Docker and Docker Compose to build a Ruby on Rails project that uses either PostgreSQL or MySQL as the database. 

The master branch is the PostgreSQL version, and mysql branch shows the configuration supporting MySQL. The Docker Compose (docker-compose.yml) configuration creates a container for the Ruby on Rails application and a separate container for the database.

Initial Conditions: Local Linux environment with Docker installed, and Docker Compose also installed.

During initial setup create a local Ruby on Rails application. In that project directory add the Dockerfile, the docker-compose.yml file, and .dockerignore file.

The docker-compose build command creates the image(s) required:

```docker-compose build```


