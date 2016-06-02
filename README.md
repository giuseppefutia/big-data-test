# Big Data Test
This repository contains my tests on the Hadoop platform

## Test Hadoop configuration files

Check items in a configuration file:

```
hadoop fs -conf conf/hadoop-localhost.xml -ls
```

Pick up the properties of *conf/hadoop-localhost.xml*:

```
mvn compile
export HADOOP_CLASSPATH=target/classes
hadoop ConfigurationPrinter -conf conf/hadoop-localhost.xml | grep yarn.resourcemanager.address=
```

The result should be: yarn.resourcemanager.address=localhost:8032

## How to run the Driver

### Run the Max Temperature example Driver locally
In this case you must load the hadoop-local configuration file to test MapReduce in your local machine:

```
mvn compile
export HADOOP_CLASSPATH=target/classes/
hadoop MaxTemp.MaxTemperatureDriver -conf conf/hadoop-local.xml src/main/resources/sample.txt output
```

Exploiting the GenericOptionsParser, you can also write:

```
hadoop MaxTemp.MaxTemperatureDriver -fs file:/// -jt local src/main/resources/sample.txt output
```


