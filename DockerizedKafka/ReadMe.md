This Project is about creating a docker image for Kafka Setup.

Now to Use kafka, you dont need to install Kafka manually. Also You dont need to create any producer or consumer manually.

First Use the docker-compose.yaml file

# docker-compose up -d

This would do everything. 
- It would install and start zookeeper.
- It would install and start Kafka Broker.
- It would install and start Kafka Console Producer.
- It would install and start Kafka Console Consumer.

# Send Message Through Kafka Producer
Open another terminal, then attach to the kafka-producer container to produce messages

        docker-compose exec kafka-producer /bin/sh
        kafka-console-producer --broker-list kafka:9092 --topic test-topic

You can now type messages into the console, and they’ll be sent to test-topic.

# To see Message on Consumer

Approach 1 :: You can either check logs of consumer.

Approach 2 :: You can open a terminal for consumer also and see there as well.

           docker-compose exec kafka-consumer /bin/sh
           kafka-console-consumer --bootstrap-server kafka:9092 --topic test-topic --from-beginning



