# Spring Boot Docker

An example on how to use Spring Boot and Docker. This example is referenced from https://spring.io/guides/gs/spring-boot-docker/.

## Pre-Requisites

Docker
Docker Toolbox (MacOSX) - https://www.docker.com/docker-toolbox
 > After installation follow the setup procedure http://docs.docker.com/mac/step_one/

Apache Maven 3.x - https://maven.apache.org/
Java JDK 1.8.x - http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html

## Build

I first had to change the tcp port that docker was listening on.

docker -H tcp://localhost:2375

To build the Spring Boot Application you need Apache Maven 3.x

mvn install

This will create a jar file in the target directory

To build the Docker Image with Maven use the docker-maven-plugin and execute the following:

mvn package docker:build

## Run Application using Java

To run the application execute the following on the command line in the root project.

java -jar target/spring-boot-docker-1.0.0.jar

After the application has started goto the following URL

http://localhost:8080

You should see the Hello Docker World message

## Run Application using Docker

On the command line execute the following:

docker run -p 8080:8080 -t westjet/spring-boot-docker
