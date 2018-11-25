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
@snapend

@snap[south-east span-45]
@size[0.8em](https://www.tradecloud1.com)
@snapend

Note:
- Show Tradecloud site
- Show open19 project
- Show packet.net server

---?image=assets/img/bg/tradecloud-light-blue.png&position=left
@title[Menu]

@snap[north-west span-35]
@box[bg-green text-white](Kafka#for managers<br>Use cases<br>Pro's and cons)
@snapend

@snap[north-east span-35]
@box[bg-orange text-white rounded](Architecture#Event driven<br>Service<br>Infrastructure<br>Configuration)
@snapend

@snap[south-west span-35]
@box[bg-blue text-white waved](Messages#Structure<br>Metadata<br>Serialization)
@snapend

@snap[south-east span-35]
@box[bg-pink text-white](Libraries#akka-stream-kafka<br>akka-kafka)
@snapend

---?image=assets/img/bg/tradecloud-light-blue.png&position=left&size=50% 100%
@title[Kafka for managers]
@snap[north-west]
@box[bg-green text-white tc-small-box](Kafka#for managers)
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
- Consumers groups

---?image=assets/img/bg/tradecloud-light-blue.png&position=left&size=50% 100%
@title[Use cases of Kafka]
@snap[north-west]
@box[bg-green text-white tc-small-box](Kafka#use cases)
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
- Show Samza site
- Show Fabric site, tell about Simplified Byzantine Fault Tolerance alternative
- Show Kafka streams usrs

---?image=assets/img/bg/tradecloud-light-blue.png&position=left&size=50% 100%
@title[Pro's and cons of Kafka]
@snap[north-west]
@box[bg-green text-white tc-small-box](Kafka#Pro's)
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

@snap[north-east]
@box[bg-green text-white tc-small-box](Kafka#Cons)
@snapend

@snap[east span-45]
<br>
@size[0.8em](Deployment) @size[0.5em](- *Zookeeper*)  
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

Note:
- Show LinkedIn Kafka scale
- Show and scroll through Kafka configuration page
- Show Burrow features

---?image=assets/img/bg/tradecloud-light-blue.png&position=left
@title[Event-driven components]
@snap[north-west span-20]
@box[bg-orange text-white rounded tc-small-box](Architecture#Event driven components)
@snapend
![](akka-kafka/assets/img/event-driven-components.svg)

@snap[south-west tc-link]
https://martinfowler.com/articles/201701-event-driven.html
@snapend

Note:
- Show Fowler article, What do you mean by “Event-Driven”?
- Show write and read side

---?image=assets/img/bg/tradecloud-light-blue.png
@title[Event-driven flow]
@snap[north-west span-25]
@box[bg-orange text-white rounded tc-small-box](Architecture#Event driven flow)
@snapend

@snap[center]
<br>
![](akka-kafka/assets/img/event-driven-flow.svg)
@snapend

Note:
- Show user / portal is asynchronous
- Show order: 1. Publish 2. Persist 3. Push websocket

---?image=assets/img/bg/tradecloud-light-blue.png&position=left
@title[Stateful service components]
@snap[north-west span-20]
@box[bg-orange text-white rounded tc-small-box](Architecture#Stateful service components)
@snapend
![](akka-kafka/assets/img/stateful-service-components.svg)

Note:
-

---?image=assets/img/bg/tradecloud-light-blue.png
@title[Stateful service flow]
@snap[north-west span-25]
@box[bg-orange text-white rounded tc-small-box](Architecture#Stateful service flow)
@snapend

@snap[center]
<br>
![](akka-kafka/assets/img/stateful-service-flow.svg)
@snapend

Note:
- EntityActor uses Cluster Sharding and auto-passivation
- Order of 1. Publish 2. Persist -> Lightbend Lagom
- Akka 2.5.18 https://github.com/akka/akka/issues/25512 auto-passivation in Sharding Typed

---?image=akka-kafka/assets/img/bg/monit-kafka.png&opacity=40
@title[Clustered infrastructure]
@snap[north-west span-25]
@box[bg-orange text-white rounded tc-small-box](Architecture#Clustered infrastructure)
@snapend

![](akka-kafka/assets/img/kafka-deployment.svg)

Note:
- Zookeeper - master
- Broker - controller
- partition - leader / follower
- Consuomer group

---?image=akka-kafka/assets/img/bg/kafka-server-properties.png&opacity=40
@title[Broker configuration]
@snap[north-west span-25]
@box[bg-orange text-white rounded tc-small-box](Architecture#Broker configuration)
@snapend

@snap[north-west]
<br>
<br>
@size[0.6em](Use documentation defaults, not distribution defaults)  
@size[0.6em](When using only one DC, persist the log, but not in /tmp)
@snapend

```console
num.partitions=2  
default.replication.factor=3  
min.insync.replicas=2  
offsets.topic.replication.factor=3  
offsets.retention.minutes=10080  
log.dir=/opt/kafka/spool  
controlled.shutdown.enable=true
```

@snap[south-west tc-link span-45]
https://kafka.apache.org/documentation/#configuration
@snapend

Note:
- /opt/kafka/kafka_1.1.1/config/server.properties
- broker log.dir when using only one DC, persist the log, but not in /tmp
- consumer auto.offset.reset latest
- Use broker documentation defaults, not distribution defaults nor examples

---?image=akka-kafka/assets/img/bg/alpakkas.jpg&opacity=40
@title[Alpakka Kafka]
@snap[north-west span-25]
@box[bg-pink text-white tc-small-box](Libraries#akka-stream-kafka)
@snapend

```scala
  val control =
    Consumer
      .committableSource(consumerSettings, 
        Subscriptions.topics(topic))
      .mapAsync(10) { msg =>
        business(msg.record.key, msg.record.value).map(
          _ => msg.committableOffset)
      }
      .mapAsync(5)(offset => offset.commitScaladsl())
      .toMat(Sink.seq)(Keep.both)
      .mapMaterializedValue(DrainingControl.apply)
      .run()

def business(key: String, value: Array[Byte]): 
  Future[Done] = // ???
```

@snap[south-west tc-link span-45]
https://developer.lightbend.com/docs/alpakka/current/
https://doc.akka.io/docs/akka-stream-kafka/current/
https://github.com/akka/alpakka-kafka
@snapend

Note:
- marketing Alpakka Kafka, library akka-stream-kafka
- Camel still maintained, but Kakfa docs do not look good 
---?image=assets/img/bg/tradecloud-light-blue.png&position=left
@title[Tradecloud Akka Kafka]
@snap[north-west span-25]
@box[bg-pink text-white tc-small-box](Libraries#akka-kafka)
@snapend

```scala
new KafkaSubscriber(
    group = "some_group_name",
    topics = Set("some_topic")
  ).atLeastOnce(
    Flow[String]
      .map { wrapper: KafkaMessage[String] =>
        println(wrapper.msg + "-world")
        msg.offset
      }
  )
```

```scala
val publisher = new KafkaPublisher()
publisher.publish("topic", msg)
```

@snap[south-west tc-link span-45]
https://github.com/tradecloud/akka-kafka
https://doc.akka.io/docs/akka/current/serialization.html
@snapend

Note:
- Wrapper around akka-stream-kafka
- Resilience
- Akka Serialization
---
### Akka-Kafka inner workings

Subscriber
Publisher

---
### Akka-Kafka example usage

Subscriber
Publisher
---?image=assets/img/bg/201612-foto-yesdelft-met-rutte.jpg&opacity=60
@title[Wrap up]
@snap[north-west]
@size[1.0em](Wrap up)
@snapend

@snap[west contact span-50]
@size[1.5em](Questions?)  
@snapend

@snap[east contact span-45]
@size[1.5em](Marcel Matthijs)  
@size[1.0em](marcel@tradecloud.nl)
@size[1.0em](YES!Delft building)
@snapend

---?video=https://www.yesdelft.com/wp-content/themes/yesdelft-website/assets/vid/header-video.mp4
@title[Join Tradecloud]
Join Tradecloud at YES!Delft  
Senior Scala Developer  
https://jobs.tradecloud.nl/o/scala-backend-developer