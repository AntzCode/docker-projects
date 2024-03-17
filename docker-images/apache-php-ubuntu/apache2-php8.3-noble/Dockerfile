FROM antzcode/apache-php-ubuntu:apache2-php8.3-noble-lean

MAINTAINER AntzCode Ltd <www.antzcode.com>

# docker build -t antzcode/apache-php-ubuntu:apache2-php8.3-noble .

# Name
LABEL Name="apache2-php8.3-noble"
LABEL Description="Apache2 + PHP8.3 on Ubuntu Noble (24.04)"

# License
LABEL org.opencontainers.image.vendor="AntzCode Ltd"
LABEL org.opencontainers.image.authors="AntzCode Ltd <www.antzcode.com>"
LABEL org.opencontainers.image.licenses="MIT-0"

# Description
LABEL org.opencontainers.image.ref.name="apache2-php8.3-noble"
LABEL org.opencontainers.image.title="Apache2 + PHP8.3 on Ubuntu Noble (24.04)"
LABEL org.opencontainers.image.description="Apache2 installed on Ubuntu Noble (24.04) with PHP8.3 and a standard set of PHP extensions: ncdu htop nano curl php8.3-mysql php8.3-pgsql php8.3-curl php8.3-bz2 php8.3-zip php8.3-gd php8.3-json php8.3-xml php8.3-mbstring php-redis php8.3-sqlite3 php-memcached php8.3-intl php8.3-odbc php-xml-svg php-zmq php-tokenizer php-tidy php-fpdf php-imagick php-mail phpunit phpunit-git php-xdebug composer"
LABEL org.opencontainers.image.created="2021-07-26T04:07:54.00Z"
# date --iso-8601=seconds --utc | sed 's/\+00:00/.00Z/'

# Source
LABEL org.opencontainers.image.url="https://github.com/antzcode/docker-projects/tree/main/docker-images/apache-php-ubuntu/apache2-php8.3-noble/README.md"
LABEL org.opencontainers.image.source="https://github.com/antzcode/docker-projects/tree/main/docker-images/apache-php-ubuntu/apache2-php8.3-noble"
LABEL org.opencontainers.image.version="1.0.0"
LABEL org.opencontainers.image.revision="0"

# BEGIN SETUP

# Let it install without stopping for user input
ARG DEBIAN_FRONTEND=noninteractive

# Update the repository sources list
RUN apt-get update

# Include server admin tools
RUN apt-get install -y ncdu
RUN apt-get install -y htop
RUN apt-get install -y nano
RUN apt-get install -y curl

# Install PHP Extensions

# Standard Installation

RUN apt-get install -y git
RUN apt-get install -y php-redis
RUN apt-get install -y php8.3-sqlite3
RUN apt-get install -y php-memcached
RUN apt-get install -y php8.3-intl
RUN apt-get install -y php8.3-odbc
RUN apt-get install -y php-xml-svg
RUN apt-get install -y php-zmq
RUN apt-get install -y php-tokenizer
RUN apt-get install -y php-tidy
RUN apt-get install -y php-fpdf
RUN apt-get install -y php-imagick
RUN apt-get install -y php-mail
RUN apt-get install -y phpunit
RUN apt-get install -y php-xdebug

# Install certbot for SSL certificates
RUN apt-get install -y certbot python3-certbot-apache

# Install composer
RUN curl -sS https://getcomposer.org/installer -o composer-setup.php
RUN php composer-setup.php --install-dir=/usr/local/bin --filename=composer


# Run the server
EXPOSE 80
CMD apachectl -D FOREGROUND
