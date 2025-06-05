# Docker Cmpose 
- DC is a configuration file which is make to easy to automatic deploy , create and manage container. It is written by YAML language. 
# Docker Compose file 
```
# Version of docker compose
version: "3.8"

# Create container for database
services: 
    mysql:
        container_name: mysql
        image: mysql  
        environment:
            MYSQL_DATABASE: "devops"
            MYSQL_ROOT_PASSWORD: "root"
        ports:
         - "3306:3306"
        volumes:
            - mysql-data:/var/lib/mysql
        network:
            - two-tier
        restart: always
        healthcheck:
            test: ["CMD", "mysqladmin", "ping", "-h", "localhost", "-uroot", "-proot"]
            interval: 10s
            timeout: 5s 
            retries: 5 
            start_period: 60s

    flask:
        build:
            context: .
        container_name: two-tier-app
        ports:
            - "5000:500"
        environment:
            MYSQL_HOST: mysql
            MYSQL_USER: root
            MYSQL_PASSWORD: root
            MYSQL_DB: devops
        networks:
         - two-tier
        depends_on:
            - mysql
        restart: always
        healthcheck:
            test: ["CMD-SHELL", "curl -f http://localhost:5000/health || exit 1"]
            interval: 10s
            timeout: 5s 
            retries: 5 
            start_period: 60s
volumes:
    mysql-data

networks:
    two-tier

```

# Install Docker Compose v2
```
sudo apt-get install docker-compose-v2
```

# Run Docker Compose 
```
docker compose up 
```

# Run Docker compose in background 
```
docker compose up -d
```

# Stop Container from docker compose 
```
docker compose down 
```


