The xFusionCorp Industries security team recently did a security audit of their infrastructure and came up with ideas to improve the application and server security. They decided to use SElinux for an additional security layer. They are still planning how they will implement it; however, they have decided to start testing with app servers, so based on the recommendations they have the following requirements:

Install the required packages of SElinux on App server 3 in Stratos Datacenter and disable it permanently for now; it will be enabled after making some required configuration changes on this host. Don't worry about rebooting the server as there is already a reboot scheduled for tonight's maintenance window. Also ignore the status of SElinux command line right now; the final status after reboot should be disabled.

---
SElinux states:!
- enforcing -  security policy is enforced.
-  permissive -  prints warnings instead of enforcing.
- **disabled - No SELinux policy is loaded**.


1. The first step is to install SElinux (and packages!) on the specified server
```bash
sudo yum install policycoreutils policycoreutils-python selinux-policy selinux-policy-targeted libselinux-utils setroubleshoot-server setools setools-console mcstrans
```
2.  Next, configure SElinux by changing it's state to disabled in the `/etc/selinux/config` file
```bash
# change this line
SELINUX=enforcing 
# To this
SELINUX=disabled
```

3. lastly, we need to check if the changes were done and the output is `Disabled`
```bash
getenforce
```

