FROM openjdk:11 AS BUILD_IMAGE
RUN apt update && apt install maven -y
RUN git clone https://github.com/abhishekm89/vprofile-project.git
# In case you want to mount Project Directory locally.
# ADD ../../vprofile-project (app/Docker-files/vprofile-project)
RUN cd vprofile-project && git checkout docker && mvn clean install


FROM tomcat:9-jre11
LABEL "Project"="vProfile"
LABEL "Author"="abhishekm89"
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=BUILD_IMAGE vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080

# Run the default Tomcat server
CMD ["catalina.sh", "run"] 

