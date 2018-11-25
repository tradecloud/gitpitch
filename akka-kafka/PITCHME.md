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
- ASK FOR QUESTIONS DURING THE PRESENTATION

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
- Show Kafka manager - one topic - 2 partitions - consumers
- Explain consumers groups

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
![](akka-kafka/assets/img/event-driven-components.png)

@snap[south-west tc-link]
https://martinfowler.com/articles/201701-event-driven.html
@snapend

Note:
- Show Fowler article, What do you mean by “Event-Driven”?
- Explain write and read side

---?image=assets/img/bg/tradecloud-light-blue.png
@title[Event-driven flow]
@snap[north-west span-25]
@box[bg-orange text-white rounded tc-small-box](Architecture#Event driven flow)
@snapend

@snap[center]
<br>
![](akka-kafka/assets/img/event-driven-flow.png)
@snapend

Note:
- Explain API vs subscriber use case
- Show portal is asynchronous
- Show websocket

---?image=assets/img/bg/tradecloud-light-blue.png&position=left
@title[Stateful service components]
@snap[north-west span-20]
@box[bg-orange text-white rounded tc-small-box](Architecture#Stateful service components)
@snapend
![](akka-kafka/assets/img/stateful-service-components.png)

Note:
- Explain subscriber-publisher use case

---?image=assets/img/bg/tradecloud-light-blue.png
@title[Stateful service flow]
@snap[north-west span-25]
@box[bg-orange text-white rounded tc-small-box](Architecture#Stateful service flow)
@snapend

@snap[center]
<br>
![](akka-kafka/assets/img/stateful-service-flow.png)
@snapend

Note:
- Explain EntityActor uses Cluster Sharding and auto-passivation
- Akka 2.5.18 https://github.com/akka/akka/issues/25512 auto-passivation in Sharding Typed

---?image=akka-kafka/assets/img/bg/monit-kafka.png&opacity=40
@title[Clustered infrastructure]
@snap[north-west span-25]
@box[bg-orange text-white rounded tc-small-box](Architecture#Infrastructure)
@snapend

@snap[center]
<br>
![](akka-kafka/assets/img/kafka-deployment.png)
@snapend

Note:
- Explain Zookeeper - master
- Explain Broker - controller
- Explain partition - leader / follower
- Explain consumer group

---?image=akka-kafka/assets/img/bg/kafka-server-properties.png&opacity=40
@title[Broker configuration]
@snap[north-west span-25]
@box[bg-orange text-white rounded tc-small-box](Architecture#Broker configuration)
@snapend

```console
// Use documentation defaults, not distribution defaults

num.partitions=2

default.replication.factor=3  

min.insync.replicas=2  

offsets.topic.replication.factor=3  

offsets.retention.minutes=10080  

log.dir=/opt/kafka/spool // not in /tmp when using one DC

controlled.shutdown.enable=true
```

@snap[south-west tc-link span-45]
https://kafka.apache.org/documentation/#configuration
@snapend

Note:
- /opt/kafka/kafka_1.1.1/config/server.properties

---?image=assets/img/bg/tradecloud-light-blue.png
@title[Messages Structure]
@snap[north-west span-25]
@box[bg-blue text-white waved tc-small-box](Messages#Structure)
@snapend

```scala
package com.tradecloud1.messages
```

```scala
trait Event {
  def publishTopics: Seq[String]
  def meta: MessageMeta
}
```

```scala
sealed trait OrderEvent extends Event {
  def id: String
```

```scala
final case class OrderIssuedByBuyer(
    id: String,
    lines: Seq[OrderLine],
...
) extends OrderEvent {
  val publishTopics: Seq[String] = ...
```

Note:
- Explain Git submodule messages
- Show OrderIssuedByBuyer

---?image=assets/img/bg/tradecloud-light-blue.png
@title[Messages Metadata]
@snap[north-west span-25]
@box[bg-blue text-white waved tc-small-box](Messages#Metadata)
@snapend

```scala
case class MessageMeta(
    messageId: UUID = UUID.randomUUID(),
    source: MessageSource,
    createdDateTime: DateTime = DateTime.now()
)
```

```scala
case class MessageSource(
    traceId: UUID = UUID.randomUUID(),
    userId: Option[UUID],
    companyId: Option[UUID]
)
```

Note:
- Explain: used for tracing and activity stream

---?image=assets/img/bg/tradecloud-light-blue.png
@title[Messages Serialization]
@snap[north-west span-25]
@box[bg-blue text-white waved tc-small-box](Messages#Serialization)
@snapend

```protobuf
syntax = "proto3";
option java_package = "com.tradecloud1.messages.order";

message OrderIssuedByBuyerMsg {
    google.protobuf.StringValue id    = 1;
    repeated order.OrderLineMsg lines = 2;
...
```

```scala
class ProtobufSerializer extends SerializerWithStringManifest
  with OrderToProtobufTransformers 
  with OrderFromProtobufTransformers {
  
  val OrderIssuedByBuyerManifest = "900"

  def toBinary(o: AnyRef): Array[Byte]
  def fromBinary(bytes: Array[Byte], manifest: String): AnyRef
```

@snap[south-west tc-link span-45]
https://doc.akka.io/docs/akka/current/serialization.html
@snapend

Note:
- Explain: Protobuf compiled to Scala and Golang
- Explain: Also using Json for data migration 
- Show: OrderToProtobufTransformers / OrderFromProtobufTransformers

---?image=akka-kafka/assets/img/bg/alpakkas.jpg&opacity=40
@title[Alpakka Kafka]
@snap[north-west span-25]
@box[bg-pink text-white tc-small-box](Libraries#akka-stream-kafka)
@snapend

@size[0.8em](Alpakka Kafka a.k.a. akka-stream-kafka f.k.a. reactive-kafka)

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
```

@snap[south-west tc-link span-45]
https://developer.lightbend.com/docs/alpakka/current/
https://doc.akka.io/docs/akka-stream-kafka/current/
https://github.com/akka/alpakka-kafka
@snapend

Note:
- Explain marketing Alpakka Kafka, library akka-stream-kafka, previous reactive-kafka
- Camel still maintained, but Kakfa docs do not look good 

---?image=assets/img/bg/tradecloud-light-blue.png&position=left
@title[Tradecloud Akka Kafka]
@snap[north-west span-25]
@box[bg-pink text-white tc-small-box](Libraries#akka-kafka intro)
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
@snapend

Note:
- Tell: Wrapper around akka-stream-kafka
- Tell purpose: Resilience, Batching
- Tell purpose: Akka Serialization
- Show order listener
- Show order publisher

---?image=assets/img/bg/tradecloud-light-blue.png&position=left
@title[Tradecloud Akka Kafka config]
@snap[north-west span-25]
@box[bg-pink text-white tc-small-box](Libraries#akka-kafka config)
@snapend

Backoff, batching, and consumer configuration

```scala
final class KafkaSubscriber(
    group: String,
    topics: Set[String],
    serviceName: Option[String] = None,
    minBackoff: Option[FiniteDuration] = None,
    maxBackoff: Option[FiniteDuration] = None,
    batchingSize: Option[Int] = None,
    batchingInterval: Option[FiniteDuration] = None,
    configurationProperties: Seq[(String, String)] = Seq.empty
```
@snap[south-west tc-link span-45]
https://github.com/tradecloud/akka-kafka
@snapend

---?image=assets/img/bg/tradecloud-light-blue.png&position=left
@title[Tradecloud Akka Kafka Inside]
@snap[north-west span-25]
@box[bg-pink text-white tc-small-box](Libraries#akka-kafka inside)
@snapend

Flow build in KafkaSubscriber  
used in KafkaSubscriberActor

```scala
  def atLeastOnceStream[T](flow: Flow[KafkaMessage[T], ... 
    consumerSource
      .via(deserializeFlow)
      .via(filterTypeFlow[T])
      .via(flow)
      .via(commitFlow)
```

@snap[south-west tc-link span-45]
https://github.com/tradecloud/akka-kafka
@snapend

Note:
- Show KafkaSubscriber and KafkaSubscriberActor
- Show KafkaMessage

---?image=assets/img/bg/tradecloud-light-blue.png&position=left
@title[Tradecloud Akka Kafka Inside]
@snap[north-west span-25]
@box[bg-pink text-white tc-small-box](Libraries#akka-kafka inside)
@snapend

Flow build in KafkaPublisher  
used in KafkaPublisherActor

```scala
  def serializeAndPublishFlow(withRetries: Boolean)
      ...
      // connect the graph
      prefixFlowShape ~> broadcast.in
      broadcast.out(0) ~> serializerFlow ~> publishFlow(withRetries) ~> zip.in0
      broadcast.out(1) ~> publishCmdBufferFlow ~> zip.in1
      zip.out ~> resultTransformerShape
```

@snap[south-west tc-link span-45]
https://github.com/tradecloud/akka-kafka
https://doc.akka.io/docs/akka/current/serialization.html
@snapend

Note:
- Show KafkaPublisher and KafkaPublisherActor

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

@snap[south-west tc-link span-50]
https://gitpitch.com/tradecloud/gitpitch/master?p=akka-kafka  
https://github.com/tradecloud/akka-kafka
@snapend
---?video=https://www.yesdelft.com/wp-content/themes/yesdelft-website/assets/vid/header-video.mp4
@title[Join Tradecloud]
Join Tradecloud at YES!Delft  
Senior Scala Developer  
https://jobs.tradecloud.nl/o/scala-backend-developer