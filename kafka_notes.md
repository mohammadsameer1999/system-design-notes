# Kafka Quick Reference Notes

## 1. Pub-Sub Model

* **Definition:** Producer publishes messages, consumer subscribes.
* **Kafka mapping:**

  * Producer → Sends message
  * Topic → Channel / Category
  * Consumer → Receives message
* **Analogy:** News channel → Cricket news → Fan

## 2. Topic & Partition

* **Topic:** Logical message category (e.g., orders, payments)
* **Partition:** Splits topic → enables parallelism, maintains order per partition
* **Single Partition Limitation:** Only 1 consumer reads → throughput bottleneck
* **Key Rule:** Ordering guaranteed **per partition**

## 3. Producer & Consumer

* **Producer:** Sends messages to topic
* **Consumer:** Reads messages from topic partitions
* **Offset:** Last read position
* **Consumer Group:** Multiple consumers sharing partitions

  * Same group → each partition → 1 consumer
  * Different groups → each group gets all messages

## 4. Kafka Flow

```
Producer → Topic → Partition → Consumer → Offset Commit
```

## 5. Scenarios / Tips

* **Consumers > Partitions:** Extra consumers idle
* **Single Partition:** Throughput limited, scaling needs more partitions
* **Crash Handling:** Use offsets & replication
* **Same key messages:** Use message key → same partition

## 6. Delivery Semantics

* **At-least-once:** May duplicate
* **At-most-once:** Possible loss
* **Exactly-once:** No duplicates, no loss

## 7. Learning Tips

* 3-Pass video method (Listen → Diagram → Predict)
* Scenario-based thinking (What if partition = 1?)
* Explain to someone / draw diagrams
* Focus on concepts before code

## 8. Scenario-Based Questions & Answers

### Q1: Why are partitions important in Kafka?

**A:** Partitions allow parallel processing of messages, improve throughput, and help distribute load across consumers.

### Q2: What happens if consumers > partitions in a consumer group?

**A:** Extra consumers remain idle. Only one consumer per partition reads messages.

### Q3: How do you handle multiple services consuming the same topic?

**A:** Use separate consumer groups for each service so each gets all messages independently.

### Q4: What if a consumer crashes mid-processing?

**A:** Kafka uses offsets. Another consumer in the group can continue from the last committed offset.

### Q5: How to maintain order for messages with same key?

**A:** Use the message key when producing so all messages with the same key go to the same partition.

### Q6: What are the delivery guarantees in Kafka?

**A:**

* At-least-once → may duplicate messages
* At-most-once → possible loss
* Exactly-once → no duplicates, no loss

### Q7: Single partition topic limitation?

**A:** Only one consumer can read at a time, limiting throughput. Scaling requires multiple partitions.

### Q8: How to scale Kafka under high traffic?

**A:** Increase number of partitions, replicate data, and use multiple consumer groups for different services.

### Q9: Ordering guarantee?

**A:** Ordering is guaranteed only within a single partition, not across partitions.

### Q10: Producer crash handling?

**A:** Ensure data is replicated and use idempotent producers to avoid duplication during retries.
