# cares-platform-integration

A proof of concept (POC) for synchronizing data between Neutron and CWS/CMS.

## Components

* [Kafka](#kafka)
* [IBM MQ](#ibm_mq)
* [MQ TO KAFKA](#mq_to_kafka)


## Kafka

[Apache Kafka](https://kafka.apache.org/) is a distributed streaming platform that stores messages in categories known as 'Topics'. There are four core APIs in Kafka: Prodcuer API, Consumer API, Streams API, and Connector API. This POC will use APIs in relevant components. More information about how kafka functions can be seen in their documentation.

Docker containers for Kafka and other tools are provided by the [confluent open source platform](https://www.confluent.io/product/confluent-open-source/)


To start all confluent platform services with Kafka and IBM-MQ you can use the following command:

```docker-compose up -d confluent-kafka/docker-compose.yml```

## IBM MQ
[IBM MQ](#ibm_mq)

Data model is coming from MQ is described in resources/xsd/mqcap.xsd 

## MQ TO KAFKA

[MQ TO KAFKA](#mq_to_kafka)


To start test application use command:

```
./gradlew clean build

cd build/libs

java -jar demo-0.0.1-SNAPSHOT.jar
```

In Eclipse, include folder "src/generated-sources/java" in the build path. Compilation errors disappear!

To launch Kafka in Docker, "cd" to the "docker" directory and run:

```docker-compose up```

To send a test message to the queue use the following command:

```curl localhost:8080/send```

Open a browser and navigate to the link below to view messages:

```http://localhost:8000/#/cluster/default/topic/n/replication/```
