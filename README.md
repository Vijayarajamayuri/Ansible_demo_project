# Ansible_demo_project

Create 3/4 servers 
1 control node 
2/3 worker nodes

## Install ansible on control node 

* sudo yum update -y
* sudo amazon-linux-extras install ansible2 -y

## Create ansadmin user on all servers and create pass : ansadmin123
* useradd ansadmin
* passwd ansadmin
