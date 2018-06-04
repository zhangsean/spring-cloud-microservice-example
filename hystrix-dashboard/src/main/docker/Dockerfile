FROM java:8-alpine
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","/app.jar"]
ADD hystrix-dashboard-0.1.0.jar app.jar
