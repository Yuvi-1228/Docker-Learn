# Docker Volume 
## To check existing volume 
```
docker volume ls
```
# Create your own volume 
```
docker volume create <volume-name>

```
# To check volume by default 
```
docker inspect <volume-name>
```

# To bind docker volume with mysql container 
```
docker run -d <Image-Name> --network <Network-Name> -v <Volume-Name>:<contain-sql-path /var/lib/mysql> -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=devops mysql
```

# Another way to create and persist volume 
- First create a folder name Volume the create another folder under the volume foler name mysql 
- under mysql you can store data here 
- Now you have to change just little bit command like just paste your host volume path instead of volume name 
```
docker run -d <Image-Name> --network <Network-Name> -v <Path your host volume path>:<contain-sql-path /var/lib/mysql> -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=devops mysql
```
