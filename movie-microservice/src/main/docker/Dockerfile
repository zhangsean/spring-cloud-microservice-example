FROM java:8-alpine
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","/app.jar"]
EXPOSE 9005
ADD movie-microservice-0.1.0.jar app.jar
