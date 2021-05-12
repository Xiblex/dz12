FROM ubuntu:20.04
#Timezone
ENV TZ=Europe/Moscow
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN apt-get update \
  && apt-get install maven git -y
RUN git clone https://github.com/shephertz/App42PaaS-Java-MySQL-Sample /App42PaaS-Java-MySQL-Sample
#  && mvn package -f /boxfuse/pom.xml
#building war file
WORKDIR App42PaaS-Java-MySQL-Sample
RUN mvn clean && mvn install
CMD tail -f /dev/null