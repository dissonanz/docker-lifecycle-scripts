FROM docker-dev.art.local/ubuntu:latest

MAINTAINER Mark Galpin markg@jfrog.com

RUN /bin/bash -c cd ~; cd /home ; mkdir exec
ADD jdk/jdk-8-linux-x64.tar.gz /home/exec
RUN /bin/bash -c cd /home/exec; mv /home/exec/jdk1* /home/exec/jdk8
ENV JAVA_HOME=/home/exec/jdk8
ADD tomcat/apache-tomcat-8.tar.gz /home/exec
RUN /bin/bash -c cd /home/exec; mv /home/exec/apache-tomcat-8.0* /home/exec/tomcat
ADD tomcat/server.xml /home/exec/tomcat/conf
ENV CATALINA_HOME=/home/exec/tomcat

CMD /bin/bash -c cd /home/exec; /home/exec/tomcat/bin/catalina.sh run
