FROM openjdk:17

ARG JAR_FILE=profilePBC.jar

COPY ${JAR_FILE} app.jar

ENTRYPOINT ["java","-jar","/app.jar"]