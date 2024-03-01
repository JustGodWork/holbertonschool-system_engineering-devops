# Scale UP

## Additional Server:
We add an additional server to further distribute the load and reduce the risk of a single point of failure. If one server goes down, the others can still serve the requests.

## Load Balancer (HAproxy) Cluster:
We configure the existing load balancer with the new one in a cluster to distribute incoming network traffic across multiple servers. This helps to increase the availability and reliability of applications.

## Split Components:
We split the web server, application server, and database each into their own server. This allows each server to be optimized for its specific task, improving performance and making it easier to scale each component independently.

## Specifics About This Infrastructure
- ***Additional Server***: The additional server is added to handle more traffic and provide redundancy. If one server fails, the other servers can continue to handle requests, minimizing downtime.

- ***Load Balancer Cluster***: The load balancer cluster is added to distribute the load evenly across all servers and to provide failover. If one load balancer fails, the other can continue to distribute traffic.

- ***Split Components***: Splitting the components onto their own servers allows each server to be optimized for its specific task. For example, the database server can be optimized for disk I/O, the application server for CPU usage, and the web server for network I/O. This also makes it easier to scale each component independently as traffic increases.