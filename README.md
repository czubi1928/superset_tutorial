# Apache Superset Docker Setup

This repository contains a lightweight Docker-based setup for running **[Apache Superset](https://superset.apache.org/)** — a modern data exploration and visualization platform.  
It allows you to quickly spin up a Superset instance for analytics, dashboarding, and data visualization.

---

## 🧱 Project Structure

```
.
├── docker/
│   └── superset/
│       └── Dockerfile
│       └── superset-init.sh
│       └── superset_config.py
├── data/
│   └── (persistent Superset data)
├── docker-compose.yaml
```

- **docker/superset/** — Contains the custom Dockerfile used to build the Superset image.  
- **data/** — Volume-mounted directory for storing Superset metadata and configuration persistently.  
- **docker-compose.yaml** — Defines and configures the Superset container service.

---

## 🚀 Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/czubi1928/superset_tutorial.git
cd superset_tutorial
````

### 2. Build and start Superset

```bash
docker-compose up -d
```

### 3. Access Superset

After the container starts, open your browser and go to:
👉 [http://localhost:8088](http://localhost:8088)

Use the following credentials (defined in the environment section of the `docker-compose.yaml`):

```
Username: superset
Password: superset
Email: superset@superset.com
```

---

## ⚙️ Configuration

You can modify Superset configuration and environment variables in:

```yaml
environment:
  - ADMIN_USERNAME=superset
  - ADMIN_EMAIL=superset@superset.com
  - ADMIN_PASSWORD=superset
```

To customize:

* Change the admin credentials.
* Map additional ports.
* Extend or modify the `Dockerfile` in `docker/superset/`.

---

## 📁 Volumes

Data is persisted in the `./data` directory, which is mounted into the container:

```
volumes:
  - ./data:/app/data
```

This ensures that Superset metadata (dashboards, charts, etc.) remains available after container restarts.

---

## 🧹 Stopping and Cleaning Up

To stop the running containers:

```bash
docker-compose down
```

To remove all data (optional):

```bash
docker-compose down -v
```

---

## 🛠️ Tech Stack

* **Apache Superset** – Data visualization & dashboarding tool
* **Docker & Docker Compose** – Containerization and orchestration
* **Python** (via Superset) – Backend
* **SQLite/Postgres (optional)** – Metadata database

---

## 🧠 Notes

* This setup is designed for **local development or learning purposes**.
* For production use, consider external databases and persistent storage solutions.

---

## 🧾 License

This repository is for **learning purposes only** and follows the licensing terms of Apache Superset.

---

### ✍️ Author

Created by [Your Name](https://github.com/<your-username>)
Feel free to fork and customize this setup for your own projects.

