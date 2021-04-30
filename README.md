# rabbiTMQuest
RabbitMQ + Telegraf + QuestDB Stack for AMQP / MQTT PubSub Systems

```
rabbITMQuest
       -----
       |-- QuestDB 5.0.3
     -
     |-- Telegraf v1.18
---
 |-- RABBITMQ 3.8
```

## Architecture

![rabbITMQ Basic Architecture](./.github/images/rabbiTMQuest.png)

### Components

1. [RabbitMQ Message Broker](https://www.rabbitmq.com/): A powerful messaging broker that can _broker_ with a lot of well-known Protocols namely __MQTT__, __AMQP__, __STOMP__ etc.

2. [Telegraf](https://www.influxdata.com/time-series-platform/telegraf/): A powerful agent to help collect metrics. A software _Swiss-Knife_.

3. [QuestDB](https://questdb.io): A Blazing Fast Time-Series Database that queries and processes data before you could say rabbitMQuest.


### MQTT -> AMQP Bridging

RabbitMQ Provides the MQTT v3.1.1 in-built plugin and provides an internal mechanism to convert MQTT Topics into AMQP Queue bindings quite easily.
[Documentation](https://www.rabbitmq.com/mqtt.html#implementation)

__Example__

| MQTT Topic          | AMQP Queue          |
|---------------------|---------------------|
| `IOT/sensorID/temp` | `IOT.sensorID.temp` |

> Hence, Publish with MQTT, Consume with AMQP and no need to write exclusive services / scripts to store it into _QuestDB_


## Usage

The Repository provides the __rabbiTMQuest__ Stack with basic security

| Stack Name          | Security               |
|:-------------------:|------------------------|
| `prototype`         | basic level passwords  |

__NOTE__: refer to `prototype` directory since it has its own `README.md` and SHOULD be referred to for initial configuration / customization

### Commands

    docker-compose -f prototype/docker-compose.prototype.yml up

## License
__MIT License__

## Contributing
Please use __GitHub Issues__ for queries, bugs etc. and feel free to open Pull-Requests for improvements, bug fixes etc.
