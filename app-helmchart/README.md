# Microservices CRUD Application

This project is a **3-tier microservices-based CRUD application** built using **Node.js** and **MySQL**.

## Architecture Overview

The application consists of:

* **Frontend Service** (Node.js UI)
* **API Service** (Backend CRUD API)
* **Options Service** (Backend supporting service)
* **MySQL Database**

### Flow

```
Frontend → API Service → MySQL
                ↓
          Options Service → MySQL
```

* Frontend communicates with API Service.
* API Service communicates with both MySQL and Options Service.
* Options Service communicates with MySQL.

---

## Services

### 1. Frontend Service

Responsible for UI and calling backend APIs.

**Default Environment Variables**

```yaml
env:
  - name: API_URL
    value: "http://api-service:80"
```

---

### 2. Backend API Service

Main CRUD backend service.

**Default Environment Variables**

```yaml
env:
  - name: DB_HOST
    value: "mysql"
  - name: DB_USER
    value: "root"
  - name: DB_PASSWORD
    value: "publicP15@"
  - name: DB_NAME
    value: "microservice_db"
  - name: PORT
    value: "3001"
  - name: OPTIONS_SERVICE_URL
    value: "http://options-service:80"
```

---

### 3. Backend Options Service

Supporting backend service for options-related operations.

**Default Environment Variables**

```yaml
env:
  - name: DB_HOST
    value: "mysql"
  - name: DB_USER
    value: "root"
  - name: DB_PASSWORD
    value: "publicP15@"
  - name: DB_NAME
    value: "microservice_db"
  - name: PORT
    value: "3002"
```

---

## Database

* **MySQL**
* Database Name: `microservice_db`
* Shared between API and Options services.

---

## Notes

* This project follows a **microservices architecture**.
* Designed to work in containerized environments like Docker / Kubernetes.

---

