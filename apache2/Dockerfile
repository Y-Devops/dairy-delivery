FROM elnomade/ubuntu:16.04
ENV REFRESHED_AT 2017-09-01

MAINTAINER Leonardo Luduena <lleo@linux.com>

ADD ./001-docker.conf /etc/apache2/sites-available/

RUN apt-get update && \
    apt-get install apache2 apache2-utils debconf-utils -y --no-install-recommends && \
    rm -rf /var/lib/apt/lists/* && \
    echo "LoadModule rewrite_module /usr/lib/apache2/modules/mod_rewrite.so" > /etc/apache2/mods-available/rewrite.load && \
    a2enmod rewrite && \
    a2dissite 000-default && \
    a2ensite 001-docker

VOLUME ["/var/www/html"]

# Set Apache environment variables (can be changed on docker run with -e)
ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_LOG_DIR /var/log/apache2
ENV APACHE_PID_FILE /var/run/apache2.pid
ENV APACHE_RUN_DIR /var/run/apache2
ENV APACHE_LOCK_DIR /var/lock/apache2
ENV APACHE_SERVERADMIN sysadmin@linux.com
ENV APACHE_SERVERNAME localhost
ENV APACHE_SERVERALIAS docker.localhost
ENV APACHE_DOCUMENTROOT /var/www/html

EXPOSE 80
ADD start.sh /start.sh
RUN chmod 0755 /start.sh
CMD ["bash", "start.sh"]
