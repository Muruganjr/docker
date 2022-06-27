__Installation of portainer in Ubuntu__

Create Docker Volume to store portainer data
```
$ docker volume create portainer_data
```
Install Portainer Server
```
docker run -d -p 8000:8000 -p 9443:9443 --name portainer \
--restart=always \
-v /var/run/docker.sock:/var/run/docker.sock \
-v portainer_data:/data \
portainer/portainer-ce:2.9.3
```
check the running container
```
$ docker ps
```
access portainer
```
https://server_ip:9443
```
default user is admin \
set user password


