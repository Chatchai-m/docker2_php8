ARG PHP_VERSION=""
# FROM php:${PHP_VERSION:+${PHP_VERSION}-}fpm-alpine
FROM php:${PHP_VERSION}-fpm

#install PHP && lib
RUN apt update; \ 
    apt -y upgrade; \
    pecl install trader; \
    docker-php-ext-enable trader; \
    apt install -y libzip-dev zip nano tree; \
    apt install -y libfreetype6-dev libjpeg62-turbo-dev libpng-dev \
	&& docker-php-ext-configure gd --with-freetype --with-jpeg \
	&& docker-php-ext-install -j$(nproc) gd

#install Pyrhon && lib
RUN apt install -y python3 python3-pip; \
    pip3 install mysql-connector-python;\ 
    pip3 install pymysql; \
    pip3 install contourpy; \
    pip3 install cycler; \
    pip3 install fonttools; \
    pip3 install greenlet; \
    pip3 install imageio; \
    pip3 install joblib; \
    pip3 install kiwisolver; \
    pip3 install matplotlib; \
    pip3 install pandas; \
    pip3 install pyparsing; \
    pip3 install scikit-learn; \
    pip3 install seaborn; \
    pip3 install SQLAlchemy; \
    pip3 install xgboost;


RUN docker-php-ext-install mysqli pdo pdo_mysql zip
#  bz2 bcmath sockets gd gettext gmp intl ldap pgsql shmop soap 
# For test