# Kafka Demo

### Kafka stack setup
    docker-compose up -d

### Create Kafka Topic
```
docker exec --interactive --tty kafka1  \
kafka-topics --bootstrap-server kafka1:19092 \
             --create \
             --topic test-topic \
             --replication-factor 1 --partitions 1

```

### Produce Messages to the topic
```
docker exec --interactive --tty kafka1  \
kafka-console-producer --bootstrap-server kafka1:19092 \
                       --topic test-topic
```

### Consume Messages from the topic
```
docker exec --interactive --tty kafka1  \
kafka-console-consumer --bootstrap-server kafka1:19092 \
                       --topic test-topic \
                       --from-beginning
```