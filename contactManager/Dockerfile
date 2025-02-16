FROM maven:3.8.5-openjdk-17 as build
WORKDIR /contactManager
COPY . .
RUN maven clean package -DskipTests

FROM openjdk:17.0.1-jdk-slim
WORKDIR /contactManager
COPY --from=build /contactManager/target/contactManager-0.0.1-SNAPSHOT.jar contactManager.jar
EXPOSE 8484
ENTRYPOINT ["java", "-jar", "contactManager.jar"]