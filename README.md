# 📊 Real-Time Analytics Pipeline with Kafka, Hive, Python, Docker & Kubernetes

This project demonstrates a **real-time data processing pipeline** using Kafka for message streaming, Hive for storage and querying, and a Streamlit dashboard for visualization — all containerized with Docker and orchestrated using Kubernetes.

---

## 🚀 Overview

This pipeline simulates real-time message production (like IoT sensor data or user activity logs), processes it via a Kafka consumer, stores key analytics in Hive, and visualizes trends in a live dashboard built with Streamlit.

---

## 🏗️ Architecture

```
┌──────────┐     ┌────────────┐     ┌────────────┐     ┌────────────┐     ┌──────────────┐
│ Producer │ ─▶─ │  Kafka      │ ─▶─ │  Consumer   │ ─▶─ │    Hive     │ ─▶─ │ Streamlit UI │
└──────────┘     └────────────┘     └────────────┘     └────────────┘     └──────────────┘
```

---

## 🔧 Tech Stack

| Layer              | Technology                        |
|--------------------|------------------------------------|
| Streaming Engine   | Apache Kafka                      |
| Data Storage       | Apache Hive                       |
| Data Processing    | Python (KafkaConsumer)            |
| Visualization      | Streamlit                         |
| Containerization   | Docker                            |
| Orchestration      | Kubernetes                        |

---

## 📁 Folder Structure

```
real-time-analytics/
├── producer/                  # Kafka message producer
├── consumer/                  # Kafka consumer (Hive ingestion)
├── dashboard/                 # Streamlit dashboard
├── hive/                      # Hive init scripts
├── Dockerfiles/               # Dockerfiles for each service
├── k8s/                       # Kubernetes manifests
├── docker-compose.yml         # For local testing
└── README.md
```

---

## 📦 Setup & Run

### 🔹 Option 1: Local (Docker Compose)

1. **Clone the repository**
   ```bash
   git clone https://github.com/<your-username>/real-time-analytics.git
   cd real-time-analytics
   ```

2. **Start containers**
   ```bash
   docker-compose up --build
   ```

3. **Access**
   - Kafdrop: [http://localhost:9000](http://localhost:9000)
   - Streamlit: [http://localhost:8501](http://localhost:8501)

---

### 🔹 Option 2: Kubernetes Deployment

1. **Apply manifests**
   ```bash
   kubectl apply -f k8s/
   ```

2. **Port-forward Streamlit**
   ```bash
   kubectl port-forward service/streamlit-service 8501:8501
   ```

3. **Port-forward Hive (if needed)**
   ```bash
   kubectl port-forward service/hive-service 10000:10000
   ```

---

## 📊 Sample Use Case

The pipeline can simulate data like:
```json
{"user_id": 1, "action": "login", "timestamp": "2025-06-17T10:00:00"}
```

It is ingested by Kafka, consumed, stored in Hive, and displayed as:
- Most active users
- Action trends over time
- Live message count

---

## 🧠 Skills Demonstrated

- Real-time stream processing with Kafka
- Building Kafka producers and consumers with Python
- Working with Hive for analytical queries
- Dockerizing and deploying microservices
- Deploying a complete stack on Kubernetes
- Building dashboards with Streamlit

---

## 📸 Screenshots

> Add screenshots of:
> - Streamlit dashboard
> - Kafdrop UI
> - Hive query results

---

## 🧪 To Do / Extensions

- Integrate Spark Streaming or Flink
- Add authentication to Streamlit
- Integrate Kafka Connect for external DBs
- Set up Grafana + Prometheus monitoring

---

## 🤝 Contributing

Contributions welcome! Please open issues or PRs for improvements.

---

## 📝 License

MIT License