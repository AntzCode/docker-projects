# Docker Images

Each image is sorted into directories bearing the name of the image role. Within each directory, a subdirectory is created for each tag that is published.

Thus, the folder structure is /antzcode/docker-projects/*{image role}*/*{image tag}*

For example: 
- apache-php-ubuntu
  - apache2-php7.4-focal
  - apache2-php7.4-focal-lean
  - apache2-php7.4-focal-full

To build an image, navigate to the image tag directory where you should see the *Dockerfile*. Run the following command:

```
docker build -t "{Your Docker Name}/{Image Role}:{Image Tag}" .
```

To start an image you have built, run the following command by using the title you gave when you built the image:

```
docker run -d {Your Docker Name/Image Role:Image Tag}
```

* Note: the use of -d parameter detaches the container from the terminal and prints the Container ID to the console. 
 
In order to access a detached container when it is running, you should run the following command:

```
docker container exec -it {Container ID} bash
```

* Note: a list of running containers can be found with this command:

```
docker container ls
```

To stop a running container, execute this command:

```
docker container stop {Container ID}
```

More information about using containers can be found at the [Docker Docs](https://docs.docker.com/)
