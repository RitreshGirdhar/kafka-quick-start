# kafka-quick-start


https://medium.com/rahasak/kafka-and-zookeeper-with-docker-65cff2c2c34f 

docker run -d --name zookeeper -p 2181:2181 jplock/zookeeper

docker run -d --name kafka -p 7203:7203 -p 9092:9092  -e KAFKA_ADVERTISED_HOST_NAME=10.4.1.29 -e ZOOKEEPER_IP=10.4.1.29 ches/kafka

docker run --rm ches/kafka kafka-topics.sh --create --topic topic1 --replication-factor 1 --partitions 1 --zookeeper 10.4.1.29:2181

docker run --rm --interactive ches/kafka kafka-console-producer.sh --topic topic1 --broker-list 192.168.1.6:9092

