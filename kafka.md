# KAFAKA 

# kafka-list-topic.sh

  bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test
  //副本要在另一个broker

  bin/kafka-topics.sh --zookeeper localhost:2181 --list

  bin/kafka-topics.sh --describe --zookeeper localhost:2181 --topic test

  delete、alert... VIEW DOC.
  
# consumer

  bin/kafka-console-consumer.sh --zookeeper localhost:2181 --topic test --from-beginning
  
  bin/kafka-run-class.sh kafka.tools.SimpleConsumerShell  --broker-list localhost:9092 --pic test --partition 0 --print-offsets
  //--offset 99
  
  bin/kafka-run-class.sh kafka.tools.GetOffsetShell --broker-list localhost:9092 --topic test --time -1
  
  bin/kafka-run-class.sh kafka.tools.ConsumerOffsetChecker --zookeeper localhost:2181 --topic test --group test
  
  https://cwiki.apache.org/confluence/display/KAFKA/System+Tools#SystemTools-ExportZookeeperOffsets
