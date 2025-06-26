# DevOps Assignment – NGINX Reverse Proxy + Docker Compose

This project sets up a containerized environment using **Docker Compose** to run:
- A **Go-based service** (Service 1)
- A **Flask-based Python service** (Service 2)
- An **NGINX reverse proxy** to route traffic to the appropriate service based on path prefixes.

---

## 🚀 Setup Instructions

1. Clone the repository:
   ```bash
   git clone https://github.com/Hemalatha-9302/devops-assignment-dpdzero.git
   cd devops-assignment-dpdzero
## Run the system with:

docker-compose up --build

## 🔍 Test the Services
Once the system is running, you can test the endpoints in your browser or via curl:

# Go Service (Service 1)
http://localhost/service1/hello

http://localhost/service1/ping

# Python Service (Service 2)
http://localhost/service2/hello

http://localhost/service2/ping


## 🧱 Project Structure

.
├── docker-compose.yml
├── nginx
│   ├── nginx.conf
│   └── Dockerfile
├── service_1
│   ├── Dockerfile
│   └── main.go
├── service_2
│   ├── Dockerfile
│   └── app.py
└── README.md

## 🔁 Routing with NGINX
The NGINX reverse proxy container handles routing based on URL path prefixes:

/service1 → forwards to Service 1 (Go app on port 8001)

/service2 → forwards to Service 2 (Flask app on port 5000)

It also logs incoming requests with:

Timestamp

Method & path

Response status

## ✅ Healthchecks
Each service includes a Docker healthcheck to ensure it's alive and ready before routing:

Go Service: GET /ping on port 8001

Flask Service: GET /ping on port 5000

## 💡 Bonus Features Implemented
✅ Healthchecks

✅ Logging via NGINX

✅ Modular, clean Docker setup

✅ Internal service-to-service communication using Docker networking


