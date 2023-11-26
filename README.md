# kafka-docker
Running Kafka locally with Docker
# Once we have created the docker-compose file, we can execute it using the following command:
# start kafka cluster
$ docker-compose up -d
# verify kafka cluster
$ docker-compose ps
# Create a Kafka Topic
$ docker-compose exec kafka kafka-topics.sh --create --topic cdc-topic --partitions 1 --replication-factor 1 --bootstrap-server kafka:9092
# Create events
$ docker-compose exec kafka kafka-console-producer.sh --topic cdc-topic --broker-list kafka:9092
# Read events
$ docker-compose exec kafka kafka-console-consumer.sh --topic cdc-topic --from-beginning --bootstrap-server kafka:9092
