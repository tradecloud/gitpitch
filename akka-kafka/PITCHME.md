---?image=akka-kafka/assets/img/bg/Open19-Rack-Photo.jpg&opacity=40
@snap[west title span-50]
@color[white]
@size[1.4em](Akka and Kafka)   
@size[1.0em](at Tradecloud)   
@snapend

@snap[south-west span-50]
@size[0.3em](https://www.open19.org/project/)  
@size[0.3em](https://www.packet.com/cloud/servers/)
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
@snap[north-west]
@size[1.3em](Kafka for managers)
@snapend

@snap[west kafka-arch-details span-50]
![](akka-kafka/assets/img/kafka-architecture.png)
@snapend

@snap[south-west]
@size[0.5em](https://thenewstack.io/apache-kafka-primer/)
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
@snap[north-west]
@size[1.3em](Use cases of Kafka)
@snapend

@snap[west span-50]
@size[1.0em]
Messaging System  
Storage System  
Stream Processing  
@snapend

@snap[south-west span-50]
@size[0.5em](https://kafka.apache.org/intro.html)
@snapend

@snap[east span-45]
@color[white]
@size[0.7em](LinkedIn, Netflix, Uber) @size[0.5em](- Apache Samza)  
@size[0.8em](New York Times) @size[0.5em](- publishing pipeline)  
@size[0.9em](Rabobank) @size[0.5em](- business event bus)  
@size[0.9em](Tradecloud) @size[0.5em](- event bus)  
@size[0.9em](Zalando) @size[0.5em](- real time business intelligence)  
@snapend

@snap[south-east span-50]
@size[0.3em](http://samza.apache.org/)
@size[0.3em](https://kafka.apache.org/documentation/streams/)
@snapend

Note:
- 
- show
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


