# kafka-microservices

### Apache Kafka

- Apache Kafka is a distributed streaming platform.
- Apache Kafka is used to process real-time data feeds with high throughput and low latency. Ex: flights data, sensors data, stocks data, news data, social media, etc.
- Kafka works based on the Publisher and Subscriber model.

### Kafka Terminology
- Zookeeper
- Kafka Server
- Kafka Topic
- Message
- Publisher
- Subscriber

### Kafka APIs

- Connector API
- Publisher API
- Subscriber API
- Streams API


========================================
Spring Boot + Apache Kafka Application
=======================================

### Step 1: Download Zookeeper from the following URL

   URL: [Download Zookeeper](http://mirrors.estointernet.in/apache/zookeeper/stable/)

### Step 2: Download Apache Kafka from the following URL

   URL: [Download Apache Kafka](http://mirrors.estointernet.in/apache/kafka/)

### Step 3: Set Path to ZOOKEEPER in Environment variables up to the bin folder

### Step 4: Start Zookeeper server using the following command from the Kafka folder

    Command: `zookeeper-server-start.bat zookeeper.properties`

    Note: The above command will be available in kafka/bin/windows folder.

    Note: zookeeper.properties file will be available in kafka/config folder. You can copy zookeeper.properties and server.properties files from kafka/config folder to kafka/bin/windows folder.

### Step 5: Start Kafka Server using the following command from the Kafka folder

    Command: `kafka-server-start.bat server.properties`

    Note: server.properties file will be available in the config folder (Copied to windows folder).

### Step 6: Create Kafka Topic using the following command from kafka/bin/windows folder

    Command: `kafka-topics.bat --create --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1 --topic demo-jrtp22-topic`

### Step 7: View created Topics using the following command

      Command: `kafka-topics.bat --list --bootstrap-server localhost:9092`

============================================
Step 8: Create Spring Boot Project in IDE
============================================

### Step 9: Add the following Kafka related dependencies in pom.xml

```xml
<dependency>
    <groupId>org.apache.kafka</groupId>
    <artifactId>kafka-streams</artifactId>
</dependency>
<dependency>
    <groupId>org.springframework.kafka</groupId>
    <artifactId>spring-kafka</artifactId>
</dependency>
<dependency>
    <groupId>com.fasterxml.jackson.core</groupId>
    <artifactId>jackson-databind</artifactId>
</dependency>
```

### Step 10: Create RestController, KafaProducer and KafaConsumer classes to publish and subscribe message
### Step 11: Test application using PostMan.

```json
{
    "customerId": 101,
    "customerName": "Suraj",
    "customerEmail": "suraj@gmail.com"
}
```

```json
[
    {
        "customerId": 101,
        "customerName": "Suraj",
        "customerEmail": "suraj@gmail.com"
    },
    {
        "customerId": 102,
        "customerName": "Raj",
        "customerEmail": "raj@gmail.com"
    },
    {
        "customerId": 102,
        "customerName": "John",
        "customerEmail": "john@gmail.com"
    }
]
```



