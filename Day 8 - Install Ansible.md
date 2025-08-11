Install `ansible` version `4.10.0` on `Jump host` using `pip3` only. Make sure Ansible binary is available globally on this system, i.e. all users on this system are able to run Ansible commands.

```
sudo pip3 install ansible==4.10.0
```

 learned that the versions of `ansible` and `ansible-core` are different as ansible-core is the engine for ansible and in out case has a`version 2.11.12`
 To verify the ansible and ansible core versions:
 - `ansible-core` : `ansible --version`
 - `ansible`: `pip3 show ansible`

Since the ansible is binary installed, the PATH environment variable needs to include `usr/local/bin` in it to be globally available. We can check that with `echo $PATH`.
## Resources
- Deepseek helped me find the command to install specific version of ansible.
- [This is How You Should Install and Configure Ansible on Linux!!! - YouTube](https://www.youtube.com/watch?v=8KdRL_yIpnM)
- [Installing Ansible — Ansible Community Documentation](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)