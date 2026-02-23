# 🐳 Docker Compose – Quick Guide

* Docker Compose is used to define and manage multi-container Docker applications using a **docker-compose.yml** file.

## 📌 What is Docker Compose?

* Docker Compose allows you to:
    1. Define multiple services in a single YAML file
    2. Start all containers with one command
    3. Create networks automatically
    4. Manage volumes easily
    5. Simplify microservices deployments

---

## 🚀 Common Docker Compose Commands

* Start Services: ```docker compose up -d```
    1. Creates and starts containers
    2. Runs in detached mode (background)

* Start & Rebuild: ```docker compose up -d --build```
    - Rebuilds image before starting

* View Running Services: ```docker compose ps```

* View Logs: ```docker compose logs```
    - Follow logs in real time: ```docker compose logs -f```

* Stop Services: ```docker compose down```
    - Stops and removes:
        1. Containers
        2. Networks
        3. Default volumes

* Stop Without Removing: ```docker compose stop```

* Remove Everything (Careful ⚠️): ```docker compose down -v```
    - Removes containers + volumes.

---

## Port Mapping

```yaml
ports:
  - "8083:80"
``` 
1. Host → 8083 , Container → 80

2. Access application: http://<server-ip>:8083

---

## ⚠️ Common Error: Port Already Allocated

* Error: Bind for 0.0.0.0:8083 failed: port is already allocated

* Cause: Another container or process is already using port 8083

* Check: ```docker ps```

* Fix:
    1. Stop the existing container OR
    2. Change host port in compose file

---

## 🧠 Interview Points

1. docker compose up → Starts containers in foreground

2. docker compose up -d → Starts in background

3. docker compose down → Stops and removes containers

4. Automatically creates default network

5. Easier than running multiple docker run commands





