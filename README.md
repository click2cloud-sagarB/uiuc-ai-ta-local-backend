# 🧠 UIUC AI Backend

The **UIUC AI Backend** powers land data processing, machine learning inference, and message-based job orchestration using **RabbitMQ**, **PostgreSQL**, and **Python** workers.

---

## 📦 Prerequisites

Before you begin, ensure the following are installed on your system:

- [Python 3.10+](https://www.python.org/downloads/)
- [pip](https://pip.pypa.io/en/stable/)
- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/)
- (Optional) [Miniconda](https://docs.conda.io/en/latest/miniconda.html) for environment management

---

## 🚀 Setup Instructions

Follow these steps to install dependencies, run migrations, and start the worker service.

### 1️⃣ Install Python Dependencies

```bash
pip install -r requirements.txt
This installs all backend dependencies, including database connectors, RabbitMQ client libraries, and ML components.
```
### 2️⃣ Navigate to the Backend Directory

```bash
Copy code
cd ai_ta_backend
```
### 3️⃣ Make the Startup Script Executable

```bash
Copy code
chmod +x startup_script.sh
```

### 4️⃣ Run the Startup Script

```bash
Copy code
./startup_script.sh
This script initializes environment variables and sets up backend components required for your app to run.
```

### 5️⃣ Run Database Migrations

```bash
Copy code
python table_migration.py
This creates or updates your PostgreSQL database tables.
```
### 6️⃣ Start RabbitMQ and Worker Containers
##### Move into the RabbitMQ directory:

```bash
Copy code
cd ai_ta_backend/rabbitmq
```
##### Then build and start the containers:
```bash
Copy code
docker-compose up -d --build
```
### 7️⃣ Monitor Worker Logs
##### To view logs and ensure the worker connects properly:

```bash
Copy code
docker-compose logs -f worker
```