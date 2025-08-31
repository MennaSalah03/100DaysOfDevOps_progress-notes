In this task, MariaDB has a connection issue and we attempt to discover and fix the problem.

1. First, we try to start/restart the MariaDB service
```bash
sudo systemctl start mariadb
```
2. Of course it doesn't work... but it prompts us to try a command `sudo journalctl -u mariadb` which we will only view the last 50 lines for less confusion
```bash
sudo journalctl -u mariadb -n 50
```
There's another option which is to lookup the error logs files
```bash
sudo tail -50 /var/log/mariadb/mariadb.log
```
3. Any of the following directs us to the error source
The error in the logs:
```
2025-08-12 11:35:31 0 [ERROR] mariadbd: Can't create/write to file '/run/mariadb/mariadb.pid' (Errcode: 13 "Permission denied")

2025-08-12 11:35:31 0 [ERROR] Can't start server: can't create PID file: Permission denied
```
This indicates that the directory either doesn't have the permission to create a file, or doesn't exist
```bash
mkdir -p /run/mariadb
sudo chmod 755 /run/mariadb
```

starting, restarting the service should give no errors now
## Resources
- Help from Claude LLM :)