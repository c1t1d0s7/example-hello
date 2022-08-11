FROM maven:3-openjdk-8 AS mbuilder
COPY . /usr/src/hello/
WORKDIR /usr/src/hello
RUN mvn package

FROM openjdk:8-jre
COPY --from=mbuilder /usr/src/hello/target/spring-hello-0.0.1.jar /usr/src/
CMD ["java", "-jar", "/usr/src/spring-hello-0.0.1.jar"]
