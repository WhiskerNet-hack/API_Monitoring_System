# 🧠 AI-Powered API Monitoring and Anomaly Detection System

An AI-driven platform to monitor, analyze, and predict anomalies in high-frequency API call environments, built for distributed infrastructures (on-premises, cloud, and multi-cloud). This system leverages log streaming, anomaly detection, real-time alerting, and dashboard visualization — all containerized with Docker.

---

## 🚀 Features

- ✅ Real-time API performance monitoring (latency, errors)
- ✅ Log streaming via Kafka
- ✅ AI-based anomaly detection (using Isolation Forest)
- ✅ Alerting system via Slack & AWS SNS
- ✅ Scalable microservices architecture using Docker
- ✅ MongoDB for flexible log storage
- ✅ Optional Kibana dashboard or React-based custom UI

---

## 🧰 Tech Stack

| Component              | Tool/Tech           |
|------------------------|---------------------|
| API Simulation         | FastAPI             |
| Log Streaming          | Kafka + Zookeeper   |
| AI/Anomaly Detection   | Python + Scikit-learn |
| Database               | MongoDB (NoSQL)     |
| Alert System           | AWS SNS, Slack      |
| Containerization       | Docker + Docker Compose |
| Optional Dashboard     | Kibana / React + Recharts |

---

## 🧱 Architecture Overview

```
FastAPI → OpenTelemetry Logs
     ↓
  Kafka (log streaming)
     ↓
Python Anomaly Detector (Isolation Forest)
     ↓              ↓
MongoDB       Slack / SNS Alerts
     ↓
(Kibana Dashboard)
```

---

## 🐳 How to Run the Project (Using Docker)

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/your-org/anomaly-detection-system.git
cd anomaly-detection-system
```

### 2️⃣ Install Docker & Docker Compose

- Download Docker: https://www.docker.com/products/docker-desktop
- Make sure `docker` and `docker-compose` work:

```bash
docker --version
docker-compose --version
```

### 3️⃣ Start All Services

```bash
docker-compose up --build
```

This will:
- Spin up FastAPI (API simulator)
- Start Kafka + Zookeeper (log streaming)
- Run the Python anomaly detector
- Launch MongoDB for log storage

### 4️⃣ Test the APIs

Use [Postman](https://www.postman.com/) or `curl`:

```bash
curl http://localhost:8000/test-api
```

This will send a sample log to Kafka, where it is:
- Stored in MongoDB
- Analyzed for anomalies
- Alerted via Slack/SNS if needed

---

## 🛠️ Configuration

### 🔐 Slack Alerting

Set your Slack Webhook URL in `alert/slack_alert.py`:

```python
webhook_url = "https://hooks.slack.com/services/..."
```

### 📡 AWS SNS Alerting

In `alert/sns_alert.py`, configure your SNS topic ARN and AWS credentials.

---

## 📦 Folder Structure

```
├── fastapi/                 # API simulator
├── anomaly_detector/       # Python anomaly detection service
├── alert/                  # Slack / SNS integration
├── docker-compose.yml      # Container orchestration file
├── mongo/                  # MongoDB setup
├── dashboard/              # Optional dashboard (React/Kibana)
├── README.md               # Project documentation
```

---

## 👨‍💻 Contributors

- **Rohit Kumar** – [rohitkumar620200@gmail.com](mailto:rohitkumar620200@gmail.com)
- **Samriddhi Dubey** – [samriddhidubey2810@gmail.com](mailto:samriddhidubey2810@gmail.com)
- **Vaibhav Verma**

---

## 📬 Want to Help?

Feel free to fork, improve, or report issues. Contributions are welcome!

---

## 📄 License

This project is licensed under MIT License.
