# Apache 2.4.41 + PHP 7.4.3 (Lean) on Ubuntu Focal (20.04)

Apache2 installed on Ubuntu Focal (20.04) with PHP7.4 and a lean set of PHP extensions: php7.4 php7.4-cli libapache2-mod-php7.4
php7.4-mysql php7.4-pgsql php7.4-curl php7.4-bz2 php7.4-zip php7.4-gd php7.4-json php7.4-xml php7.4-mbstring

## To build:

```
docker build -t antzcode/apache-php-ubuntu:apache2-php7.4-focal-lean .
```

## To run:
* Note: web root on the host is at ./www in this example
```
docker run -d -p 80:80 -v `pwd`/www:/var/www/html antzcode/apache-php-ubuntu:apache2-php7.4-focal-lean
```
