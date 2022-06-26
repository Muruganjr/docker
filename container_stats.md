container stats
```
$ docker stats container_name 
```
or
```
$ docker stats container_ID
```
```
$ docker system df
```
```
docker ps --size
```
 information on space usage 
```
docker system df --verbose
```
docker stats
```
docker stats $(docker ps --format={{.Names}}) --no-stream
```
