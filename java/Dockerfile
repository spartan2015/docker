#
# Oracle Java 8 Dockerfile
#
# https://github.com/dockerfile/java
# https://github.com/dockerfile/java/tree/master/oracle-java8
#

# Pull base image.
FROM vertigomedia/ubuntu-jdk8

RUN apt-get update && \
    apt-get install -y --no-install-recommends apt-utils; \
    apt-get install -y byobu curl git htop man unzip vim wget && \
    apt-get install -y git python python-dev python-pip maven libldap2-dev libsasl2-dev libssl-dev libffi-dev libfontconfig libmysqlclient-dev zip mysql-client subversion && \
    pip install virtualenv awscli ;\
    apt-get install -y wget unzip curl maven git; \
    echo \
    "<settings xmlns='http://maven.apache.org/SETTINGS/1.0.0\' \
    xmlns:xsi='http://www.w3.org/2001/XMLSchema-instance' \
    xsi:schemaLocation='http://maven.apache.org/SETTINGS/1.0.0 https://maven.apache.org/xsd/settings-1.0.0.xsd'> \
        <localRepository>/root/.m2/repository</localRepository> \
        <interactiveMode>true</interactiveMode> \
        <usePluginRegistry>false</usePluginRegistry> \
        <offline>false</offline> \
    </settings>" \
    > /usr/share/maven/conf/settings.xml; \
    mkdir /root/.m2/; \
    echo \
    "<settings xmlns='http://maven.apache.org/SETTINGS/1.0.0\' \
    xmlns:xsi='http://www.w3.org/2001/XMLSchema-instance' \
    xsi:schemaLocation='http://maven.apache.org/SETTINGS/1.0.0 https://maven.apache.org/xsd/settings-1.0.0.xsd'> \
        <localRepository>/root/.m2/repository</localRepository> \
        <interactiveMode>true</interactiveMode> \
        <usePluginRegistry>false</usePluginRegistry> \
        <offline>false</offline> \
    </settings>" \
    > /root/.m2/settings.xml
# run with local maven repo -v /C/Users/eXpert/.m2/:/root/.m2/
# Restore Java 8
#docker build -t imageName:imageTag .
#docker run -d -v /.../.m2/:/opt/.m2/ --name containerName imageName:imageTag


# Define working directory.
WORKDIR /opt/ci-dev

# Define commonly used JAVA_HOME variable
ENV JAVA_HOME /usr/lib/jvm/java-8-oracle

# Define default command.
CMD ["bash"]