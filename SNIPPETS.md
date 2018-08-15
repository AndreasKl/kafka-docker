#### Start the environment

docker-compose -f docker-compose-single-broker.yml up

docker-compose -f docker-compose-single-broker.yml build

docker-compose -f docker-compose-single-broker.yml down


#### Produce message from console

./kafka-console-producer.sh --topic myTopic --broker-list 127.0.0.1:9092

./kafkacat -P -b 127.0.0.1:9092 -t myTopic

for i in {1..10}; do  echo "Hallo $i" | ./kafkacat -P -b 127.0.0.1:9092 -t rewe-topic; done

#### Topic status

./kafkacat -L -b 127.0.0.1:9092 -t myTopic
