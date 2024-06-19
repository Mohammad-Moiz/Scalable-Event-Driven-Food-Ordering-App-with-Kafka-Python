# Scalable-Event-Driven-Food-Ordering-App-with-Kafka-Python
A highly scalable backend system for a food ordering app. The system is event driven. Every important thing is an event, such as an order being placed and an order being confirmed.   These events are written to Apache Kafka which is a central bus for all moving data. Other systems, such as the transaction system or the email system, will be built on top of Apache Kafka. They will subscribe to different Kafka topics that they are concerned with, and process in real time as these messages are written to Kafka. 

We use a library called kafka-python to hook up a locally running Kafka broker and our Python code. 

The system should be highly scalable. Given the decoupled nature, you can scale up or down individual components as required. These individual components can either be microservices or some stream processing jobs or just plain Python files like I do here. 

The system is also very extensible because of the nature of Apache Kafka. The messages for a given topic can be retained within Kafka. That means, if you were to build a new component, you could replay all the messages of a topic from the beginning and make the component process all messages from the beginning of the topic. 

Similarly, given the persistence of Kafka, if there is an issue with any downstream or upstream system, you won't suffer from any data loss. 
