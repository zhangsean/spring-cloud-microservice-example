FROM java:8-alpine
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","/app.jar"]
EXPOSE 9006
ADD movies-ui-0.1.0.jar app.jar
