# Docker File 
- Docker file is sets of instruction where we can write scripts for deploy application 
# Process to create dockerfile 
- So, Before Write Dockerfile we have identified which application we are going to install 
```
# Official Java runtime base image
FROM openjdk:17-jdk-alpine

# metadata
LABEL maintainer="your-email@example.com"
LABEL version="1.0"
LABEL description="A simple Java application"

# working directory
WORKDIR /app

# Copy source code into the container
COPY src/Main.java /app/Main.java

# Compile the Java code
RUN javac Main.java

# Run the Java application when the container starts
CMD ["java", "Main"]
```
# Build Image from Docker file 
```
docker build -t <app_name> . 
```
# Create container from images 
```
docker run <image-name>
```
# Run container with Port map 
```
docker run -d -p 80:80 <image-name>
```
# check logs 
```
docker logs <container-id>

```

# See logs real time 
```
docker attach <conatiner-id>
```
# How to executive container 
```
docker exec -it <container-id> bash
```
# How to access database container 
- Run exec command then run following command 
```
mysql -u root -p 
```
# If you want run container continously 
```
docker run -itd <container-id>
```

