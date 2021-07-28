# Apache 2.4.41 + PHP 7.4.3 on Ubuntu Focal (20.04)

Apache2 installed on Ubuntu Focal (20.04) with PHP7.4 and a extra set of PHP extensions: ncdu htop nano php7.4 php7.4-cli libapache2-mod-php7.4
php7.4-mysql php7.4-pgsql php7.4-curl php7.4-bz2 php7.4-zip php7.4-gd php7.4-json php7.4-xml php7.4-mbstring 
php-redis php7.4-sqlite3 php-memcached php7.4-intl php7.4-odbc php-xml-svg php-zmq php-tokenizer php-tidy 
php-fpdf php-imagick php-mail phpunit phpunit-git php-xdebug php7.4-intl php7.4-odbc php-xml-svg php-zmq 
php-tokenizer php-tidy php-fpdf php-xdebug php7.4-ldap php7.4-phpdbg php7.4-soap php-dompdf php-htmlawed 
php-text-wiki php-markdown php-cocur-slugify php-stomp php-masterminds-html5 php-solr php-seclib

## To build:

```
docker build -t antzcode/apache-php-ubuntu:apache2-php7.4-focal-extra .
```

## To run:
* Note: web root on the host is at ./www in this example
```
docker run -d -p 80:80 -v `pwd`/www:/var/www/html antzcode/apache-php-ubuntu:apache2-php7.4-focal-extra
```
