FROM openjdk:17-ea-jdk-buster

WORKDIR /app
COPY gradle ./gradle
COPY build.gradle ./build.gradle
COPY gradlew ./gradlew
COPY gradlew.bat ./gradlew.bat
COPY settings.gradle ./settings.gradle
RUN ./gradlew --no-daemon init

COPY src ./src
RUN ./gradlew --no-daemon bootJar

CMD ["./gradlew", "--no-daemon", "bootRun"]
