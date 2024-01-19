# nginx_lime_survey-mariadb
Docker compose to setup LimeSurvey with a MariaDB using nginx

## Limesurvey module

There is a directory called lime-survey which contains:

#### Dockerfile

- Docker image based on lastest nginx image
- Whole pre-requisites required for LimeSurvey to run
- Volume defined for nginx and fpm config files
> Allows to modify configuration without having to restart docker instance
- Entrypoint to trigeer nginx and php-fpm deamons 

#### LimeSurvey App

A raw copy of lime survey application is passed through the container in order to be placed `/usr/share/nginx/html` for server to locate it

NOTE: This could be improved by pulling the limesurvey app straight from their git repository


#### Volumes

1. **nginx** 
> folder containing the nginx configuration file 
> there is currently a functional but not yet optimized config file inside of it
2. **php-fpm** 
> folder containing the php-fpm configuration file
> there is currently a functional but not yet optimized config file inside of it


Both config files take the advantage of the nginx user. Otherwise php-fpm can not comunicate to with unix sock listener


### How to build

1. Open the console right inside the lime-survey folder
1. Run `docker build -t lime-survey-image .`

### How to run

1. Run `docker run -p 80:80 -v $(pwd)/nginx:/etc/nginx/conf.d -v $(pwd)/php-fpm:/etc/php/8.2/fpm/pool.d/ -d lime-survey-image`
2. Open http://localhost/
