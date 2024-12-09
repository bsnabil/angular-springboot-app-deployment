# Build Stage
FROM maven:3.8.4-openjdk-17-slim AS build

# Set the working directory in the container
WORKDIR /app

# Copy the pom.xml and download dependencies
COPY backend/pom.xml .

# Copy the source code and package the application
COPY  backend/src /app/src
#RUN mvn clean package -DskipTests

# Run Stage
FROM openjdk:17-jdk-slim

# Set the working directory in the container
WORKDIR /app

# Copy the jar from the build stage
COPY --from=build app/backend/target/*.jar app.jar

# Expose the application port
EXPOSE 8080

# Run the application
ENTRYPOINT ["java", "-jar", "/app/app.jar"]

