# Build Stage
FROM maven:3.6.3-openjdk-17 AS build
WORKDIR /app
COPY . .
RUN mvn clean package 

# Stage 2: Runtime stage
FROM openjdk:17-alpine
WORKDIR /app
COPY --from=build /app/target/employees-details-1.1.jar .
CMD ["java", "-jar", "employees-details-1.1.jar"]
