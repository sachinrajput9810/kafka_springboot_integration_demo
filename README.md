# Spring Boot Kafka Tutorial with JSON Serialization

This project demonstrates how to send and receive custom Java objects (POJOs) using Apache Kafka and Spring Boot with proper JSON serialization and deserialization.

---

## 🔧 Kafka Configuration (`application.properties`)

```properties
spring.application.name=springboot-kafka-tutorial

# Kafka broker address
spring.kafka.consumer.bootstrap-servers=localhost:9092
spring.kafka.producer.bootstrap-servers=localhost:9092

# Consumer group ID
spring.kafka.consumer.group-id=myGroup

# Always read messages from the beginning
spring.kafka.consumer.auto-offset-reset=earliest

# Deserializer for Kafka keys (usually strings)
spring.kafka.consumer.key-deserializer=org.apache.kafka.common.serialization.StringDeserializer
spring.kafka.producer.key-serializer=org.apache.kafka.common.serialization.StringSerializer

# Deserialize Kafka values from JSON into POJO
spring.kafka.consumer.value-deserializer=org.springframework.kafka.support.serializer.JsonDeserializer

# Serialize POJO values to JSON for Kafka
spring.kafka.producer.value-serializer=org.springframework.kafka.support.serializer.JsonSerializer

# Allow Spring Kafka to deserialize all packages (dev only)
spring.kafka.consumer.properties.spring.json.trusted.packages=*
