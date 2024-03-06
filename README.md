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
5. Fill database requirements:
	- IP: *Paste the one in the clipboard*:3306
	- Database name: limesurveydb 
	- Database user: limesurveyuser
	- Database passoword: localhost
6. Default *username* and *password* for lime survey:
	- user: admin
	- password: password
7. Enjoy

