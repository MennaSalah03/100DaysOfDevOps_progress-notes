
Installing itables + services + dependencies
```
sudo yum install -y iptables iptables-services iptables-utils
```

```
iptables -F iptables -X
iptables -P INPUT ACCEPT
iptables -P FORWARD DROP
iptables -P OUTPUT ACCEPT
```


`-A` is for putting at the top and `-I` is adding to the end. In general when we want to have just one ACCEPT and the rest DROP, as the rules is executed sequentially (top to bottom), the order is to drop all then accept the exception. One way to do is as follows:
```
iptables -A INPUT -p tcp -s <LBR_HOST_IP> --dport <PORT> -j ACCEPT
iptables -A INPUT -p tcp --dport <PORT> -j DROP
```

I am not sure whether saving the rule is necessary, but I think it's advisable at least so that when rebooting, it's still the same rules in effect.
```
sudo service iptables save
```
## Resources
This is the only thing I needed besides some assistance from an LLM for saving rules
- [iptables Complete Guide | HackerSploit Linux Security - YouTube](https://www.youtube.com/watch?v=6Ra17Qpj68c)
