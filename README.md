# demo-haproxy-php-fpm

## What will happened?
This demo will create three virtual machines which will be connected in VPN.
The first machine is HAProxy server which serves SSL traffic to webservers in SSL Termination mode.
The second and third machines are identical Apache 2.4 servers with php-fpm configured with worker_module through Unix socket.

## Requirements
* ansible 2.7.5
* vagrant 2.2.3
* virtualbox 5.2.26


## How to run the demo?
1. Clone the demo code:
git clone https://github.com/yadkov/demo-haproxy-php-fpm.git ~/demo

2. Create the virutal machines:
cd ~/demo
vagrant up

3. Provision the virtual machines:
ansible-playbook playbooks/demo.yaml -i inventory/hosts.yaml

4. Test with the following link:
https://192.168.60.103/info.php
