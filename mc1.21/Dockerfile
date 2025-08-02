FROM alpine:latest

RUN apk add curl
RUN apk add git
RUN apk add openjdk21

RUN mkdir build-tools
WORKDIR /build-tools
RUN curl https://hub.spigotmc.org/jenkins/job/BuildTools/lastSuccessfulBuild/artifact/target/BuildTools.jar > BuildTools.jar
RUN java -jar BuildTools.jar --rev 1.21.8

WORKDIR /
RUN mkdir dummy-project

WORKDIR /dummy-project
COPY gradle gradle
COPY gradlew gradlew
COPY mc1.21/build.gradle build.gradle
COPY mc1.21/src src
RUN /dummy-project/gradlew build --no-daemon

