
# Simple Web Stack

## 1 - What is a server?
A server is a computer or system that provides resources, data, services, or programs to other computers, known as clients, over a network. In the case of our infrastructure, the server hosts the website.

## 2 - What is the role of the domain name?
The domain name serves as an easy-to-remember address to access a website. Instead of having to remember an IP address (like 8.8.8.8), you can simply type www.foobar.com.

## 3 - What type of DNS record is www in www.foobar.com?
The "www" in www.foobar.com is a type of DNS record known as a CNAME (Canonical Name). It is used to alias one name to another. In this case, it's aliasing www.foobar.com to the IP address of our server (8.8.8.8).

## 4 - What is the role of the web server?
The web server (Nginx in our case) accepts incoming requests from clients (browsers), processes these requests, and sends back the appropriate response, usually in the form of a webpage.

## 5 - What is the role of the application server?
The application server runs the application code. It processes the business logic of the application and interacts with the database to fetch, store, or update data.

## 6 - What is the role of the database?
The database (MySQL in our case) stores all the data that the application needs to function. This could be user data, application data, files, and more.

## 7 - What is the server using to communicate with the user's computer requesting the website?
The server communicates with the user's computer using the HTTP (Hypertext Transfer Protocol) or HTTPS (HTTP Secure) protocols.

## 8 - What are the issues with this infrastructure?

- SPOF (Single Point of Failure): If the single server goes down, the entire website goes down.
- Downtime when maintenance needed: If we need to deploy new code or the web server needs to be restarted, the website will be unavailable during that time.
- Cannot scale if too much incoming traffic: If the website receives more traffic than the server can handle, it will become slow or unresponsive. This setup does not have a way to easily add more resources to handle increased load.