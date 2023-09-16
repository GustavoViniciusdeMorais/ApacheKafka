# Apache Kafka Studies

Created By: Gustavo Morais

https://hub.docker.com/r/gustavovinicius/guskafka

### Enter container
```
sudo docker exec -it -u 0 guskafka bash
```

## Kafka commands version 2

### Start the ZooKeeper service
```
bin/zookeeper-server-start.sh config/zookeeper.properties
```

### Start the Kafka broker service
```
bin/kafka-server-start.sh config/server.properties
```

### Create a topic to store events
Kafka is a distributed event streaming platform that lets you read, write, store, and process events
(also called records or messages in the documentation) across many machines.
Very simplified, a topic is similar to a folder in a filesystem, and the events are the files in that folder.
```
bin/kafka-topics.sh --create --topic [topic-name] --bootstrap-server localhost:9092
```

### Write events into the topic
A Kafka client communicates with the Kafka brokers via the network for writing (or reading) events. Once received, the brokers will store the events in a durable and fault-tolerant manner for as long as you need—even forever.
Run the console producer client to write a few events into your topic. By default, each line you enter will result in a separate event being written to the topic.
```
bin/kafka-console-producer.sh --topic [topic-name] --bootstrap-server localhost:9092
```

### Read the events
Open another terminal session and run the console consumer client to read the events you just created.
Stop with Ctrl + C.
```
bin/kafka-console-consumer.sh --topic [topic-name] --from-beginning --bootstrap-server localhost:9092
```