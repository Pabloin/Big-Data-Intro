# Big-Data-Intro
Introducción a Big Data

## Lab-01-Hadoop
Lab 01 Hadoop


## Lab 00 Hadoop Single Node
https://hadoop.apache.org/docs/r1.2.1/single_node_setup.html

(necesito Java 1.6+)  
Voy con la default

    sudo apt-get update
    sudo apt install default-jdk
    java --version



            ✔ ~/Big-Data-Intro [develop|✔] 
            23:50 $ java --version
            openjdk 11.0.19 2023-04-18
            OpenJDK Runtime Environment (build 11.0.19+7-post-Ubuntu-0ubuntu122.04.1)
            OpenJDK 64-Bit Server VM (build 11.0.19+7-post-Ubuntu-0ubuntu122.04.1, mixed mode, sharing)

            ~/Big-Data-Tools
            $ ls /usr/lib/jvm/ 
                default-java  java-1.11.0-openjdk-amd64  java-11-openjdk-amd64  openjdk-11


    mkdir ~/Big-Data-Tools
       cd ~/Big-Data-Tools

    wget https://dlcdn.apache.org/hadoop/common/current/hadoop-3.3.5.tar.gz
    wget https://dlcdn.apache.org/hadoop/common/current/hadoop-3.3.5.tar.gz.asc
    wget https://downloads.apache.org/hadoop/common/KEYS

    gpg –-import KEYS 
    gpg --verify hadoop-3.3.5.tar.gz.asc hadoop-3.3.5.tar.gz

        gpg: Signature made Wed Mar 15 17:28:06 2023 UTC
        gpg:                using RSA key 38237EE425050285077DB57AD22CF846DBB162A0
        gpg: Good signature from "Steve Loughran (ASF code sign key  - 2018) <stevel@apache.org>" [unknown]
        gpg:                 aka "[jpeg image of size 8070]" [unknown]
        gpg:                 aka "Steve Loughran <stevel@cloudera.com>" [unknown]
        gpg:                 aka "Steve Loughran <steve.loughran@gmail.com>" [unknown]
        gpg:                 aka "Steve Loughran <stevel@hortonworks.com>" [unknown]
        gpg: WARNING: This key is not certified with a trusted signature!
        gpg:          There is no indication that the signature belongs to the owner.
        Primary key fingerprint: 3823 7EE4 2505 0285 077D  B57A D22C F846 DBB1 62A0

    tar- xvf hadoop-3.3.5.tar.gz



        # set to the root of your Java installation
        export JAVA_HOME=/usr/lib/jvm/default-java



    ubuntu@ip-172-31-16-183:
    ~/Big-Data-Tools/hadoop-3.3.5
        $ cat  etc/hadoop/hadoop-env.sh

            export JAVA_HOME=/usr/lib/jvm/default-java

    ubuntu@ip-172-31-16-183:~/Big-Data-Tools/hadoop-3.3.5$ bin/hadoop --help
        Usage: hadoop [OPTIONS] SUBCOMMAND [SUBCOMMAND OPTIONS]
        or    hadoop [OPTIONS] CLASSNAME [CLASSNAME OPTIONS]
        where CLASSNAME is a user-provided Java class

        OPTIONS is none or any of:

        --config dir                     Hadoop config directory
        --debug                          turn on shell script debug mode
        --help                           usage information
        buildpaths                       attempt to add class files from build tree


---

    - Esto significa que con los pasos anteriores Hadoop (Standalon) esta instalado ... 


------------     

## Standalone Operation


------------
Demo 01

https://hadoop.apache.org/docs/r1.2.1/single_node_setup.html

    ubuntu@ip-172-31-16-183:~/Big-Data-Tools/hadoop-3.3.5/etc/hadoop$ ls *xml
    capacity-scheduler.xml  hadoop-policy.xml  hdfs-site.xml    kms-acls.xml  mapred-site.xml
    core-site.xml           hdfs-rbf-site.xml  httpfs-site.xml  kms-site.xml  yarn-site.xml

    $ mkdir input
    $ cp conf/*.xml input
    $ bin/hadoop jar hadoop-examples-*.jar grep input output 'dfs[a-z.]+'
    $ cat output/*

Demo 02
https://hadoop.apache.org/docs/r1.2.1/mapred_tutorial.html#Example%3A+WordCount+v1.0



