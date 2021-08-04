# Mariadb 10.6.3 on Ubuntu Focal (20.04)

Mariadb 10.6.3 installed on Ubuntu Focal (20.04)

## To build:

```
docker build -t antzcode/mariadb-ubuntu/mariadb10.6-focal .
```

## To run:

```
docker run -d -p 3306:3306 -v `pwd`/data:/var/lib/mysql -d `pwd`/files:/var/lib/mysql-files antzcode/mariadb-ubuntu/mariadb10.6-focal
```
