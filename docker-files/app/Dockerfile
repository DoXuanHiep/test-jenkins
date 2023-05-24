FROM openjdk:17-alpine AS BUILD_IMAGE
RUN apt update && apt install git -y
RUN git clone https://github.com/DoXuanHiep/test-jenkins.git
RUN cd test-jenkins && chmod +x mvnw && ./mvnw install

FROM eclipse-temurin:17-jdk-alpine
LABEL "Project"="test"
LABEL "Author"="HIEP"

VOLUME /tmp/webapps
WORKDIR /tmp/webapps

COPY --from=BUILD_IMAGE test-jenkins/target/*.jar /tmp/webapps/app.jar
ENTRYPOINT ["java","-jar","/tmp/webapps/app.jar"]