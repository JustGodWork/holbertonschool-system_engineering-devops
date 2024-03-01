# Distributed Web Infrastructure

## Additional Servers:
We add two more servers to distribute the load and reduce the risk of a single point of failure. If one server goes down, the others can still serve the requests.

## Load Balancer (HAproxy):
The load balancer distributes incoming network traffic across multiple servers to ensure no single server bears too much load. This helps to increase the availability and reliability of applications.

### Load Balancer Configuration
The load balancer can be configured with various distribution algorithms, such as round-robin, least connections, and IP hash. In a round-robin setup, the load balancer distributes requests in a circular order, moving from one server to the next, looping back to the first when it reaches the end of the list.

### Active-Active vs Active-Passive Setup
In an Active-Active setup, all servers are running and can handle requests. The load balancer distributes incoming requests to all servers equally. In an Active-Passive setup, the passive server only starts handling requests if the active server fails. In our case, we are enabling an Active-Active setup to maximize resource utilization.

## Database Primary-Replica (Master-Slave) Cluster
In a Primary-Replica setup, the primary node (master) handles all write operations and can optionally handle read operations. The replica nodes (slaves) are read-only and replicate the primary node's data. This setup allows for high read scalability and data redundancy.

## Primary Node vs Replica Node
The primary node is responsible for handling write operations, while the replica nodes handle read operations. This separation allows for load distribution and increased performance.

## Issues with This Infrastructure
- ***SPOF (Single Point of Failure)***: If the load balancer or the database goes down, the entire website goes down.
- ***Security issues***: Without a firewall or HTTPS, the infrastructure is vulnerable to attacks and data transmitted over the network is not secure.
- ***No monitoring***: Without monitoring, it's difficult to identify and troubleshoot issues or understand the performance of the infrastructure.