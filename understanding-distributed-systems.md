# Key Characteristics of Distributed Systems

## 1. Scalability
- **Horizontal vs Vertical Scaling**:
  - **Horizontal Scaling**: Adding more servers.
  - **Vertical Scaling**: Increasing the computing power (CPU, RAM) of existing machines.
  - **Examples**:
    - *Horizontal*: MongoDB, Cassandra
    - *Vertical*: MySQL
  - **Note**: Vertical scaling often involves downtime due to the need to migrate to more powerful machines.

## 2. Reliability
- The ability of a system to continue functioning when one or more components fail.
- Requires replacing failed components/subsystems.
- Involves **redundancy** of software, components, or data — though this increases cost.

## 3. Availability
- A **reliable** system is always **available**, but an **available** system may not always be **reliable**.
- Increased **reliability** contributes to better **availability**, but the reverse is not necessarily true.

## 4. Efficiency
- Measured using two key properties:
  - **Latency**: Time taken to return a result.
  - **Throughput**: Number of results returned in a given time.

## 5. Serviceability and Manageability
- Refers to how easily the system can be maintained, updated, and monitored.

---

# Load Balancing

## 1. Purpose
- Enables **horizontal scaling**.
- Performs **health checks** on nodes and stops redirecting traffic to failed nodes.

## 2. Load Balancing Algorithms
- **Least Connection Method**: Sends requests to the server with the fewest active connections.
- **Least Response Time Method**: Prioritizes servers with the fastest response time and lowest active connections.
- **Least Bandwidth Method**: Chooses the server with the lowest data transfer load.
- **Round Robin Method**: Distributes requests sequentially across the pool of servers.
- **Weighted Round Robin Method**: Similar to Round Robin, but prioritizes servers with higher capacities.
- **IP Hash**: Uses the client’s IP address to consistently route requests to the same server.

## 3. Redundancy in Load Balancing
- Multiple load balancers can be clustered.
- Load balancers **monitor each other’s health** and step in if one fails.
