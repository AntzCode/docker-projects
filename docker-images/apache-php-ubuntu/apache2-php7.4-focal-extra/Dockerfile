FROM antzcode/apache-php-ubuntu:apache2-php7.4-focal

MAINTAINER AntzCode Ltd <www.antzcode.com>

# docker build -t antzcode/apache-php-ubuntu:apache2-php7.4-focal-extra .

# Name
LABEL Name="apache2-php7.4-focal-extra"
LABEL Description="Apache2 + PHP7.4 (Extra) on Ubuntu Focal (20.04)"

# License
LABEL org.opencontainers.image.vendor="AntzCode Ltd"
LABEL org.opencontainers.image.authors="AntzCode Ltd <www.antzcode.com>"
LABEL org.opencontainers.image.licenses="MIT-0"

# Description
LABEL org.opencontainers.image.ref.name="apache2-php7.4-focal-extra"
LABEL org.opencontainers.image.title="Apache2 + PHP7.4 (Extra) on Ubuntu Focal (20.04)"
LABEL org.opencontainers.image.description="Apache2 installed on Ubuntu Focal (20.04) with PHP7.4 and a extra set of PHP extensions: ncdu htop nano \
php7.4-mysql php7.4-pgsql php7.4-curl php7.4-bz2 php7.4-zip php7.4-gd php7.4-json php7.4-xml php7.4-mbstring php-redis php7.4-sqlite3 php-memcached php7.4-intl php7.4-odbc php-xml-svg php-zmq php-tokenizer php-tidy php-fpdf php-imagick php-mail phpunit phpunit-git php-xdebug php7.4-intl php7.4-odbc php-xml-svg php-zmq php-tokenizer php-tidy php-fpdf php-xdebug php7.4-ldap php7.4-phpdbg php7.4-soap php-dompdf php-htmlawed php-text-wiki php-markdown php-cocur-slugify php-stomp php-masterminds-html5 php-solr php-seclib"
LABEL org.opencontainers.image.created="2021-07-26T04:07:54.00Z"
# date --iso-8601=seconds --utc | sed 's/\+00:00/.00Z/'

# Source
LABEL org.opencontainers.image.url="https://github.com/antzcode/docker-projects/tree/main/docker-images/apache-php-ubuntu/apache2-php7.4-focal-extra/README.md"
LABEL org.opencontainers.image.source="https://github.com/antzcode/docker-projects/tree/main/docker-images/apache-php-ubuntu/apache2-php7.4-focal-extra"
LABEL org.opencontainers.image.version="1.0.0"
LABEL org.opencontainers.image.revision="0"

# BEGIN SETUP

# Let it install without stopping for user input
ARG DEBIAN_FRONTEND=noninteractive

# Update the repository sources list
RUN apt-get update

# Install PHP Extensions

# Extra Installation
RUN apt-get install -y php7.4-ldap
RUN apt-get install -y php7.4-phpdbg
RUN apt-get install -y php7.4-soap
RUN apt-get install -y php-dompdf
RUN apt-get install -y php-htmlawed
RUN apt-get install -y php-text-wiki
RUN apt-get install -y php-markdown
RUN apt-get install -y php-cocur-slugify
RUN apt-get install -y php-stomp
RUN apt-get install -y php-masterminds-html5
RUN apt-get install -y php-solr
RUN apt-get install -y php-seclib

# Run the server
EXPOSE 80
CMD apachectl -D FOREGROUND
