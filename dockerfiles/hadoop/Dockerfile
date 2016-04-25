FROM my/hadoop-base

RUN groupadd hadoop \
    && useradd hduser -g hadoop \
    && mv hadoop* hadoop \
    && mkdir -p /opt/hadoop_tmp/hdfs/datanode \
    && mkdir -p /opt/hadoop_tmp/hdfs/namenode \
    && chown hduser:hadoop -R hadoop*

ENV JAVA_HOME=/usr/lib/jvm/jre-1.7.0-openjdk.x86_64/
ENV HADOOP_HOME=/opt/hadoop
ENV PATH=$PATH:$HADOOP_HOME/bin
ENV PATH=$PATH:$HADOOP_HOME/sbin
ENV HADOOP_MAPRED_HOME=$HADOOP_HOME
ENV HADOOP_COMMON_HOME=$HADOOP_HOME
ENV HADOOP_HDFS_HOME=$HADOOP_HOME
ENV YARN_HOME=$HADOOP_HOME
ENV HADOOP_COMMON_LIB_NATIVE_DIR=$HADOOP_HOME/lib/native
ENV HADOOP_OPTS="-Djava.library.path=$HADOOP_HOME/lib/native"

#USER hduser
RUN ssh-keygen -t rsa -f $HOME/.ssh/id_rsa -q -P ""
RUN cat $HOME/.ssh/id_rsa.pub >> $HOME/.ssh/authorized_keys

#USER root
