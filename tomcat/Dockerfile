FROM lchennup/myfirst:1.0-1

RUN mkdir -p /apps

# Java Installation
RUN cd /apps && wget --no-cookies --no-check-certificate --header \
 "Cookie:oraclelicense=accept-securebackup-cookie"  \ 
 http://download.oracle.com/otn-pub/java/jdk/8u111-b14/jdk-8u111-linux-x64.tar.gz \
 && tar xvf jdk-8u111-linux-x64.tar.gz -C /apps && mv /apps/jdk1.8.0_111 /apps/jdk8

# Tomcat Installation
RUN wget --output-document=/apps/apache-tomcat-8.5.12.tar.gz http://mirror.nexcess.net/apache/tomcat/tomcat-8/v8.5.12/bin/apache-tomcat-8.5.12.tar.gz \
 && tar zxvf /apps/apache-tomcat-8.5.12.tar.gz -C /apps  

ENV JAVA_HOME /apps/jdk8
ENV PATH $PATH:$JAVA_HOME/bin
ENV CATALINA_HOME /apps/apache-tomcat-8.5.12

RUN chmod +x /apps/apache-tomcat-8.5.12/bin/*.sh

WORKDIR /

EXPOSE 8080

CMD /apps/apache-tomcat-8.5.12/bin/catalina.sh start && bash
