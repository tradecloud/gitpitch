---?image=img/bg/tradecloud-light-blue.png&position=left&size=50% 100%

@snap[west title span-50]
@color[white]
@size[1.5em]Akka and Kafka at Tradecloud
@snapend

@snap[east contact span-45]
![](img/tradecloud_platform_logo1_hq.png)
@size[0.5em]Marcel Matthijs
@size[0.5em]marcel@tradecloud.nl
@snapend
---?image=img/bg/tradecloud-light-blue.png&position=left&size=50% 100%
@snap[north-west]
@size[1.5em](Kafka)
@snapend

@snap[west kafka-arch-details span-50]
![](akka-kafka/img/kafka-architecture.png)
@size[0.3em](https://thenewstack.io/apache-kafka-primer/)
@snapend

@snap[east kafka-arch span-45]
@color[white]
@ul[](false)
- producer -publishes-> message (bytes)
- message -published to-> topic
- message -written to-> partition
- partition -replicates over-> cluster
- consumer -connects to-> partition
- consumer(group) -subscribes to-> topic
- consumer(group) -maintains-> offset
@ulend
@snapend

Note:
- test
---
### Requirements that justify Kafka 
Messaging System
Storage System
Stream Processing

---
### Pros and cons of Kafka
Versus MOM


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


