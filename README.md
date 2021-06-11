# Quickly Set up kafka

Below are the commands to quickly setup kafka using docker.


```
docker run -d --name zookeeper -p 2181:2181 jplock/zookeeper
docker run -d --name kafka -p 7203:7203 -p 9092:9092  -e KAFKA_ADVERTISED_HOST_NAME=<ipaddress> -e ZOOKEEPER_IP=<ipaddress> ches/kafka

docker run --rm ches/kafka kafka-topics.sh --list --zookeeper 192.168.1.4:2181

docker run --rm ches/kafka kafka-topics.sh --create --topic topic1 --replication-factor 1 --partitions 1 --zookeeper <ipaddress>:2181
docker run --rm --interactive ches/kafka kafka-console-producer.sh --topic topic1 --broker-list <ipaddress>:9092

```

I don't set up tools on my local, as docker is the easiest way to set up service/tool on demand. So, I am creating this repo to keep shortnote on setting up kafka on local.
