FROM openjdk:17

ARG JAR_FILE=searchPBC.jar

COPY ${JAR_FILE} app.jar

ENTRYPOINT ["java","-jar","/app.jar"]