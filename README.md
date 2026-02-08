# CST8915 Lab 1: Algonquin Pet Store on Azure VM

**Student Name**: Xinyi Zhao    
**Student ID**: 040953633    
**Course**: CST8915 Full-stack Cloud-native Development    
**Semester**: Winter 2026    

---

## Demo Video

🎥 https://youtu.be/y7T8f8sv9xk

---

## Technical Explanations

### Order Service (Node.js)

The Order Service is responsible for receiving placed order requests from the Store Front and processing customer orders. It exposes a REST API which is running on prot 3000 that accepts order data. It performs basic validation and then forwards the order to RabbitMQ. 
Using Node.js is beneficial because it handles HTTP requests efficiently, and it is suitable for lightweight microservices. 
In a microservices architecture, this service acts as a gateway between the client and the server. It happens via HTTP from the Store Front to Order Service, and via AMQP publishing from Order Service to RabbitMQ. 

### Product Service (Rust)

The Product Service manages the product and offers endpoints for retrieving product listings and details. It runs as a REST API on port 3030 and is called by the Store Front to load product data. It is mainly responsible for serving consistent product information. 
This service is implemented in Rust, which is good for high-performance APIs and safe concurrency. Product Service is a backend component for product data; the service remains independent. 

### Store Front (Vue.js)

The Store Front is the user interface built with Vue.js, which runs on port 8080. It supports user interaction with this application, as it is a client that calls backend services via API request. 
In the microservices architecture, the Store Front implement user interactions and integrates Product Service(3030) and submits orders to the Order Service(3000). 

---

## Challenges and Learnings (Optional)

The main challenge was troubleshooting RabbitMQ connectivity on the Azure VM due to service startup order and network port configuration.

---

## Acknowledgments

ChatGPT assisted with troubleshooting RabbitMQ installation and revising non-native and unnatural expressions in the documentation.

