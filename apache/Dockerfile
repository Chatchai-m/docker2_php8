ARG APACHE_VERSION=""
# FROM httpd:${APACHE_VERSION:+${APACHE_VERSION}-}alpine
FROM httpd:${APACHE_VERSION}

RUN apt update; \
    apt -y upgrade;

# Copy apache vhost file to proxy php requests to php-fpm container
RUN sed -i '/LoadModule rewrite_module/s/^#//g' /usr/local/apache2/conf/httpd.conf

# COPY custom.apache.conf /usr/local/apache2/conf/custom.apache.conf
RUN echo "Include /usr/local/apache2/conf/custom.apache.conf" >> /usr/local/apache2/conf/httpd.conf