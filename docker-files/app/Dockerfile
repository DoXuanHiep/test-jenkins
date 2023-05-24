FROM eclipse-temurin:17-jdk-alpine
LABEL "Project"="test"
LABEL "Author"="HIEP"

VOLUME /tmp/webapps
WORKDIR /tmp/webapps

COPY target/*.jar app.jar app.jar
ENTRYPOINT ["java","-jar","/app.jar"]