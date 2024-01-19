FROM nginx:latest

# Install PHP and required extensions
RUN apt-get update && apt-get install -y \
    php-fpm \
    php-mbstring \
    php-zip \
    php-imap \
    php-xml \
    php-gd \
    php-mysql

# Copy your LimeSurvey application files to the web root directory
COPY LimeSurvey-3.x-LTS/ /usr/share/nginx/html

# Expose the web server port
EXPOSE 80

# Volumes for Nginx and PHP configuration files
VOLUME ["/etc/nginx/conf.d", "/etc/php/8.2/fpm/pool.d/"]

RUN chown -R www-data:www-data /usr/share/nginx/html
# Start Nginx and PHP-FPM in the foreground
CMD ["bash", "-c", "nginx -g 'daemon off;' & php-fpm8.2 -F"]
