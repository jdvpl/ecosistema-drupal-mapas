FROM nginx:latest

# Install prerequisite OS packages
RUN apt-get update -y && apt-get upgrade -y && apt-get install -y php php-cli php-xml php-mbstring php-gd \
  php-zip php-curl php-json php-pdo php-opcache zip git curl

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer \
  && php --version; composer --version;

RUN chown -R www-data:www-data $HOME/.composer/

COPY docker/nginx/conf/site.conf /etc/nginx/conf.d/default.conf
COPY docker/nginx/conf/server.conf /etc/nginx/nginx.conf

COPY ./docroot /var/www/app
RUN mkdir -p /var/www/.composer && \
    chown www-data /var/www/.composer


# Install composer dependencies
RUN bash -c "cd /var/www/app && composer install --no-scripts --no-autoloader"

RUN chown www-data:www-data -R /var/www/app

#Create dir's necesary
RUN mkdir -p /var/www/app/sites/default/files/tmp && \
    mkdir -p /var/www/app/sites/default/files/private

RUN chown www-data:www-data -R /var/www/app/sites/default/files && chmod -R 755 /var/www/app/sites/default/files

# Set working directory
WORKDIR /var/www/app