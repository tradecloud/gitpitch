---?image=akka-kafka/assets/img/bg/Open19-Rack-Photo.jpg&opacity=40
@title[Intro]

@snap[west title span-50]
@color[white]
@size[1.4em](Akka and Kafka)   
@size[1.0em](at Tradecloud)   
@snapend

@snap[south-west tc-link span-50]
https://www.open19.org/project/  
https://www.packet.com/cloud/servers/
@snapend

@snap[east contact span-45]
@size[1.5em](Marcel Matthijs)  
@size[1.0em](marcel@tradecloud.nl)
@size[1.0em]
@snapend

@snap[south-east span-45]
@size[0.8em](https://www.tradecloud1.com)
@snapend

---?image=assets/img/bg/tradecloud-light-blue.png&position=left&size=50% 100%
@title[Kafka for managers]

@snap[north-west]
@size[1.3em](Kafka for managers)
@snapend

@snap[west kafka-arch-details span-50]
![](akka-kafka/assets/img/kafka-architecture.png)
@snapend

@snap[south-west tc-link]
https://thenewstack.io/apache-kafka-primer/
@snapend

@snap[east kafka-arch span-45]
@color[white]
@size[1.0em](producer) @size[0.5em](publishes) @size[1.0em](message)  
@size[1.0em](message) @size[0.5em](consists of) @size[1.0em](bytes) 
@size[1.0m](message) @size[0.5em](published to) @size[1.0em](topic)  
@size[1.0em](message) @size[0.5em](written to) @size[1.0em](partition)  
@size[1.0em](partition) @size[0.5em](replicates over) @size[1.0em](cluster)  
@size[0.9em](consumer) @size[0.5em](connects to) @size[1.0em](partition)  
@size[0.9em](consumer) @size[0.5em](subscribes to) @size[1.0em](topic)  
@size[1.0em](consumer) @size[0.5em](maintains) @size[1.0em](offset)  
@size[1.0em](consumer) @size[0.5em](has) @size[1.0em](lag)
@ulend
@snapend

Note:
- show Kafka manager - one topic - 2 partitions - consumers

---?image=assets/img/bg/tradecloud-light-blue.png&position=left&size=50% 100%
@title[Use cases of Kafka]
@snap[north-west]
@size[1.3em](Use cases of Kafka)
@snapend

@snap[west span-50]
@size[1.0em]
Messaging System  
Storage System  
Stream Processing  
@snapend

@snap[south-west tc-link span-50]
https://kafka.apache.org/intro.html
@snapend

@snap[east span-45]
@color[white]
@size[0.7em](LinkedIn, Netflix, Uber) @size[0.5em](- Apache Samza)
@size[0.7em](Hyperledger Fabric)  @size[0.5em](- tx ordering service) 
@size[0.8em](New York Times) @size[0.5em](- publishing pipeline)  
@size[0.9em](Rabobank) @size[0.5em](- business event bus)  
@size[0.9em](Tradecloud) @size[0.5em](- event bus)  
@size[0.9em](Zalando) @size[0.5em](- real time business intelligence)  
@snapend

@snap[south-east tc-link span-50]
http://samza.apache.org/  
https://medium.com/swlh/hyperledger-chapter-6-hyperledger-fabric-components-technical-context-767985f605dd  
https://kafka.apache.org/documentation/streams/
@snapend

Note:
- 
---?image=assets/img/bg/tradecloud-light-blue.png&position=left&size=50% 100%
@title[Pro's and cons of Kafka]
@snap[north-west]
@size[1.3em](Pro's of Kafka)
@snapend

@snap[west span-50]
High througput @size[0.5em](- *millions msg p/s*)  
Very scalable @size[0.5em](- *100s brokers*)  
Reliable @size[0.5em](- *fault tolerant, durable*)  
Easy of use @size[0.5em](- *for producers/consumers*)
@snapend

@snap[south-west tc-link span-50]
https://engineering.linkedin.com/kafka/running-kafka-scale
@snapend

@snap[north-east span-45]
@size[1.3em](Cons of Kafka)
@snapend

@snap[east span-45]
@size[1.0em]
@size[0.9em](No protocols) @size[0.5em](- *API's*)
@size[0.9em](Deployment) @size[0.5em](- *Zookeeper*)  
@size[0.8em](Configuration) @size[0.4em](- *producer, broker, consumer*)  
@size[0.8em](Monitoring) @size[0.4em](- *Burrow, Confluent Enterprise*)  
@size[0.8em](Management) @size[0.5em](- *Kafka manager, Confluent*)  
@size[0.8em](Multi-dc) @size[0.5em](- *Confluent Enterprise*)   
@size[0.8em](Auto balancer) @size[0.5em](- *Confluent Enterprise*)  
@snapend

@snap[south-east tc-link span-45]
https://kafka.apache.org/documentation/#configuration
https://github.com/linkedin/Burrow  
https://github.com/yahoo/kafka-manager 
https://www.confluent.io/product/confluent-enterprise/
@snapend
---
### Event-driven architecture

---
### Software architecture

---
### Clustered infrastructure

Broker
Cluster
Zookeeper
One cluster, multi DC in one region
Multiple regions, use replication

---
### Broker configuration


Note:
controlled.shutdown.enable=true
default.replication.factor=3
min.insync.replicas=2
default.replication.factor=3
offsets.topic.replication.factor=3
offsets.retention.minutes=10080
num.partitions=2
log.dir=/opt/kafka/spool
- /opt/kafka/kafka_1.1.1/config/server.properties
- broker log.dir when using only one DC, persist the log, but not in /tmp
- consumer auto.offset.reset latest
- Use broker documentation defaults, not distribution defaults nor examples

---
### Alpakka Kafka 

https://github.com/akka/alpakka-kafka
https://doc.akka.io/docs/akka-stream-kafka/current/
---
### Tradecloud Akka-Kafka

Wrapper around alpakka-kafka
Resilience
Akka Serialization

https://github.com/tradecloud/akka-kafka
---
### Akka-Kafka inner workings

Subscriber
Publisher

---
### Akka-Kafka example usage

Subscriber
Publisher

---
### Wrap up

Contact


