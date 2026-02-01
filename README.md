# iitjmicroservices
IITJ Microservices Virtualbox VM project

# Microservices Deployment Using VirtualBox

## 📌 Project Objective
The objective of this project is to create and configure multiple Virtual Machines (VMs) using **Oracle VirtualBox**, establish networking between them, and deploy a **microservice-based application** across the connected VMs using Python-based REST services.

---

## 🧱 Project Architecture
The project consists of **three Virtual Machines**, each assigned a specific role:

1. **User Service VM**
   - Hosts a REST API for user data
   - Runs on port **8001**

2. **Order Service VM**
   - Hosts a REST API for order data
   - Runs on port **8002**

3. **API Gateway VM**
   - Acts as a single entry point for clients
   - Routes requests to User and Order services
   - Runs on port **8000**

---

## 🌐 Network Configuration
- All VMs are connected using **Host-Only Adapter**
- Each VM has a private IP address in the `192.168.56.0/24` network
- Services communicate using internal IPs

---

## 🛠 Technologies Used
- Oracle VirtualBox
- Ubuntu 24.04 LTS
- Python 3
- HTTPServer (`http.server`)
- REST API (GET endpoints)

---

## 📁 Project Folder Structure

microservices-project/ │ ├── user_service/ │   └── service.py │ ├── order_service/ │   └── service.py │ ├── gateway/ │   └── gateway.py │ └── README.md

---

## 🚀 Microservices Details

### 👤 User Service
- Endpoint: `/users`
- Port: `8001`
- Sample Response:
```json
{
  "users": ["Sumit", "Ved"]
}

📦 Order Service
Endpoint: /orders
Port: 8002
Sample Response:

{
  "orders": ["Order-101", "Order-102"]
}

🔀 API Gateway
Routes requests to appropriate microservices
Endpoints:
/users → User Service
/orders → Order Service
Port: 8000
▶️ How to Run the Project
Step 1: Start User Service

cd user_service
python3 service.py

Step 2: Start Order Service
cd order_service
python3 service.py

Step 3: Start API Gateway
cd gateway
python3 gateway.py

🧪 Testing the Application
curl http://<GATEWAY_VM_IP>:8000/users
curl http://<GATEWAY_VM_IP>:8000/orders

Or access via browser:
http://<GATEWAY_VM_IP>:8000/users
http://<GATEWAY_VM_IP>:8000/orders


