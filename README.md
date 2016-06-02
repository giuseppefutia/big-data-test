Check items in a configuration file

```
hadoop fs -conf conf/hadoop-localhost.xml -ls
```

Pick up the properties of *conf/hadoop-localhost.xml*

```
mvn compile
export HADOOP_CLASSPATH=target/classes
hadoop ConfigurationPrinter -conf conf/hadoop-localhost.xml | grep yarn.resourcemanager.address=
```

The result should be: yarn.resourcemanager.address=localhost:8032