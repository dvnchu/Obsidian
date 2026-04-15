[[web]]
## Load Balancers
Load balancers provide two main features, ensuring high traffic websites can handle the load and providing a failover if a server becomes unresponsive.

When you request a website with a load balancer, the load balancer will receive your request first and then forward it to one of the multiple servers behind it.

![[Pasted image 20251219180911.png]]
Load balancers perform periodic checks with each server to enseure they are running; Health check if a server doesnt respond approprately the load balancer will stop sending traffic

## CDN (Content Delivery Networks)

It helps for cutting down traffic to a busy website.
It hosts static files from your website (Js, CSS, Images, Videos) and host them across thousands of servers all over the world. When a user request a file the CDN works out the nearest server and sends the request.

## DB
Webservers can communicate with databases to store and recall data from them.

## WAF (Web Application Firewall)
it sits between your web request and the web server; its primary puropose is to protect the webserver from hacking or DOS.


