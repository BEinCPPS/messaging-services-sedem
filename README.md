# messaging-services-sedem

The SeDEM component has been conceived as a wrapper library intended to ease the publish and subscribe operations of AMQP clients of a RabbitMQ-based event broker, hiding underlying details of the mechanisms transparently provided by the library to grant confidentiality in the execution of these operations. 

The SeDEM library provides the following functionalities:
+ Event Creation: the library enables the creation of the Event dispatched to the broker. An Event is made up by the following parts:
  - headers: a set of (key, value) pairs the publisher can use to indicate some data useful to enable subscribers to correctly understand the payload of the event and/or to put the informative content of the event;
  - payload: an opaque list of bytes that represents the informative content of the event. NOTE: the informative content carried by an event may be put in the headers hence the message payload may be empty.
+ Publishing: provides the capability to send the generated Event to the event broker in a secure way.
+ Subscribing: enables the creation of a consumer for a specific set of events dispatched through the event broker. The actual processing of the events is performed by registering an event listener that is invoked every time a new event has been received by the subscriber.
