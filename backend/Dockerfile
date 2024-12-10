FROM openjdk:17-jdk-alpine 

# Set the working directory inside the container
WORKDIR /app

COPY target/*.jar /app/app.jar

EXPOSE 8080

ENTRYPOINT ["java", "-jar", "/app/app.jar"]
