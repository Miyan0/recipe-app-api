# DOCKER SETUP

## Setup the Python environment image

Create a Dockerfile
Create the requirements.txt file
Create an app folder

run

``` bash
 docker build .
```

If the build fails because of username and password issue, you need to run:

``` bash
 docker login
```

and enter the userid and password from Docker. Note that the userid is NOT
the email but your Docker username. You can find it when loggin in on the
Docker website (top right corner).

## Setup the Docker compose file

This is the configuration file for all the services that make up our project

Create a docker-compose.yml file

and run:

``` bash
 docker-compose build
```

## Create a Django project

Running command with Docker require usage of the following prefix:
`docker-compose run app sh -c` where 'app' is the name of our service in the docker-compose file.

for example, to create a Django project, you run:

``` bash
 docker-compose run app sh -c "django-admin.py startproject app ."
```

## Running the project

``` bash
 docker-compose up"
```

Note that to load the site in the browser you must go to `127.0.0.1:8000` instead of `0.0.0.0:8000`

## Run tests and linter

``` bash
 docker-compose run app sh -c "python manage.py test && flake8"
```

