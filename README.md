# HW3-DevOps

### Building Infrastructure

* Complete Tasks 1--5.

### Conceptual Questions

1. Describe three desirable properties for infrastructure.
- **Available:** 
  - No or limited interruption to provided services.
- **Resilient:** 
  - Can adapt to unknown and unexpected situations.
- **Scalable:** 
  - Can increase specific units in response to demand.


2. Describe some benefits and issues related to using Load Balancers.
- **Benefits:** 
  - **Available:** Send traffic to healthy instances.
  - **Scalable:** Request new instances as needed.
  - **Efficiency:** Shift delivery of static content from infrastructure to third-party provider.
  
- **Issues:** 
  - When load balancer goes down, stand-by servers can take over in the event leader goes down.
  
  
3. What are some reasons for keeping servers in seperate availability zones?
- Supports isolation and spreads risk by operating instances in independent pools to avoid **cascading** failures.
- Ensures **availability** and **robustness**. Useful for supporting certain deployment strategies.
- Geographically placed production environments.


4. Describe the Circuit Breaker and Bulkhead pattern.
- **Circuit Breaker:**
  - Circuit breaker avoids making the protected call when the circuit is open, it eliminates connections to faulty services. Circuit breakers help reduce resources tied up in operations which are likely to fail. Also, it avoids waiting on timeouts for the client, and a broken circuit avoids putting load on a struggling server.

- **Bulkhead pattern:**
  - Bulkheads effectively isolate components and protect from cascading failures through the enforcement of limits (load shedding).


### Screencast

[Click here to view the screencast](https://docs.google.com/forms/d/e/1FAIpQLSe30s_3WGuBNCMIycibJX7Aa_jVltrMkS0np6Udzq9yi6MvNQ/viewform?usp=sf_link)
