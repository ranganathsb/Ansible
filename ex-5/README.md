# Ansible Module

Run this command : 
- Ansible inbuilt module : `ansible-doc -l` 
- #Comment `ansible-doc ModuleName`
- We need to check the module : `ansible-doc yum` `ansible-doc service`
- You can check playbooks can be written : `ansible-doc yum -s` `ansible-doc service -s`

- For webservers :
- Install: ```ansible webservers -i inventory -m yum -a "name=httpd state=present" --sudo```
- Start the service : ```ansible webservers -i inventory -m service -a "name=httpd enabled=yes state=started" --sudo```

- For db servers: 
- Install : ```ansible dbservers -i inventory -m yum  -a "name=mysql-server state=present" --sudo```
- Start the service :```ansible dbservers -i inventory -m service  -a "name=mysqld  state=started" --sudo```
- can verify the `vagrant ssh db` in another terminal `service mysqld status`


- Try accessing the webpage cannot because of firewall is blocking :`192.168.33.20`
```ansible webservers:dbservers -i inventory -m service -a "name=iptables state=stopped" --sudo```

