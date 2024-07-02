
FROM maven:3.9.4-eclipse-temurin-21 AS build
# Set the working directory inside the container
WORKDIR /app

# Copy the pom.xml and download the dependencies
COPY pom.xml .
COPY .mvn/ .mvn
COPY mvnw .

# Download dependencies specified in the pom.xml
RUN ./mvnw dependency:go-offline

# Copy the source code into the container
COPY src ./src

# Package the application, skipping tests for faster builds
RUN ./mvnw clean package -DskipTests

# Stage 2: Run the application
FROM openjdk:21-jdk-slim

# Set the working directory for the runtime
WORKDIR /app

# Copy the JAR file from the build stage to the runtime stage
COPY --from=build /app/target/springboot-backend-0.0.1-SNAPSHOT.jar app.jar

# Expose the application port
EXPOSE 8080

# Define the entry point to run the application
ENTRYPOINT ["java", "-jar", "app.jar"]
