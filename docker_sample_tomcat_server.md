update the server
```
apt update -y
```
install docker
```
sudo apt install docker.io
```
check the docker version
```
docker --version
```
start , enable and check status of docker
```
sudo systemctl start docker
sudo systemctl enable docker
sudo systemctl status docker
```

create the docker file for tomcat server

$ sudo vim Dockerfile
```
FROM centos:latest
RUN yum install java -y
RUN mkdir /opt/tomcat
WORKDIR /opt/tomcat
ADD https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.56/bin/apache-tomcat-9.0.56.tar.gz .
RUN tar -xvzf apache-tomcat-9.0.56.tar.gz
RUN mv apache-tomcat-9.0.56/* /opt/tomcat
EXPOSE 8080
COPY ./sample.war /opt/tomcat/webapps
CMD ["/opt/tomcat/bin/catalina.sh", "run"]
:wq! save and exit
```

download the sample.war file from 
```
wget https://tomcat.apache.org/tomcat-7.0-doc/appdev/sample/sample.war
```
and put in the same docker file location

creating the image
```
docker build -t mytomcat .
docker images
```

creating the container with name demo-tomcat
```
docker run -d --name demo-tomcat -p 8082:8080 mytomcat
```
check with running containers
```
docker ps -a
```
access the tomcat sample application
```
http://server_ip:8082/sample
```
to validate, stop the container running the app
```
docker stop container_ID
```
check with  
```
http://server_ip:8082/sample
```
it will not run

again start the container
```
docker start container_ID
```
```
http://server_ip:8082/sample
```
it works now
:)




