FROM maven:3.8.5-openjdk-17 as build
COPY ..
RUN maven clean package -DskipTests

FROM openjdk:17.0.1-jdk-slim
COPY --FROM=build /target/contactManager-0.0.1-SNAPSHOT.jar contactManager.jar
EXPOSE 8484
ENTRYPOINT ["java", "-jar", "contactManager.jar"]