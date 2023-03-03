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


Node 1
ssh -i "testkey.pem" ec2-user@ec2-54-224-65-133.compute-1.amazonaws.com

Node2:
ssh -i "testkey.pem" ec2-user@ec2-54-163-193-206.compute-1.amazonaws.com

Ansible controller :
ssh -i "testkey.pem" ec2-user@ec2-3-93-201-53.compute-1.amazonaws.com![image](https://user-images.githubusercontent.com/46686521/222639627-6ac969a6-01ac-4f97-b35e-5bc89b9c2635.png)

