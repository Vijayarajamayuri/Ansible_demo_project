# Ansible_demo_project

Create 3/4 servers 
1 control node 
2/3 worker nodes

## Install ansible on control node 

* sudo yum update -y
* sudo amazon-linux-extras install ansible2 -y

## Create ansadmin user on all servers and create pass : ansadmin
### Create same user(ansadmin) across all servers and provide password for all users.
* useradd ansadmin
* passwd ansadmin

IPS :

Node 1
ssh -i "testkey.pem" ec2-user@ec2-54-224-65-133.compute-1.amazonaws.com

Node2:
ssh -i "testkey.pem" ec2-user@ec2-54-163-193-206.compute-1.amazonaws.com

Ansible controller :
ssh -i "testkey.pem" ec2-user@ec2-3-93-201-53.compute-1.amazonaws.com![image](https://user-images.githubusercontent.com/46686521/222639627-6ac969a6-01ac-4f97-b35e-5bc89b9c2635.png)


## Provide root privileges to all ansadmin users on all servers.

visudo
ansadmin ALL ALL 
#### UNDER ROOT USER 

## Make sure that PasswordAuthentication yes in all servers under / etc/ssh/sshd_config file.

## restart process
systemctl restart sshd

## Generate ssh-keys using ssh-keygen command from ansadmin.

From control node generate run `ssh-keygen` as ansadmin, it genrates pub and priv keys 
[ansadmin@ip-172-31-31-112 .ssh]$ ls
id_rsa  id_rsa.pub


## Copy ssh public key using ssh-copy-id <hostname> from /home/ansadmin/.ssh/ location.

[ansadmin@ip-172-31-31-112 .ssh]$ ssh-copy-id 54.224.65.133


## Add public IPS TO HOSTS AND ping 

ansible all -m ping



