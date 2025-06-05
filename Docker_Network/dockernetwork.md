# Docker Network 
## There are seven type of docker network 
- Host 
- Default Bridge 
- User define Bridge 
- None
- MACVLAN (Docker swarm )
- IPVLAN
- Overlay 

# Check Network list 
```
docker network ls
```
# Create your own network
```
docker network create <network-name> -d bridge 
```

# Two tier Application project in docker network
- First create image for backend 
```
docker build -t <backend-app-name> . 
```
- Now, run the backend images 
```
docker run -d -p 5000:5000 --network two-tier -e MYSQL_HOST=mysql -e MYSQL_USER=root -e MYSQL_PASSWORD=root -e MYSQL_DB=devops <image-name>:latest
```
# How to create docker netwoek and connect it 
```
docker network create <two-tier> -d bridge
```
# Now connect network between both container 
```
docker run -d --name mysql --network two-tier -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=devops mysql 
```
```
docker run -d -p 5000:5000 --network two-tier -e MYSQL_HOST=mysql -e MYSQL_USER=root -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DB=devops two-tier-backend:latest
```
# now check docker ps and docker logs 
```
docker ps
```
```
docker logs
```
# To get information about container network 
```
docker network inspect <network-name>
```

