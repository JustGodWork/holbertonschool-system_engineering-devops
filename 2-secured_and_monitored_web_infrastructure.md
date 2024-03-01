# Secured And Monitored Web Infrastructure

## Firewalls:
We add a firewall to each server to control the traffic that reaches the server based on an applied rule set. Firewalls can block traffic from certain sources or of certain types, providing a first line of defense against attacks.

## SSL Certificate:
We add an SSL certificate to serve traffic over HTTPS. This encrypts the communication between the user's browser and the server, protecting sensitive information from being intercepted or tampered with.

## Monitoring Clients:
We add a monitoring client to each server to collect and send data to a monitoring service like Sumo Logic. This allows us to track and analyze the performance of our servers and applications over time.

## Specifics About This Infrastructure
Firewalls: Firewalls are used to protect the servers from unauthorized access and attacks. They filter incoming and outgoing traffic based on predefined security rules.

## HTTPS Traffic:
Traffic is served over HTTPS to encrypt the communication between the server and the client, ensuring that sensitive data like passwords and credit card numbers can't be intercepted or tampered with.

## Monitoring:
Monitoring is used to track the performance and health of our servers and applications. It helps us identify issues before they become critical and affect the user experience.

## Data Collection:
The monitoring tool collects data such as CPU usage, memory usage, disk I/O, network traffic, and application logs. This data is sent to a central monitoring service where it can be analyzed.

## Monitoring Web Server QPS:
To monitor your web server's Queries Per Second (QPS), you would configure your monitoring tool to collect this data from your web server. This could involve tracking the number of requests the server receives and sends each second.

## Issues with This Infrastructure
- ***SSL Termination at Load Balancer***: Terminating SSL at the load balancer level can be an issue because it means that traffic between the load balancer and the servers is not encrypted. This could potentially expose sensitive data if the internal network is compromised.

- ***Single MySQL Server for Writes***: Having only one MySQL server capable of accepting writes is an issue because it creates a single point of failure. If the MySQL server goes down, no new data can be written to the database until it's back up.

- ***Same Components on All Servers***: Having servers with all the same components (database, web server, and application server) can be a problem because it doesn't allow for load distribution based on the type of task. For example, serving static files (a task for the web server) uses very different resources than executing application code (a task for the application server).