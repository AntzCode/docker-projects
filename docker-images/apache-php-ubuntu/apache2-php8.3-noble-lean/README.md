# Apache 2.4.41 + PHP 8.3.3 (Lean) on Ubuntu Noble (24.04)

Apache2 installed on Ubuntu Noble (24.04) with PHP8.3 and a lean set of PHP extensions: php8.3 php8.3-cli libapache2-mod-php8.3
php8.3-mysql php8.3-pgsql php8.3-curl php8.3-bz2 php8.3-zip php8.3-gd php8.3-json php8.3-xml php8.3-mbstring

## To build:

```
docker build -t antzcode/apache-php-ubuntu:apache2-php8.3-noble-lean .
```

## To run:
* Note: web root on the host is at ./www in this example
```
docker run -d -p 80:80 -v `pwd`/www:/var/www/html antzcode/apache-php-ubuntu:apache2-php8.3-noble-lean
```
