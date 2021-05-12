FROM ubuntu:20.04
#Timezone
ENV TZ=Europe/Moscow
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN apt-get update \
  && apt-get install maven git wget -y
RUN git clone https://github.com/shephertz/App42PaaS-Java-MySQL-Sample /App42PaaS-Java-MySQL-Sample
#  && mvn package -f /boxfuse/pom.xml
#building war file
WORKDIR /App42PaaS-Java-MySQL-Sample
RUN wget https://raw.githubusercontent.com/Xiblex/dz12/master/buildapp/pom.xml -O ./pom.xml
RUN mvn clean && mvn package
CMD tail -f /dev/null