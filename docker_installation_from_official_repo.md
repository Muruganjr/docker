:red_square: __Installing Docker from Official Repository__

update server
```
# sudo apt update
```
Downloading Dependencies
```
# sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
```
Adding Docker’s GPG Key
```
# curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
Installing the Docker Repository
```
# sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```
Installing the Latest Docker

update the server 
```
# sudo apt update
```
install docker-ce package
```
# sudo apt-get install docker-ce
```
check the docker version
```
# docker --version
```
start , enable and check the status of docker service
```
# sudo systemctl start docker
# sudo systemctl enable docker
# sudo systemctl status docker
```
:smile: it works
