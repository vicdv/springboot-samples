# Springboot & docker sample 

This application is hello world example of using [Spring Boot Web 2.0.4.RELEASE](https://github.com/spring-projects/spring-boot) & [dockerfile-maven 1.4.4](https://github.com/spotify/dockerfile-maven)

## Building & running app
Run SpringBoot app
```
mvn spring-boot:run
```
Build jar & Run it
```
mvn package & java -jar target\springboot-docker-0.0.1-SNAPSHOT.jar
```
Log in to docker hub ( login equals docker.image.prefix property in pom). it's necessary only once.
As an alternative .m2/settings.xml can be used for configuration 
```
docker login
```
Build docker image with latest tag
```
mvn dockerfile:build
```
Add project version tag to image 
```
mvn dockerfile:tag@tag-version
```
Push image with the latest tag to docker hub
```
mvn dockerfile:push@latest
```
Push image with a project version tag to docker hub
```
mvn dockerfile:push@version
```
Push image to docker hub
``` 
mvn dockerfile:push ( if docker has an image with 2 tags then the image with project version is chosen )
```
Pull image with the latest tag from docker hub
```
docker pull vdivco/springboot-docker
```
Run image
```
docker run -p 8080:8080 -t vdivco/springboot-docker
```