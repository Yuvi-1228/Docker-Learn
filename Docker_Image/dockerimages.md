# what is Docker Images?
- 
- DockerFile->Images->Container

# Login Docker 
```
docker login -u <username>
```
# Pull Images from outsource 
```
docker pull hello-world
```

# Check docker images 
```
docker images
```
# create container from Docker images 
```
docker run hello-world
```
# Pull mysql 
```
docker pull mysql
```
# How to run mysql images 
```
docker run -d -e MYSQL_ROOT_PASSWORD=root mysql
```
# How to stop running container
```
docker stop <container_id>
```
# How to delete images 
```
docker rmi <image-id>
```
```
docker rmi -f <image-id> 
```




