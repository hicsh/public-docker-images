ARG TAG
FROM releases-docker.jfrog.io/jfrog/artifactory-jcr:${TAG}

# Define the MariaDB JDBC driver version
ARG MARIADB_DRIVER_VERSION=3.5.2
# Download/install mariadb-java-client
RUN curl https://repo1.maven.org/maven2/org/mariadb/jdbc/mariadb-java-client/${MARIADB_DRIVER_VERSION}/mariadb-java-client-${MARIADB_DRIVER_VERSION}.jar -o ${JF_PRODUCT_HOME=/opt/jfrog/artifactory}/app/artifactory/tomcat/lib/mariadb-java-client.jar
# Ensure permissions are set correctly for the new jar file
USER root
RUN cp ${JF_PRODUCT_HOME=/opt/jfrog/artifactory}/app/artifactory/tomcat/lib/mariadb-java-client.jar ${JF_PRODUCT_HOME=/opt/jfrog/artifactory}/app/access/tomcat/lib/mariadb-java-client.jar && \ 
    chmod 644 ${JF_PRODUCT_HOME}/app/artifactory/tomcat/lib/mariadb-java-client.jar && \
    chmod 644 ${JF_PRODUCT_HOME}/app/access/tomcat/lib/mariadb-java-client.jar
USER artifactory

