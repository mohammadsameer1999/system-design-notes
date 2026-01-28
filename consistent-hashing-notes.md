# Hashing & Consistent Hashing – System Design Notes

---

## 1. What is Hashing?
Hashing is a technique used to convert an input key into a fixed-size numerical value using a hash function.  
The generated value is used to quickly locate data in a data structure or distributed system.

---

## 2. Why is Hashing Used?
Hashing is used to:
- Achieve fast data access (O(1) average time)
- Distribute data uniformly
- Improve scalability in distributed systems
- Enable efficient caching and load balancing
- Secure sensitive data such as passwords

---

## 3. Basic Hashing Formula
hashValue = hash(key)
index = hash(key) % N

Where `N` is the number of servers or buckets.

---

## 4. Problem with Traditional (Modulo) Hashing
When using modulo hashing:
serverIndex = hash(key) % N

### Issues:
- Adding or removing a server changes `N`
- Almost all keys are remapped
- Causes cache misses and session loss
- Poor scalability in distributed systems

---

## 5. What is Consistent Hashing?
Consistent Hashing is a distributed hashing technique where:
- Both **servers** and **keys** are placed on a logical **hash ring**
- A key is assigned to the **next clockwise server** on the ring

This approach minimizes key movement when servers scale up or down.

---

## 6. Why Consistent Hashing is Needed?
Consistent Hashing is used to:
- Minimize key redistribution during scaling
- Preserve cache and session data
- Improve fault tolerance
- Support horizontal scaling smoothly

Only a small subset of keys move when a server is added or removed.

---

## 7. How Consistent Hashing Works (Step-by-Step)

### Step 1: Create a Hash Ring
- The hash space is represented as a circle from `0` to `2³² - 1`

### Step 2: Place Servers on the Ring
serverPosition = hash(serverId)

### Step 3: Place Keys on the Ring
keyPosition = hash(key)

### Step 4: Assign Key to Server
- Move clockwise on the ring
- The first server encountered handles the key

---

## 8. Core Rule of Consistent Hashing

Assigned Server = first server clockwise from hash(key)

---

## 9. Server Add / Remove Behavior

### Server Added:
- Only keys between the new server and its previous server are reassigned

### Server Removed:
- Its keys move to the next clockwise server

This ensures minimal disruption to the system.

---

## 10. Virtual Nodes (VNodes)
To avoid uneven load:
- Each physical server is mapped to multiple virtual nodes

### Example:
Server A → A1, A2, A3
Server B → B1, B2, B3

Benefits:
- Better load distribution
- Reduced hotspots
- Improved scalability

---

## 11. Where Hashing is Used in System Design
- HashMap / In-memory storage
- Caching systems (Redis, Memcached)
- Password storage (BCrypt, Argon2)
- Database indexing
- Bloom filters

---

## 12. Where Consistent Hashing is Used
- Load Balancers (sticky sessions)
- Distributed Caches (Redis Cluster)
- Database Sharding
- Message partitioning (Kafka – conceptually)
- CDN request routing

---

## 13. Load Balancer Example

hash(userId) → position on ring
→ route request to nearest clockwise server

Ensures:
- Session stickiness
- Cache efficiency
- High availability

---

## 14. Interview One-Line Answers

### Hashing:
Hashing enables fast data access and uniform distribution by converting keys into fixed-size hash values.

### Consistent Hashing:
Consistent hashing minimizes key redistribution during scaling by mapping both servers and keys onto a hash ring and routing keys to the nearest clockwise server.

---

## 15. Key Takeaways
- Modulo hashing is not suitable for distributed systems
- Consistent hashing enables smooth scaling
- Virtual nodes are essential for load balancing
- Widely used in modern system design
