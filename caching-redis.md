# Caching (Redis)

![Caching Architecture](./images/caching-redis.png)

## What is it?
Caching is a technique where frequently accessed data is stored in fast memory so that future requests can be served quickly without hitting the database.

---

## Why needed?
- Database is slow compared to memory
- Repeated queries increase database load
- To reduce response time
- To improve system performance and scalability

---

## How it works?
1. Client sends request
2. Server first checks cache
3. If data exists in cache → return response (Cache Hit)
4. If data not in cache → fetch from database (Cache Miss)
5. Store data in cache for future requests
6. Return response to client

### Flow
Client → Server → Cache  
Cache Hit → Response  
Cache Miss → Database → Cache → Response

---

## Cache Hit vs Cache Miss

### Cache Hit
- Data found in cache
- Fast response
- Database not accessed

### Cache Miss
- Data not found in cache
- Database is accessed
- Data stored in cache for next time

---

## Redis (High Level)
- Redis is an in-memory data store
- Very fast (used as cache)
- Commonly used in backend systems
- Suitable for read-heavy applications

---

## Benefits
- Faster response time
- Reduced database load
- Better scalability
- Improved user experience

---

## Real-world Example
User profile data is stored in Redis.  
If the same user opens the app again, data is served from cache instead of querying the database.

---

## Interview Ready Explanation
"Caching improves performance by storing frequently accessed data in memory. Redis is commonly used to reduce database load and improve response time."
