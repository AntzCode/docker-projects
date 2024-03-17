FROM antzcode/apache-php-ubuntu:apache2-php8.3-noble

MAINTAINER AntzCode Ltd <www.antzcode.com>

# docker build -t antzcode/apache-php-ubuntu:apache2-php8.3-noble-extra .

# Name
LABEL Name="apache2-php8.3-noble-extra"
LABEL Description="Apache2 + PHP8.3 (Extra) on Ubuntu Noble (24.04)"

# License
LABEL org.opencontainers.image.vendor="AntzCode Ltd"
LABEL org.opencontainers.image.authors="AntzCode Ltd <www.antzcode.com>"
LABEL org.opencontainers.image.licenses="MIT-0"

# Description
LABEL org.opencontainers.image.ref.name="apache2-php8.3-noble-extra"
LABEL org.opencontainers.image.title="Apache2 + PHP8.3 (Extra) on Ubuntu Noble (24.04)"
LABEL org.opencontainers.image.description="Apache2 installed on Ubuntu Noble (24.04) with PHP8.3 and a extra set of PHP extensions: ncdu htop nano \
php8.3-mysql php8.3-pgsql php8.3-curl php8.3-bz2 php8.3-zip php8.3-gd php8.3-json php8.3-xml php8.3-mbstring php-redis php8.3-sqlite3 php-memcached php8.3-intl php8.3-odbc php-xml-svg php-zmq php-tokenizer php-tidy php-fpdf php-imagick php-mail phpunit phpunit-git php-xdebug php8.3-intl php8.3-odbc php-xml-svg php-zmq php-tokenizer php-tidy php-fpdf php-xdebug php8.3-ldap php8.3-phpdbg php8.3-soap php-dompdf php-htmlawed php-text-wiki php-markdown php-cocur-slugify php-stomp php-masterminds-html5 php-solr php-seclib"
LABEL org.opencontainers.image.created="2021-07-26T04:07:54.00Z"
# date --iso-8601=seconds --utc | sed 's/\+00:00/.00Z/'

# Source
LABEL org.opencontainers.image.url="https://github.com/antzcode/docker-projects/tree/main/docker-images/apache-php-ubuntu/apache2-php8.3-noble-extra/README.md"
LABEL org.opencontainers.image.source="https://github.com/antzcode/docker-projects/tree/main/docker-images/apache-php-ubuntu/apache2-php8.3-noble-extra"
LABEL org.opencontainers.image.version="1.0.0"
LABEL org.opencontainers.image.revision="0"

# BEGIN SETUP

# Let it install without stopping for user input
ARG DEBIAN_FRONTEND=noninteractive

# Update the repository sources list
RUN apt-get update

# Install PHP Extensions

# Extra Installation
RUN apt-get install -y php8.3-ldap
RUN apt-get install -y php8.3-phpdbg
RUN apt-get install -y php8.3-soap
# RUN apt-get install -y php-dompdf
RUN apt-get install -y php-htmlawed
RUN apt-get install -y php-text-wiki
# RUN apt-get install -y php-markdown
# RUN apt-get install -y php-cocur-slugify
RUN apt-get install -y php-stomp
RUN apt-get install -y php-masterminds-html5
RUN apt-get install -y php-solr
RUN apt-get install -y php-seclib

WORKDIR /tmp
RUN git clone https://github.com/dompdf/dompdf.git
WORKDIR /tmp/dompdf
RUN composer install

WORKDIR /tmp
RUN git clone https://github.com/michelf/php-markdown.git
WORKDIR /tmp/php-markdown
RUN composer install

WORKDIR /tmp
RUN git clone https://github.com/cocur/slugify.git
WORKDIR /tmp/slugify
RUN composer install

# Run the server
EXPOSE 80
CMD apachectl -D FOREGROUND
