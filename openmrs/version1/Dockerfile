FROM maven:3-jdk-8 as mvn
LABEL author='ashik'
LABEL purpose='practice'
RUN git clone https://github.com/openmrs/openmrs-core.git && cd openmrs-core && mvn clean package
 
FROM tomcat:8
LABEL author='ashik'
LABEL purpose='practice'
COPY --from=mvn /openmrs-core/webapp/target/openmrs.war /usr/local/tomcat/webapps/openmrs.war
EXPOSE 8080
CMD ["catalina.sh", "run"]


#docker image build -t ashik1431/openmrs-core:1.0 .
#docker login
#docker push ashik1431/openmrs-core:1.0