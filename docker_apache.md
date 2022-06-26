Docker file for Apache2
```
$ sudo vim Dockerfile
```
```
FROM ubuntu:latest
ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update
RUN apt-get install apache2 -y
RUN apt-get install apache2-utils -y
RUN apt-get clean
EXPOSE 80
CMD ["apache2ctl","-D","FOREGROUND"]
:wq! save and exit
```

build the docker image
```
# docker build -t apache2 .
```
create the container with name myapache to run in port 8086
```
# docker run -d --name myapache -p 8086:80 apache2
```
