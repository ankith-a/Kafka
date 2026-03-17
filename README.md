# 🧩 Kafka Producer & Consumer Example — `gitnivedhj-topic`

This repository demonstrates a simple **Apache Kafka** setup showing how messages are sent and received between a **Producer** and **Consumer** using command-line tools on **Windows**.

---

## ⚙️ Prerequisites
- Apache Kafka (version 3.8.0 or similar)   
- Java installed and configured (`JAVA_HOME` set)
- Kafka extracted to: `D:\kafka_2.13-3.8.0`

---

## 🚀 Steps to Run

### 1️⃣ Start ZooKeeper
```powershell
cd D:\kafka_2.13-3.8.0\bin\windows
.\zookeeper-server-start.bat ..\..\config\zookeeper.properties
```
### 2️⃣ Start Kafka Broker
```powershell new tab 
cd D:\kafka_2.13-3.8.0\bin\windows
.\kafka-server-start.bat ..\..\config\server.properties
```
### 3️⃣ Create a Topic
```powershell new tab
cd D:\kafka_2.13-3.8.0\bin\windows
.\kafka-topics.bat --create --topic gitnivedhj-topic --bootstrap-server localhost:9092 --partitions 1 --replication-factor 1

✅ Confirm topic creation:
.\kafka-topics.bat --list --bootstrap-server localhost:9092
```
### 4️⃣ Start a Producer
```
.\kafka-console-producer.bat --topic gitnivedhj-topic --bootstrap-server localhost:9092
```
### 5️⃣ Start a Consumer (in a new PowerShell window)
```
.\kafka-console-consumer.bat --topic gitnivedhj-topic --from-beginning --bootstrap-server localhost:9092

```
Output Example

Producer Window:

Hello Kafka!
This is Ankith testing producer.

Consumer Window:

Hello Kafka!
This is Ankith testing producer.

### 🪄 Summary

This example shows the core concept of Kafka messaging — how producers send messages to a topic and consumers receive them, all through the command line.
