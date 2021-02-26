# Confluent-Kafka-Installing-on-MAC
A repo that give with the files and the process of installing Confluent Kafka and Java 8(required by it) on Mac Os Catelina.

## Steps :

![](pictures/Apache_Kafka_Connect_MQTT_Broker_Mosquitto_Integration.png)



Here is the full configuration for the MQTT Connector for Kafka Connect's Standalone mode, which we use with Confluent CLI for a local setup: 

                name=MqttSourceConnector1
                connector.class=io.confluent.connect.mqtt.MqttSourceConnector
                tasks.max=1
                mqtt.server.uri=< Required Configuration >
                mqtt.topics=< Required Configuration >

For distributed mode, you can use the same configuration with REST API:

                curl -s -X POST -H 'Content-Type: application/json' http://localhost:8083/connectors -d '{
                    "name" : "< Required Configuration >",
                "config" : {
                    "connector.class" : "io.confluent.connect.mqtt.MqttSourceConnector",
                    "tasks.max" : "1",
                    "mqtt.server.uri" : "< Required Configuration >",
                    "mqtt.topics" : "< Required Configuration >",
                    "kafka.topics" : "< Required Configuration >"
                }
                }'

