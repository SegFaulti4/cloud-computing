FROM openjdk:17-ea-jdk-buster
LABEL authors="navjig"

WORKDIR /app
COPY gradle ./gradle
COPY build.gradle ./build.gradle
COPY gradlew ./gradlew
COPY gradlew.bat ./gradlew.bat
COPY settings.gradle ./settings.gradle
RUN ./gradlew --no-daemon init

COPY src ./src
RUN ./gradlew --no-daemon bootJar
EXPOSE 8080

CMD ["./gradlew", "--no-daemon", "bootRun"]
