FROM php:7.4.3-apache

RUN echo "deb http://mirrors.aliyun.com/debian/ buster main non-free contrib\ndeb http://mirrors.aliyun.com/debian-security buster/updates main\ndeb http://mirrors.aliyun.com/debian/ buster-updates main non-free contrib\ndeb http://mirrors.aliyun.com/debian/ buster-backports main non-free contrib \ndeb-src http://mirrors.aliyun.com/debian-security buster/updates main\ndeb-src http://mirrors.aliyun.com/debian/ buster main non-free contrib\ndeb-src http://mirrors.aliyun.com/debian/ buster-updates main non-free contrib\ndeb-src http://mirrors.aliyun.com/debian/ buster-backports main non-free contrib" > /etc/apt/sources.list

RUN apt-get update && apt-get install -y  vim dnsutils net-tools iputils-ping
RUN apt-get install -y libc-client2007e libenchant1c2a libfreetype6 libicu63 libjpeg62-turbo libmcrypt4 libmemcachedutil2 libpng16-16 libpq5 libsybdb5  libtidy-dev libx11-6 libxpm4 libxslt1.1 snmp --no-install-recommends 
RUN apt-get install -y freetds-dev \
        libbz2-dev \
        libc-client-dev \
        libenchant-dev \
        libfreetype6-dev \
        libgmp3-dev \
        libicu-dev \
        libjpeg62-turbo-dev \
        libkrb5-dev \
        libldap2-dev \
        libmcrypt-dev \
        libmemcached-dev \
        libpng-dev \
        libpq-dev \
        libpspell-dev \
        libsasl2-dev \
        libsnmp-dev \
        libssl-dev \
        libtidy-dev \
        libxml2-dev \
        libxpm-dev \
        libxslt1-dev \
        zlib1g-dev		

ADD https://raw.githubusercontent.com/mlocati/docker-php-extension-installer/master/install-php-extensions /usr/local/bin/

RUN chmod uga+x /usr/local/bin/install-php-extensions && sync && \
    install-php-extensions gd iconv bcmath bz2 calendar dba enchant exif ftp gd gettext gmp imap intl ldap mbstring mcrypt mysqli opcache pcntl pdo pdo_dblib pdo_mysql pdo_pgsql pdo_sqlsrv pgsql pspell shmop snmp soap sockets sysvmsg sysvsem sysvshm tidy xmlrpc xsl zip xdebug

RUN a2enmod rewrite
