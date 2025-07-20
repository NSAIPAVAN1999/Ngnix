**NGINX**( Generally called as Engine-x)

It is a high performance,open source web server(server that is going to serve content to our browser)
also functions as
**-Reverse Proxy
-load balancer
-HTTP Cache
-Api Gateway**

**What Does NGINX Do?**
At its core, NGINX is designed to handle many simultaneous connections efficiently.
It was originally created to solve the C10k problem — the challenge of handling 10,000+ concurrent client connections on a single serve

**How NGINX Works**
NGINX uses an asynchronous, event-driven architecture, which means:

It doesn’t create a new thread or process for each request (unlike traditional servers like Apache).
Instead, it uses a master process to manage multiple worker processes.
Each worker can handle thousands of connections concurrently without blocking others.

**Common Use Cases**

**Web Server** – Serves static files like HTML, CSS, JS, images.
**Reverse Proxy** – Forwards client requests to backend servers (e.g., Node.js, Python, Java apps).
**Load Balancer** – Distributes traffic across multiple servers to improve performance and reliability.
**SSL/TLS Termination** – Handles HTTPS encryption/decryption.
**Caching** – Stores responses to reduce load on backend services.
**API Gateway** – Routes and manages API traffic in microservices architectures.

`Example used AIRBNB`


so if we do not have the NGINX we need to increase the servers(inside of our AWS account) as we get the lot of traffic

`Reverse Proxy` - The client makes the request to the nginx and then the nginx makes the request to the backend server and that backend server will respond with the response to the NGINX
`Load Balancer` - so when the client send the request to the nginx(as we have only one instance of nginx) and it is responsible to send this to the available server.

when we have the HTTP or HTTPS server - so basically server need to encrypt and decrypt the request and response and if we have lot of servers we need to do this encryption and decryption on each single server so instead we can
do the encryption on the nginx so it sends the request and get the response so it basically does the encryption and decryption process.

Nginx terminology:
In NGINX, configuration is built around a set of directives and blocks that define how it should behave. Here's a clear breakdown of the key terminology used in NGINX:

				1. Directive
						A directive is a single instruction in the NGINX configuration file. It tells NGINX what to do.
						Syntax: directive_name value;
						Example
								listen 80;
								server_name example.com;
				2. Context (or Block)
						A context is a block of configuration enclosed in {} that groups related directives. Some directives are only valid inside specific contexts.
						
						Context		Purpose
						main		Top-level context for global settings
						http		Defines HTTP server settings
						server		Defines a virtual host (domain)
						location	Defines how to respond to specific URL paths
						upstream	Defines backend servers for load balancing
						events	    Controls connection processing