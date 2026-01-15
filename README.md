# 🚀 Lyftr AI — Containerized Webhook API

A production-grade **FastAPI** service that ingests WhatsApp-like webhooks **exactly once**, verifies **HMAC signatures**, persists messages in **SQLite**, and exposes **query, analytics, health, and metrics** endpoints — all fully containerized with **Docker**.

Built to meet **Lyftr AI’s backend engineering evaluation criteria**.

---

## ✨ Features

### 🔐 Secure Webhook Ingestion
- HMAC-SHA256 signature verification  
- Rejects unsigned or tampered requests  

### ♻️ Idempotent Message Processing
- `message_id` enforced as primary key  
- Same message can be sent multiple times without duplication  

### 🗄️ SQLite Persistence
- Database stored on Docker volume  
- File path: `/data/app.db`  

### 🔍 Searchable & Paginated Message API
- Filter by sender  
- Filter by timestamp  
- Free-text search  

### 📊 Analytics Endpoint
- Total messages  
- Unique senders  
- Top senders  
- First & last message timestamps  

### ❤️ Health Probes
- `/health/live`  
- `/health/ready`  

### 📈 Prometheus Metrics
- HTTP request counters  
- Webhook processing counters  
- Request latency histogram  

### 🧾 Structured JSON Logs
- One JSON log per request  
- Includes:
  - `request_id`
  - `latency_ms`
  - `status`
  - webhook `result`  

### 🐳 Fully Dockerized
- Zero local setup  
- Runs with Docker Compose  

---

## 🛠️ Tech Stack

- **API** → FastAPI  
- **Database** → SQLite  
- **Metrics** → Prometheus client  
- **Logging** → JSON structured logs  
- **Containerization** → Docker & Docker Compose  

---

## ▶️ How to Run

### 1️⃣ Prerequisites
Make sure you have:
- **Docker Desktop** installed and running

---

### 2️⃣ Start the Service

From the project root:

```bash
docker compose up --build
