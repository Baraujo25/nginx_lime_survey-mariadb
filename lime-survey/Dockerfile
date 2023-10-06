FROM nginx

RUN apt update -y && apt upgrade -y

RUN apt install -y apache2 mariadb-server php libapache2-mod-php php-mysql

RUN apt install -y php-xml php-gd php-ldap php-zip php-imap

RUN cd /var/www/html/

RUN apt install -y wget 

RUN apt install -y unzip

# RUN rm /etc/nginx/nginx.conf /etc/nginx/conf.d/default.conf

# COPY ./limesurvey.conf /etc/nginx/nginx.conf
COPY ./nginx.conf /etc/nginx/nginx.conf
COPY ./default.conf /etc/nginx/conf.d/default.conf

COPY ./LimeSurvey-3.x-LTS/* /usr/share/nginx/html

RUN apt-get install -y lsb-release && apt-get install -y software-properties-common && add-apt-repository "deb http://archive.ubuntu.com/ubuntu $(lsb_release -sc) universe"

RUN apt update -y && apt-get upgrade -y

RUN apt-get install -y php-mbstring



