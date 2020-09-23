# Kafka Installation

## Installing

1. Firstly, install or upgrade Maven and OpenJDK using the following commands
- choco install maven -y
- choco install openjdk -y
- refreshenv
- choco list -l

2. Now, go to [Kafka](https://kafka.apache.org/quickstart) and install the current source tgz file to C:\

3. Un-tar the downloaded file using ``` tar -xzf <filename> ``` and ``` cd <folder> ```

## Setting the environment variables

1. Go to Windows/ Edit the System Environment Variables / Environment Variables / System variables

2. Using the version that we previously installed set the following
- JAVA_HOME = C:\Program Files\OpenJDK\jdk-version folder
- KAFKA_HOME =  C:\kafka-version folder
- M2_HOME = C:\ProgramData\chocolatey\lib\maven\apache-maven-version
- Path includes %JAVA_HOME%\bin OR C:\Program Files\OpenJDK\jdk-version\bin
- %M2_HOME%\bin
- %KAFKA_HOME%\bin
- %KAFKA_HOME%\bin\windows

## Commands

1. To run Zookeeper Service

```  .\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties ```

2. To run Kafka Service

``` .\bin\windows\kafka-server-start.bat .\config\server.properties ```

3. To execute one-time commands (create, list, delete topics)

``` .\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --create --topic novels-list ```

``` .\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --list ```

4. To run Kafka Producer

``` .\bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic novels-list ```

5. To run Kafka Consumer

``` .\bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic novels-list --from-beginning ```

