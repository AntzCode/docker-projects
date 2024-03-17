FROM ubuntu:noble

MAINTAINER AntzCode Ltd <www.antzcode.com>

# docker build -t antzcode/apache-php-ubuntu:apache2-php8.3-noble-lean .

# Name
LABEL Name="apache2-php8.3-noble-lean"
LABEL Description="Apache2 + PHP8.3 (Lean) on Ubuntu Noble (24.04)"

# License
LABEL org.opencontainers.image.vendor="AntzCode Ltd"
LABEL org.opencontainers.image.authors="AntzCode Ltd <www.antzcode.com>"
LABEL org.opencontainers.image.licenses="MIT-0"

# Description
LABEL org.opencontainers.image.ref.name="apache2-php8.3-noble-lean"
LABEL org.opencontainers.image.title="Apache2 + PHP8.3 (Lean) on Ubuntu Noble (24.04)"
LABEL org.opencontainers.image.description="Apache2 installed on Ubuntu Noble (24.04) with PHP8.3 and a lean set of PHP extensions: \
php8.3-mysql php8.3-pgsql php8.3-curl php8.3-bz2 php8.3-zip php8.3-gd php8.3-json php8.3-xml php8.3-mbstring"
LABEL org.opencontainers.image.created="2021-07-26T04:07:54.00Z"
# date --iso-8601=seconds --utc | sed 's/\+00:00/.00Z/'

# Source
LABEL org.opencontainers.image.url="https://github.com/antzcode/docker-projects/tree/main/docker-images/apache-php-ubuntu/apache2-php8.3-noble-lean/README.md"
LABEL org.opencontainers.image.source="https://github.com/antzcode/docker-projects/tree/main/docker-images/apache-php-ubuntu/apache2-php8.3-noble-lean"
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

# Install PHP 8.3

RUN apt-get install -y php8.3 php8.3-cli libapache2-mod-php8.3

# Lean Installation PHP Extensions
RUN apt-get install -y php8.3-mysql 
RUN apt-get install -y php8.3-pgsql
RUN apt-get install -y php8.3-curl
RUN apt-get install -y php8.3-bz2
RUN apt-get install -y php8.3-zip
RUN apt-get install -y php8.3-gd
RUN apt-get install -y php8.3-xml
RUN apt-get install -y php8.3-mbstring


# Run the server
EXPOSE 80
CMD apachectl -D FOREGROUND
