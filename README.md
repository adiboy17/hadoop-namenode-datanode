# hadoop-namenode-datanode
Setup of Hadoop name node and data node

## HADOOP:SETUP

### 1) Download the following file:

  - hadoop.rpm
  
  - jdk.rpm

### 2) Installed the software:

   -> rpm -ivh jdk.rpm
   
   -> rpm -ivh hadoop.rpm --force

### 3) Check software installed successfully using cmd:

    -> hadoop version
    
    -> java -version 

### 4) Namenode setup:

  -> cd /etc/hadoop/
   
   -> vim hdfs-site.xml

```Language

<configuration>
<property>
<name>dfs.name.dir</name>
<value>/nn</value>
</property>
</configuration>    

```
   -> hadoop namenode -format

   -> vim core-site.xml
   
```Language

<configuration>
<property>
<name>fs.default.name</name>
<value>hdfs://0.0.0.0:9001</value>
</property>
</configuration>

```
### CMD:

   -> hadoop-daemon.sh start namenode
   
   -> jps  
   
   -> netstat  -tnlp  | grep java

### 5) Datanode setup

 CMD:
 
   -> cd /etc/hadoop/

   ->   vim hdfs-site.xml
    
```Language

<configuration>
<property>
<name>dfs.data.dir</name>
<value>/dhadn1</value>
</property>
</configuration> 
    
```

### CMD :

  -> [location:hadoop]    mkdir /dn1
  
  ->    vim core-site.xml

```Language

<configuration>
<property>
<name>fs.default.name</name>
<value>hdfs://<public-ip>:9001</value>
</property>
</configuration>    

```

### CMD :

  ->    hadoop-daemon.sh start datanode

  ->  jps 

  -> hadoop dfsadmin -report
























