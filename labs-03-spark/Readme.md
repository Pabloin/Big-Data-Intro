Sobre Spark

    


    
vi ~/.bashrc

export $HADOOP_HOME=/home/hadoop/hadoop

export HADOOP_CONF_DIR=$HADOOP_HOME/etc/hadoop
export SPARK_HOME=/home/ubuntu/spark
export PATH=$PATH:$SPARK_HOME/bin
export LD_LIBRARY_PATH=$HADOOP_HOME/lib/native:$LD_LIBRARY_PATH


Sigo a :
https://sparkbyexamples.com/spark/spark-setup-on-hadoop-yarn/