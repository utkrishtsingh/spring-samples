FROM openjdk:11-jdk-slim as builder
COPY / /tmp
RUN cd /tmp && ./gradlew clean build

FROM openjdk:11-jre-slim
COPY --from=builder /tmp/build/libs/spring-boot-h2.jar /app.jar
ENTRYPOINT exec java -jar /app.jar
