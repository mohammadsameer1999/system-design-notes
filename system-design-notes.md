# System Design – Basics

## What is System Design?
System Design is the process of designing a software system that is:
- Scalable
- Maintainable
- Reliable
- User-friendly

It focuses on how different components of a system work together and how the system behaves when users and traffic grow.

---

## Why System Design is Important?
- To handle increasing users (scalability)
- To avoid single point of failure
- To make future changes easy
- To ensure high availability and performance

---

## Scalability
Scalability means the ability of a system to handle increased load by adding resources.

There are two types of scaling:
1. Horizontal Scaling
2. Vertical Scaling

---

## 1. Horizontal Scaling
Horizontal scaling means increasing the number of servers when users increase.

### Example:
- 1 server handles 10,000 users
- 3 servers handle 30,000 users

### Benefits:
- High availability
- Fault tolerant (if one server fails, others work)
- Used in large-scale systems

### Real-life example:
Adding more billing counters in a mall when crowd increases.

---

## 2. Vertical Scaling
Vertical scaling means increasing the power of a single server by adding:
- More RAM
- Better CPU
- More storage

### Example:
- Upgrade server from 4GB RAM to 16GB RAM

### Limitations:
- Hardware limit exists
- Single point of failure
- Downtime during upgrade

### Used in:
- Small applications
- Early-stage systems

---

## Horizontal vs Vertical Scaling

| Feature | Horizontal Scaling | Vertical Scaling |
|------|------------------|----------------|
| Servers | Multiple | Single |
| Scalability | High | Limited |
| Fault Tolerance | Yes | No |
| Cost | Medium | High |
| Usage | Large systems | Small systems |

---

## Interview Ready Explanation
"System Design is about designing scalable and reliable systems.  
We can scale systems horizontally by adding more servers or vertically by upgrading server resources."

---

## Key Takeaways
- System Design focuses on structure and scalability
- Horizontal scaling is preferred for large systems
- Vertical scaling has limits
- Reliability and availability are core goals
