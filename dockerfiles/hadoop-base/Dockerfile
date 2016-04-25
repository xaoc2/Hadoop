FROM centos:6.6

RUN yum -y update \
    && yum -y install wget \
    && yum -y install tar \
    && yum -y install openssh-server \
    && yum -y install openssh-clients \
    && yum -y install which

WORKDIR /opt

RUN wget http://apache-mirror.rbc.ru/pub/apache/hadoop/common/hadoop-2.6.0/hadoop-2.6.0.tar.gz \
    && tar -xzf hadoop-2.6.0.tar.gz \
    && rm -rf *tar.gz \
    && yum -y install java-1.7.0-openjdk
