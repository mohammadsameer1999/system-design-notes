# Load Balancer

![Load Balancer Architecture](./images/load-balancer.png)

## What is it?
A Load Balancer is a component that distributes incoming client requests across multiple backend servers.

---

## Why needed?
- A single server cannot handle high traffic
- To avoid system downtime when a server crashes
- To improve performance and availability

---

## How it works?
1. Client sends request
2. Load Balancer receives the request
3. Load Balancer checks backend server health
4. Request is routed to a healthy server
5. Server processes request and sends response

### Flow
Client → Load Balancer → Backend Server → Response

---

## Health Check
- Load balancer continuously checks server health
- If a server is unhealthy, traffic is not sent to it
- Traffic is routed to healthy servers only

---

## Benefits
- Handles high traffic
- Prevents system failure
- Improves scalability and reliability

---

## Real-world Example
An e-commerce website uses a load balancer to distribute user requests across multiple backend servers during high traffic sales.

---

## Interview Ready Explanation
"Load balancer distributes traffic across multiple servers and performs health checks to ensure high availability and fault tolerance."
