FROM ubuntu:focal

MAINTAINER AntzCode Ltd <www.antzcode.com>

# docker build -t antzcode/apache-php-ubuntu:apache2-php7.4-focal-lean .

# Name
LABEL Name="apache2-php7.4-focal-lean"
LABEL Description="Apache2 + PHP7.4 (Lean) on Ubuntu Focal (20.04)"

# License
LABEL org.opencontainers.image.vendor="AntzCode Ltd"
LABEL org.opencontainers.image.authors="AntzCode Ltd <www.antzcode.com>"
LABEL org.opencontainers.image.licenses="MIT-0"

# Description
LABEL org.opencontainers.image.ref.name="apache2-php7.4-focal-lean"
LABEL org.opencontainers.image.title="Apache2 + PHP7.4 (Lean) on Ubuntu Focal (20.04)"
LABEL org.opencontainers.image.description="Apache2 installed on Ubuntu Focal (20.04) with PHP7.4 and a lean set of PHP extensions: \
php7.4-mysql php7.4-pgsql php7.4-curl php7.4-bz2 php7.4-zip php7.4-gd php7.4-json php7.4-xml php7.4-mbstring"
LABEL org.opencontainers.image.created="2021-07-26T04:07:54.00Z"
# date --iso-8601=seconds --utc | sed 's/\+00:00/.00Z/'

# Source
LABEL org.opencontainers.image.url="https://github.com/antzcode/docker-projects/tree/main/docker-images/apache-php-ubuntu/apache2-php7.4-focal-lean/README.md"
LABEL org.opencontainers.image.source="https://github.com/antzcode/docker-projects/tree/main/docker-images/apache-php-ubuntu/apache2-php7.4-focal-lean"
LABEL org.opencontainers.image.version="1.0.0"
LABEL org.opencontainers.image.revision="0"

# BEGIN SETUP

# Let it install without stopping for user input
ARG DEBIAN_FRONTEND=noninteractive

# Update the repository sources list
RUN apt-get update

# Install and run apache
RUN apt-get install -y apache2 && apt-get clean

# Enable Apache mod_rewrite
RUN a2enmod rewrite

# Install PHP 7.4

RUN apt-get install -y php7.4 php7.4-cli libapache2-mod-php7.4 

# Lean Installation PHP Extensions
RUN apt-get install -y php7.4-mysql 
RUN apt-get install -y php7.4-pgsql
RUN apt-get install -y php7.4-curl
RUN apt-get install -y php7.4-bz2
RUN apt-get install -y php7.4-zip
RUN apt-get install -y php7.4-gd
RUN apt-get install -y php7.4-json
RUN apt-get install -y php7.4-xml
RUN apt-get install -y php7.4-mbstring


# Run the server
EXPOSE 80
CMD apachectl -D FOREGROUND
