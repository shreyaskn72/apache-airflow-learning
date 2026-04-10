If you want to go with theoretical approach, you can refer [theory.md](theory.md) file.


Below is a **lab-driven Table of Contents** (progressive, project-style 👇)

---

# 🧪 Apache Airflow – Hands-On Lab Roadmap

---

## 🧠 Phase 0: Foundations (Learn Just Enough to Start)

### 0.1 What is Apache Airflow?

* What problem Airflow solves
* Workflow orchestration vs scripting
* Real-world use cases (ETL, APIs, scheduling)

---

### 0.2 Why Airflow (vs cron, scripts)?

**Limitations of:**
* Cron jobs
* Python scripts

**Benefits of Airflow:**
* Dependency management
* Retry & monitoring
* UI visibility

👉 Mental model:
* Cron = "run this at time X"
* Airflow = "run this workflow with dependencies, retries, visibility"

---

### 0.3 Core Concepts (Very Important)

Understand these before writing any code:

* **DAG** (Directed Acyclic Graph)
  * Workflow definition
* **Tasks**
  * Individual units of work
* **Operators**
  * How tasks are executed
* **Scheduling**
  * When DAG runs

👉 Think:
* DAG = pipeline
* Task = step
* Operator = implementation

---

### 0.4 Airflow Architecture (High Level)

* Webserver → UI
* Scheduler → decides what runs
* Executor → runs tasks
* Metadata DB → stores state

👉 You don't need internals yet — just roles

---

### 0.5 Installation & Setup Overview

Options:
* `pip install` (quick but messy)
* Docker (recommended ✅)

---

### 0.6 Local Setup (You Will Do This in Lab 1)

Airflow with:
* SQLite (dev)
* Later: PostgreSQL/MySQL (prod)

---

### 0.7 Airflow UI Walkthrough

* DAGs list
* Graph view
* Logs
* Trigger DAG

---

### 0.8 CLI Basics

* `airflow dags list`
* `airflow tasks list`
* `airflow dags trigger`

---

## 🔰 Phase 1: Environment & First DAG (Setup by Doing)

### Lab 1: Run Airflow Locally with Docker

* Install Docker
* Run Airflow using docker-compose
* Access UI
* Trigger example DAG

👉 Outcome: You have Airflow running locally

---

### Lab 2: Write Your First DAG

* Create a simple DAG file
* Use `PythonOperator`
* Print logs

👉 Build:

* “Hello World” pipeline

---

### Lab 3: Task Dependencies

* Create 3 tasks
* Chain them using `>>`

👉 Build:

* Simple ETL flow (Extract → Transform → Load simulation)

---

## ⚙️ Phase 2: Core Building Blocks

### Lab 4: Working with Scheduling

* Add cron schedule
* Experiment with:

  * `@daily`
  * `@hourly`
* Turn catchup ON/OFF

👉 Build:

* Daily job with backfill

---

### Lab 5: Real API Integration

* Call a public API (e.g., weather, crypto)
* Parse JSON
* Store result in file

👉 Build:

* API ingestion pipeline

---

### Lab 6: XCom Data Passing

* Pass data between tasks
* Use `xcom_push` and `xcom_pull`

👉 Build:

* Pipeline where one task feeds another

---

### Lab 7: Variables & Connections

* Store API key in Variables
* Create Connection (DB/API)

👉 Build:

* Secure API pipeline

---

## 🗄️ Phase 3: Real Data Pipelines

### Lab 8: Database Integration

* Connect to:

  * MySQL or PostgreSQL
* Insert data from DAG

👉 Build:

* API → DB pipeline

---

### Lab 9: File Processing Pipeline

* Read CSV
* Transform data (Python)
* Write processed output

👉 Build:

* Batch data processing pipeline

---

### Lab 10: Sensors (Waiting Systems)

* Use FileSensor / TimeSensor

👉 Build:

* Wait for file → then process it

---

## 🔁 Phase 4: Reliability & Production Thinking

### Lab 11: Retry & Failure Handling

* Add retries
* Force task failure
* Observe logs

👉 Build:

* Fault-tolerant pipeline

---

### Lab 12: Alerts & Monitoring

* Enable email/log alerts
* Explore UI deeply

👉 Build:

* Observable pipeline

---

### Lab 13: Parallel Tasks

* Run tasks in parallel

👉 Build:

* Multi-branch DAG

---

### Lab 14: Branching Logic

* Use `BranchPythonOperator`

👉 Build:

* Conditional workflows

---

## 🚀 Phase 5: Advanced Workflows

### Lab 15: Dynamic DAGs

* Generate DAGs dynamically

👉 Build:

* Multi-client pipelines

---

### Lab 16: Task Groups

* Group tasks logically

👉 Build:

* Clean, production-style DAG

---

### Lab 17: Custom Operator

* Create your own operator

👉 Build:

* Reusable task component

---

## ☁️ Phase 6: Scaling & Kubernetes (Very Important for You)

### Lab 18: Run Airflow with CeleryExecutor

* Add:

  * Redis / RabbitMQ
  * Multiple workers

👉 Build:

* Distributed execution system

---

### Lab 19: Airflow on Kubernetes

* Deploy using Helm
* Use KubernetesExecutor

👉 Build:

* Cloud-native Airflow

---

### Lab 20: Run Tasks as Pods

* Each task runs as separate pod

👉 Build:

* Scalable task execution

---

## 🔄 Phase 7: CI/CD & Deployment

### Lab 21: DAG Deployment via Git

* Store DAGs in GitHub
* Auto-sync DAGs

👉 Build:

* Version-controlled workflows

---

### Lab 22: CI/CD Pipeline for Airflow

* Validate DAGs before deploy

👉 Build:

* Production-ready pipeline

---

## 🧠 Phase 8: Capstone Projects (Real Industry Level)

### 💼 Project 1: API → DB Pipeline

* Fetch API data daily
* Store in DB
* Retry on failure

---

### 💼 Project 2: ETL Pipeline

* Read CSV → Transform → Load DB
* Add logging + monitoring

---

### 💼 Project 3: Microservices Orchestration

* Trigger:

  * Flask APIs
  * Background jobs

---

### 💼 Project 4 (🔥 Recommended for someone with microservices background): Airflow on Kubernetes

Full System:

* Airflow + Kubernetes
* API ingestion
* Celery workers
* DB storage
* Scheduled + event-driven

---

# 🧭 How to Use This

Don’t just “complete labs” — treat each like production:

* Add logging
* Handle failures
* Keep code clean
* Think idempotency

---

# ⚡ Pro Tip (Important)

Given your background (Flask + Kubernetes):

👉 Focus heavily on:

* Lab 5 (API pipelines)
* Lab 8 (DB pipelines)
* Lab 18–20 (Scaling + Kubernetes)

That’s where your **career ROI is highest**

---