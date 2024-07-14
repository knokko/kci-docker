FROM eclipse-temurin:16

RUN apt-get update
RUN apt-get install git --yes

RUN mkdir build-tools
WORKDIR /build-tools
RUN curl https://hub.spigotmc.org/jenkins/job/BuildTools/lastSuccessfulBuild/artifact/target/BuildTools.jar > BuildTools.jar
RUN java -jar BuildTools.jar --rev 1.17.1

WORKDIR /
RUN mkdir dummy-project

WORKDIR /dummy-project
COPY gradle gradle
COPY gradlew gradlew
COPY mc1.17/build.gradle build.gradle
COPY mc1.17/src src
RUN /dummy-project/gradlew build --no-daemon
