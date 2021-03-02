# Kafka-individual-2

### Swaroopa Tirumalareddy
Github profile link: https://github.com/swaroopatirumalareddy 

## Commands to Start Services:
### Zookeeper:
- To start a zookeeper service, open Powershell in your C:\kafka_2.13-2.7.0 directory and run this command

```Powershell
.\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties
```

### Kafka:
- To start a kafka service, open Powershell in your C:\kafka_2.13-2.7.0 directory and run this command

```Powershell
.\bin\windows\kafka-server-start.bat .\config\server.properties
```
### Create a topic
- Create a new topic,open Powershell in your C:\kafka_2.13-2.7.0 directory and run this command

```PowerShell
 .\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --create --topic displaydata
```
## Compile and Build the Fat Jar File

- Open PowerShell in the root project folder, then compile the code using Maven and create an executable jar file. Generated artificacts can be found in the new 'target' folder.

```PowerShell
mvn clean compile assembly:single
```
## Consumer

- Open PowerShell in the root project folder, start the original consumer app using topic displaydata and group1 with:

```PowerShell
  java -cp target/kafka-individual-2-1.0-SNAPSHOT-jar-with-dependencies.jar edu.nwmissouri.bigdata.swaroopa.Consumer displaydata group1
```
## Producer

- Open PowerShell in the root project folder then, start the Producer app using topic displaydata:

```PowerShell
  java -cp target/kafka-individual-2-1.0-SNAPSHOT-jar-with-dependencies.jar edu.nwmissouri.bigdata.swaroopa.ProducerBySwaroopa displaydata
```
