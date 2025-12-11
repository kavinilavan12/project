FROM maven:3.9.9-eclipse-temurin-21-jammy AS BUILD_IMAGE
RUN  git clone https://github.com/kavinilavan12/project.git
RUN  git checkout kavi && cd power && mvn install

FROM tomcat:10-jdk21
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=BUILD_IMAGE project/power/target.vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war
EXPOSE 8080
CMD [ "catalina.sh" ,"run" ]