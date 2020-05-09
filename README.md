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
