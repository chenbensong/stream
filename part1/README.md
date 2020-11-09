Start a Spark Cluster
From the terminal: cd /home/workspace/spark/sbin

Type: ./start-master.sh

Watch for a message similar to this: Logging to /home/workspace/spark/logs/spark--org.apache.spark.deploy.master.Master-1-5a00814ba363.out

Copy the path to your log, for example: /home/workspace/sparklogs/logs/spark--org.apache.spark.deploy.master.Master-1-5a00814ba363.out

Type: cat [path to log]

Look for a message like this: Starting Spark master at spark://5a00814ba363:7077

Copy the Spark URI, for example: spark://5a00814ba363:7077

Type: ./start-slave.sh [Spark URI]

Create a hello world Spark application and submit it to the cluster
Complete the hellospark.py application (be sure to click File Save when done)

From the terminal type: cd /home/workspace/spark/bin

Type: ./spark-submit /home/workspace/hellospark.py

Watch for the output at the end for the counts

Create a Spark Streaming Dataframe with a Kafka source and write it to the console
Click the button to start Kafka and Trucking Simulation: Start Kafka
Start the spark master and spark worker
From the terminal type: /home/workspace/spark/sbin/start-master.sh
View the log and copy down the Spark URI
From the terminal type: /home/workspace/spark/sbin/start-slave.sh [Spark URI]
Complete the kafkaconsole.py python script
Submit the application to the spark cluster:
From the terminal type: /home/workspace/spark/submit-kakfaconsole.sh
Watch the terminal for the values to scroll past (it may take up to 2 minutes)
Create and query temporary spark view and write to kafka
If you just started the workspace, click the button to start Kafka and Trucking Simulation: Start Kafka
If you just started the workspace, start the spark master and spark worker
From the terminal type: /home/workspace/spark/sbin/start-master.sh
View the log and copy down the Spark URI
From the terminal type: /home/workspace/spark/sbin/start-slave.sh [Spark URI]
Complete the gear-position.py python script
Submit the application to the spark cluster:
From the terminal type: /home/workspace/spark/submit-gear-position.sh
Use the kafka-console-consumer command to watch the data you are sinking
Parse a JSON payload into separate fields for analysis
If you just started the workspace, click the button to start Kafka and Trucking Simulation: Start Kafka
If you just started the workspace, start the spark master and spark worker
From the terminal type: /home/workspace/spark/sbin/start-master.sh
View the log and copy down the Spark URI
From the terminal type: /home/workspace/spark/sbin/start-slave.sh [Spark URI]
Complete the vehicle-status.py python script
Submit the application to the spark cluster:
From the terminal type: /home/workspace/spark/submit-vehicle-status.sh
Watch the terminal for the values to scroll past (can take up to 2 minutes)
Join streaming dataframes from different sources
If you just started the workspace, click the button to start Kafka and Trucking Simulation: Start Kafka
If you just started the workspace, start the spark master and spark worker
From the terminal type: /home/workspace/spark/sbin/start-master.sh
View the log and copy down the Spark URI
From the terminal type: /home/workspace/spark/sbin/start-slave.sh [Spark URI]
Complete the vehicle-checkin.py python script
Submit the application to the spark cluster:
From the terminal type: /home/workspace/spark/submit-vehicle-checkin.sh
Watch the terminal for the values to scroll past (can take up to 2 minutes)
Write a Streaming Dataframe to Kafka
If you just started the workspace, click the button to start Kafka and Trucking Simulation: Start Kafka
If you just started the workspace, start the spark master and spark worker
From the terminal type: /home/workspace/spark/sbin/start-master.sh
View the log and copy down the Spark URI
From the terminal type: /home/workspace/spark/sbin/start-slave.sh [Spark URI]
Complete the vehicle-checkin.py python script and then change the sink from the console to a new kafka topic
Submit the application to the spark cluster:
From the terminal type: /home/workspace/spark/submit-vehicle-checkin.sh
Manually Save and Read With Redis and Kafka
If you just started the workspace, click the button to start Kafka: Start Kafka
Run the Redis CLI:
From the terminal type: /data/redis/redis-stable/src/redis-cli -a notreally
From the terminal type: keys **
You will see the list of all the Redis tables
From another terminal type /data/kafka/bin/kafka-console-consumer --bootstrap-server localhost:9092 --topic redis-server
From the first terminal type: set myKey myValue
Open the second terminal
A new JSON message will appear from the redis-server topic
The key field contains the base64 encoded name of the Redis key
The value field contains the base64 encoded value written to the key
To decode the name of the Redis key, open a third terminal, and type: echo "[encoded key]" | base64 -d
To decode the value, copy the encoded value, then from the third terminal type: echo "[encoded value]" | base64 -d
Parse Base64 With Pyspark
If you just started the workspace, click the button to start Kafka and Trucking Simulation: Start Kafka
If you just started the workspace, start the spark master and spark worker
From the terminal type: /home/workspace/spark/sbin/start-master.sh
View the log and copy down the Spark URI
From the terminal type: /home/workspace/spark/sbin/start-slave.sh [Spark URI]
Complete the payment.py python script
Submit the application to the spark cluster:
From the terminal type: /home/workspace/spark/submit-reservation-base64.sh
Watch the terminal for the values to scroll past (may take up to 2 minutes)
Sink a Subset of JSON fields with Pyspark
If you just started the workspace, click the button to start Kafka: Start Kafka
If you just started the workspace, start the spark master and spark worker
From the terminal type: /home/workspace/spark/sbin/start-master.sh
View the log and copy down the Spark URI
From the terminal type: /home/workspace/spark/sbin/start-slave.sh [Spark URI]
Complete the payment.py python script
Change the payment.py python script to add one more streaming dataframe which selects only the reservationId, and amount
Instead of sinking to the console, sink to a kafka topic
Submit the application to the spark cluster:
From the terminal type: /home/workspace/spark/submit-payment.sh
Connect to the kafka sink topic and watch the data streaming (may take up to 2 minutes)
Join Two Base64 Decoded Dataframes
If you just started the workspace, click the button to start Kafka and Trucking Simulation: Start Kafka
If you just started the workspace, start the spark master and spark worker
From the terminal type: /home/workspace/spark/sbin/start-master.sh
View the log and copy down the Spark URI
From the terminal type: /home/workspace/spark/sbin/start-slave.sh [Spark URI]
Complete the reservation-payment.py python script
Submit the application to the spark cluster:
From the terminal type: /home/workspace/spark/submit-reservation-payment.sh
Watch the terminal for the values to scroll past (may take up to 2 minutes)
