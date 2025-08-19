The task was to install NGINX and setup SSL for it

moving the nginx certificate and key (making the folder first if nonexistent)
```
mv /path/to/crt/and/key /etc/nginx/ssl/
```

nginx.conf (inside sever block)
```
ssl_certificate /etc/nginx/ssl/nautilus.crt;
ssl_private_key /etc/nginx/ssl/nautilus.key;
```
as per the task, also we'll make an html file with `Welcome!` typed in, and store it in the "root" `/usr/share/nginx/html` directory specified in the conf file.
```
echo "Welcome!" | sudo tee /usr/share/nginx/html/index.html
```

At any failure, it's a good idea to reload/restart NGINX and/or test its' configuration
```
sudo systemctl status nginx
sudo nginx -t
```

The final test is done from `jump_host`
```
curl -Ik https://172.16.238.11/
```

## Resources
- [Securing Nginx Web Server | Hackersploit Linux Security](https://www.youtube.com/watch?v=W44Q-8fU1OU&list=PLTnRtjQN5ieb3ljl02823yOnUax7sF1DD&index=1)
- 
