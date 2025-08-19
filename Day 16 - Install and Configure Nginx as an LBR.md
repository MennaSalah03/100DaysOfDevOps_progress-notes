Today, I learned more about NGINX, and Load balancers

The task was to install and configure NGINX on our load balancer server with an http context for the 3 app servers we have. 

I got confused about ports and what is connected to what. but I found out traffic worked like this:
```
Internet/Clients → nginx:80 → App Servers:8089 → DB
```
- The app servers port is not exposed publicly to the internet and could be any number. 
-  port 80 is a standard HTTP port that clients expect

The steps were really similar to day 15 as in installing and configuring steps.

The configuration was a bit different though, and you need to know the port connected with the app servers
```
sudo ss -tlnp | grep httpd
```
upstream app_servers {
    server 172.16.238.10:8089;
    server 172.16.238.11:8089;
    server 172.16.238.12:8089;
}

server {
	......
	
    location / {
        proxy_pass http://app_servers;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}

## check success
After changing configuration file, Test nginx configuration for syntax errors
```
 sudo nginx -t
```

Check httpd status on the app servers
```
sudo systemctl status httpd
```
Checking each app server:
```
curl -I http://172.16.238.10:8089
curl -I http://172.16.238.11:8089
curl -I http://172.16.238.12:8089
```
Check port connection (80) for the NGINX server aka Load balancer
```
curl -I http://localhost:80
#or
curl -I http://172.16.238.12:80
```
## Resources
- [What is a Load Balancer?](https://www.youtube.com/watch?v=sCR3SAVdyCc&t=10s)
- [How to configure NGINX as a load balancer - YouTube](https://www.youtube.com/watch?v=v81CzSeiQjo)