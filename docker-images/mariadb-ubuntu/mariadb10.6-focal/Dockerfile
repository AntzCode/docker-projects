FROM mariadb:10.6.3-focal

MAINTAINER AntzCode Ltd <www.antzcode.com>

# docker build -t antzcode/mariadb-ubuntu:mariadb10.6-focal .

# Name
LABEL Name="mariadb10.6-focal"
LABEL Description="MariaDB 10.6 on Ubuntu Focal (20.04)"

# License
LABEL org.opencontainers.image.vendor="AntzCode Ltd"
LABEL org.opencontainers.image.authors="AntzCode Ltd <www.antzcode.com>"
LABEL org.opencontainers.image.licenses="MIT-0"

# Description
LABEL org.opencontainers.image.ref.name="mariadb10.6-focal"
LABEL org.opencontainers.image.title="MariaDB 10.6 on Ubuntu Focal (20.04)"
LABEL org.opencontainers.image.description="MariaDB 10.6 installed on Ubuntu Focal (20.04) with server tools: htop nano"
LABEL org.opencontainers.image.created="2021-07-26T04:07:54.00Z"
# date --iso-8601=seconds --utc | sed 's/\+00:00/.00Z/'

# Source
LABEL org.opencontainers.image.url="https://github.com/antzcode/docker-projects/tree/main/docker-images/mariadb-ubuntu/mariadb10.6-focal/README.md"
LABEL org.opencontainers.image.source="https://github.com/antzcode/docker-projects/tree/main/docker-images/mariadb-ubuntu/mariadb10.6-focal"
LABEL org.opencontainers.image.version="1.0.0"
LABEL org.opencontainers.image.revision="0"

# BEGIN SETUP

# Update the repository sources list
RUN apt-get update

# Install Server Tools
RUN apt-get install -y htop
RUN apt-get install -y nano

EXPOSE 3306

HEALTHCHECK --start-period=5m \
  CMD mariadb -e 'SELECT @@datadir;' || exit 1

CMD ["mysqld"]
