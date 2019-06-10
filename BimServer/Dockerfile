FROM ubuntu:16.04

RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install openjdk-8-jre-headless wget unzip -y

RUN mkdir /var/www
RUN mkdir /var/www/bimserver
RUN useradd -s /sbin/nologin tomcat8
RUN chown -R tomcat8 /var/www/bimserver
RUN mkdir /var/bimserver
RUN mkdir /var/bimserver/home
RUN chown -R tomcat8 /var/bimserver
RUN cd /opt
RUN wget http://apache.uvigo.es/tomcat/tomcat-8/v8.5.41/bin/apache-tomcat-8.5.41.zip -O tomcat8.zip
RUN unzip tomcat8.zip
RUN rm tomcat8.zip
RUN mv apache-tomcat-8.5.41 /opt/tomcat8
RUN chmod +x /opt/tomcat8/bin/*.sh
RUN mkdir /opt/tomcat8/conf/policy.d
RUN echo "grant { permission java.security.AllPermission; };" > /opt/tomcat8/conf/policy.d/default.policy
RUN chown -R tomcat8 /opt/tomcat8
RUN cd /var/www/bimserver
# RUN wget https://github.com/opensourceBIM/BIMserver/releases/download/v1.5.147/bimserverwar-1.5.147.war -O ROOT.war
RUN wget https://github.com/opensourceBIM/BIMserver/releases/download/v1.5.138/bimserverwar-1.5.138.war -O ROOT.war
RUN mv ROOT.war /var/www/bimserver
RUN mkdir /opt/samples
COPY sample.ifc /opt/samples
COPY server.xml /opt/tomcat8/conf
COPY tomcat8 /etc/init.d/

CMD ["/etc/init.d/tomcat8 start"]