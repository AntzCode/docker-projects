# Apache 2.4.41 + PHP 8.3.3 (Extra) on Ubuntu Noble (24.04)

Apache2 installed on Ubuntu Noble (24.04) with PHP8.3 and an extra set of PHP extensions: ncdu htop nano php8.3 php8.3-cli libapache2-mod-php8.3
php8.3-mysql php8.3-pgsql php8.3-curl php8.3-bz2 php8.3-zip php8.3-gd php8.3-json php8.3-xml php8.3-mbstring 
php-redis php8.3-sqlite3 php-memcached php8.3-intl php8.3-odbc php-xml-svg php-zmq php-tokenizer php-tidy 
php-fpdf php-imagick php-mail phpunit phpunit-git php-xdebug php8.3-intl php8.3-odbc php-xml-svg php-zmq 
php-tokenizer php-tidy php-fpdf php-xdebug php8.3-ldap php8.3-phpdbg php8.3-soap php-dompdf php-htmlawed 
php-text-wiki php-markdown php-cocur-slugify php-stomp php-masterminds-html5 php-solr php-seclib

## To build:

```
docker build -t antzcode/apache-php-ubuntu:apache2-php8.3-noble-extra .
```

## To run:
* Note: web root on the host is at ./www in this example
```
docker run -d -p 80:80 -v `pwd`/www:/var/www/html antzcode/apache-php-ubuntu:apache2-php8.3-noble-extra
```
