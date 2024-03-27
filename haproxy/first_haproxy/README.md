Install HAProxy on Ubuntu 20.04
---------------------------------
  [refer here](https://www.vultr.com/docs/how-to-install-haproxy-on-ubuntu-20-04/?utm_source=performance-max-apac&utm_medium=paidmedia&obility_id=16876059738&utm_adgroup=&utm_campaign=&utm_term=&utm_content=&gclid=Cj0KCQiA2-2eBhClARIsAGLQ2Rmq6I44uo0Dqzv7-y8E95QQryAM1zMKZnkz2NqZyy1psNhTN56NQn0aAk37EALw_wcB)

### Manual steps for HaProxy

```
sudo vi /etc/ssh/sshd_config
sudo service sshd restart
sudo adduser raj 
sudo vi /etc/sudoers
su raj
```
![preview](Images/haproxy2.png)
![preview](Images/haproxy3.png)
![preview](Images/haproxy4.png)
![preview](Images/haproxy5.png)
* The above steps are executed by the `main-server and server1, server2`

# Main-server
```
sudo apt update
sudo apt install haproxy -y
sudo systenmctl status haproxy
haproxy -v
```
# Configure the HaProxy

```
sudo cp /etc/haproxy/haproxy.cfg /etc/haproxy/haproxy.cfg.bk
sudo nano /etc/haproxy/haproxy.cfg
sudo systemctl restart haproxy
```

## Server1 and Server2

```
sudo nano /etc/apache2/ports.conf
sudo nano /etc/apache2/sites-available/000-default.conf
sudo systemctl restart apache2
sudo rm  /var/www/html/index.html 
sudo nano  /var/www/html/index.html
```



These steps are for the 3 instances
-----------------------------------
* we need to create 3 ubuntu 20.04 instances
  ![preview](Images/haproxy1.png)
* And ensure the sudo permissions are given or not
* Then the PasswordAuthentication can be changed `no to yes`
   
* and restart the sshd service
* after that we need to adduser <username>
* we have to given permission to user
* and Add a user to sudoers file `username  ALL=(ALL:ALL) NOPASSWD:ALL`
  to execute the above steps for all the 3 instances parallelly

# Main Server
--------------
* install the haproxy on main server
```
sudo apt update
sudo apt install haproxy -y
sudo systemctl status haproxy
haproxy -v
```  
  Configure the HaProxy server

* To execute the following commands to configure the haproxy
```
sudo cp /etc/haproxy/haproxy.cfg /etc/haproxy/haproxy.cfg.bk
sudo nano /etc/haproxy/haproxy.cfg
sudo systemctl restart haproxy
```
> Playbook for the above all manual commands[Refer Here](https://github.com/qtrajkumar/Ansible_Zone/tree/main/HaProxy)

  
![preview](Images/haproxy6.png)
![preview](Images/haproxy7.png)
![preview](Images/haproxy8.png)
![Preview](Images/haproxy9.png)
