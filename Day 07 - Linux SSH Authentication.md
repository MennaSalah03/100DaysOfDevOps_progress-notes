The task is to allow the 3 app servers to be accessed with `ssh` without the need to enter a password from the host server 

The process was to create a key pair on the host server (if there's none) and then copying the contents of the **Public** key (it ends with`.pub`) to the app server which can be done manually, or with a certain command which make everything much easier.

The only new commands I used is for generating a key pair for the host server and copying the public key of said server to the 3 app servers after.
```
ssh-keygen -t rsa
ssh-copy-id -i ~/.ssh/id_rsa.pub root@serverip    
```
I checked success of the operation by trying to access the app servers and they accessed without needing a password as intended.

## Resources
I only needed this video for this task
[How to SSH Without a Password (like a boss)](https://www.youtube.com/watch?v=j2vBT3T79Pg&t=1s)