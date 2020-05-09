# Hadoop

## 搭建单节点 Hadoop
https://hadoop.apache.org/docs/stable/hadoop-project-dist/hadoop-common/SingleCluster.html

**Hadoop Bin:**   
https://www.apache.org/dyn/closer.cgi/hadoop/common/


```
export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
export PATH=$JAVA_HOME/bin:$PATH
export CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar

```

##  搭建三节点大数据集群   
https://juejin.im/post/5dc93091518825409533cd65


```
 hostnamectl set-hostname 　ｘｘｘ
```


**vim /etc/hosts**

```
10.252.92.3 master
10.252.92.4 slave1
10.252.92.5 slave2
```


**Ubuntu  add user and add sudo **

```
# adduser username

```


```
# usermod -aG sudo username

```



### Ubuntu 18.04 更换源

```
ALI:
wget https://raw.githubusercontent.com/latermonk/Linux-Env-Config/master/Source/sources.list-alicloud-ubuntu18.04

163:
wget https://raw.githubusercontent.com/latermonk/Linux-Env-Config/master/Source/sources.list-163-ubuntu18.04

```




##  集群操作

```
bin/hadoop namenode -format

sbin/start-all.sh

hadoop dfsadmin -report


sbin/stop-all.sh

```



#  第一个wordcount例子
 
https://juejin.im/post/5e1594f1e51d4540e47ca934    




```
yarn jar $HADOOP_HOME/share/hadoop/mapreduce/hadoop-mapreduce-examples-3.2.1.jar wordcount /demo/word.txt /output

```


