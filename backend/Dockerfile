FROM maven:3.8.4-openjdk-17-slim AS build

WORKDIR /app

COPY backend/pom.xml .

COPY  backend/src /app/src

FROM openjdk:17-jdk-slim

WORKDIR /app

RUN ls -lia

COPY --from=build /app/src/target/*.jar app.jar

EXPOSE 8080

ENTRYPOINT ["java", "-jar", "/app/app.jar"]

