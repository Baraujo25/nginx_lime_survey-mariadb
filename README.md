# Docker compose for LimeSurvey using Nginx & MariaDB

## Requirements

- [Docker](https://www.docker.com/)
- Port 80 available

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
4. Fill database requirements:
   - IP: _Paste the one in the clipboard_:3306
   - Database name: limesurveydb
   - Database user: limesurveyuser
   - Database password: localhost
5. Default _username_ and _password_ for lime survey:
   - user: admin
   - password: password

### Additional information

If you desire to change database name, username or password feel free to modify the [compose.yaml](https://github.com/Baraujo25/nginx_lime_survey-mariadb/blob/fc2b2118f775c1cc2bf47f31d6fcc6e595614753/compose.yaml#L17-L20)
