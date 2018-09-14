FROM openjdk:8-jre-alpine
ARG JAR_FILE
COPY ${JAR_FILE} springboot-docker.jar
EXPOSE 8080
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","/springboot-docker.jar"]