# Client–Server Architecture

## What is it?
Client–Server Architecture is a model where a client sends a request to a server, the server processes the request, and sends a response back to the client.

---

## Why needed?
- To separate frontend (UI) from backend logic
- To support multiple users at the same time
- To centralize business logic and data
- To make systems scalable and maintainable

---

## How it works?
1. Client sends a request (HTTP/HTTPS)
2. Server receives the request
3. Server processes business logic
4. Server interacts with database (if needed)
5. Server sends response back to client

Flow:
Client → Request → Server → Process → Database → Response → Client

---

## Client Examples
- Web browsers (Chrome, Firefox)
- Web apps (React, Angular)
- Mobile applications

---

## Server Examples
- Backend frameworks (Spring Boot, Node.js)
- Web servers (Apache, Nginx)
- Databases (MySQL, PostgreSQL)

---

## Types of Client–Server Architecture

### 1. Two-Tier Architecture
Client directly communicates with the database.

Example:
Desktop Application → Database

Used in:
- Small systems
- Desktop applications

---

### 2. Three-Tier Architecture
Client communicates with an application server, which then talks to the database.

Example:
Client → Application Server → Database  
React → Spring Boot → MySQL

Benefits:
- Better separation of concerns
- More secure than two-tier

---

### 3. N-Tier Architecture
System is divided into multiple layers.

Example:
Client → API Gateway → Services → Database

Used in:
- Microservices
- Large-scale systems

---

## Real-world Example
A browser sends a request to fetch user profile data.  
The backend API processes the request, fetches data from database, and returns the response.

---

## Interview Ready Explanation
"Client–Server architecture separates the client interface from backend services. Clients send requests, servers process them and return responses. This helps in scalability, maintainability, and supporting multiple users."
