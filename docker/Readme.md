# Spring Cloud on Docker example

### Start up commands
```shell
mvn clean package
docker images
docker ps
docker run -itd -p 8761:8761 --name discovery kbastani/discovery-microservice && docker logs -f discovery
docker run -itd -p 8888:8888 --link discovery --name configserver kbastani/config-microservice && docker logs -f configserver
docker run -itd --link discovery --link configserver --name user kbastani/users-microservice && docker logs -f user
docker run -itd --link discovery --link configserver --name movie kbastani/movie-microservice && docker logs -f movie
docker run -itd --link discovery --link configserver --name recommendation kbastani/recommendation-microservice && docker logs -f recommendation
docker run -itd --link discovery --link configserver --name moviesui -p 9006:9006 kbastani/movies-ui && docker logs -f moviesui
docker run -itd -p 10000:10000 --link discovery --link configserver --link user --link movie --link recommendation --name gateway kbastani/api-gateway-microservice && docker logs -f gateway
docker run -itd -p 7979:7979 --link discovery --link gateway --name hystrix kbastani/hystrix-dashboard && docker logs -f hystrix
docker ps
```