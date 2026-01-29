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
