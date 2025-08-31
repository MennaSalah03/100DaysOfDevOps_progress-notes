Since it's the first time, it took some time and multiple sessions to figure how things work and the architecture of the nautilus network.

A very important and fundamental aspect for the tasks in general is to be able to connect to remote servers using SSH
```bash
ssh user@server_name_or_ip
```
then paste the respective password for the server.

Another aspect is operating as root user with the root privileges and permissions that comes with it
```bash
sudo su -
```
For this, you'll also be prompted to enter the server's password again, but it's the last time, I promise.

For the task itself, we had to setup a user with non-interactive shell, which basically means the user won't be able to run shell commands, the user account is just to run automatic scripts.
```bash
adduser user_name -s /sbin/nologin
```
To check the user has been generated
```bash
id user_name
```