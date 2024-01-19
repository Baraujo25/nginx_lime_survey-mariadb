# Docker compose for LimeSurvey using Nginx & MariaDB

## Requirements
- Docker
## Build

1. Open terminal in the root folder of the nginx_lime_survey project
2. Run `docker compose up`
3. Run `docker container inspect nginx_lime_survey-mariadb-mariadb-1`
> container name may vary, we want to inspect the mariadb container
4. Look for **IPAddress** inside **Network**
5. Save it in clipboard

## Installation

1. Navigate in the browser to http://localhost
2. Start installation process
3. All LimeSurvey pre-requisites should be met
4. Fill username and password for database
5. IP of database is the one saved into clipboard
6. Enjoy

