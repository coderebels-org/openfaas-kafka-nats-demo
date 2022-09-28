# openfaas-kafka-nats-demo
Demo of how to trigger [OpenFaas](https://www.openfaas.com/) Functions from 
[Kafka](https://kafka.apache.org/) using the kafka-nats-bridge

----
## !!! Deprecation Notice !!!
The OpenFaaS Team decided to not support nats-streaming in the now so-called Community Edition
anymore. It should not be working from June 2023. If we didn't miss a thing, from then on it is
only a Pro feature for paying customers - what a pity!

For more information on the changes in OpenFaaS check out their documentation. You can start here:
https://docs.openfaas.com/openfaas-pro/introduction/#comparison

This demo is working with the current (Sep 2022) versions of the used tools.

----

## Why? What's it all about?
OpenFaaS has no Kafka Trigger to start a function in the non-payed Version. But it is possible
to trigger a function via [NATS](https://nats.io/) Messaging.

So the purpose of this demo is to show how you can trigger functions with Kafka anyway - using 
the [NATS-Kafka Bridge](https://github.com/nats-io/nats-kafka).

The other way, sending a Kafka message from a OpenFaaS function works as well with this solution.

## Overview
![Setup overview](openfaas-kafka-nats-setup.png)

- From Kafka messages supposed to trigger functions will be send
- The NATS-Kafka Bridge listens for those topics, translates them to NATS messages
  and sends them out to all subscribers
- OpenFaaS has the [nats-connector](https://github.com/openfaas/nats-connector) installed
  which subscribes to NATS Messages for functions. When such a message is received it will
  trigger all functions which are listening to this type of message.

  ## The setup

  _TBD / WIP ..._