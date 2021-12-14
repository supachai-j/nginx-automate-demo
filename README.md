# NGINX Automation Demo
Webinar NGINX Automation Demo


Step 1 : Installation NGINX OSS Mainline/Stable Version.
```
$ cd vagrant
$ vagrant up nginx-oss01
```
Browsing access URL: http://192.168.55.41

Step 2: Installation NGINX Plus laste version (R25)
```
$ vagrant up nginx-plus01
```
Browsing access URL: http://192.168.55.42


Step 3 : Deploy NGINX Config for NGINX Web Server to NGINX Plus and NGINX OSS.
```
$ ansible -i hosts_vagrant all -m ping

$ ansible-playbook -i hosts_vagrant 3-deploy-config-nginx-web-server.yml
```

Step 4 : Deploy NGINX Config for NGINX Web Server (Reverse Proxy and Load Balanceing) to NGINX Plus and NGINX OSS.
```
$ ansible-playbook -i hosts_vagrant 4-deploy-config-nginx-web-server-proxy.yml
```

Step 5 : Deploy NGINX Config for NGINX Web Server (Reverse Proxy and Load Balanceing) + NGINX App Protect (WAF) to NGINX Plus.
```
$ ansible-playbook -i hosts_vagrant 5-deploy-config-nginx-app-protect-web-server-proxy.yml
```