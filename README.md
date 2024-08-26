
# What tools will we use in the project?

# Prerequisite
Oracle VM Virtualbox

ansible

Vagrant

Vagrant plugins


![image](https://github.com/user-attachments/assets/75d1eb7e-4687-438a-8592-ccbc9144fc32)


# Project Overview

This project involves automating the deployment of a web application using Vagrant and Ansible. The setup includes provisioning five virtual machines (VMs) to handle different components of the application. The VMs are configured as follows:

    Tomcat VM: Hosts the Apache Tomcat application server.
    NGINX VM: Acts as a reverse proxy server using NGINX.
    MariaDB VM: Provides the MariaDB database service.
    RabbitMQ VM: Manages message queuing with RabbitMQ.
    Memcached VM: Utilizes Memcached for caching.

The Vagrant configuration manages VM provisioning, while Ansible handles the configuration and deployment of the software on each VM. This setup allows for scalable and efficient deployment of web applications.

# Project steps 

Create ansible playbook for each VM 

# mariadb.yml

![image](https://github.com/user-attachments/assets/7192e162-9422-492c-ab62-847dd88b964e)

![image](https://github.com/user-attachments/assets/41caa712-46bd-476b-ae56-667cdb1c861b)

![image](https://github.com/user-attachments/assets/734a52af-f5eb-4d15-b500-259599fba9ca)

![image](https://github.com/user-attachments/assets/2b3c4004-7863-4661-b186-ee8bf9b12bff)

# MEMCACHE.yml

![image](https://github.com/user-attachments/assets/0d54becd-bb53-4e8d-9418-8783d04687c4)

# rmq.yml

![image](https://github.com/user-attachments/assets/71efa534-2b50-4f9c-a67f-4cd02e0e5cba)

![image](https://github.com/user-attachments/assets/c92468ad-e8b9-4121-ba44-b32100f7db1e)

# app01.yml

![image](https://github.com/user-attachments/assets/ad89281f-af50-4519-affd-44fdaa73e7bb)


![image](https://github.com/user-attachments/assets/155e2247-3f01-4aaa-aefc-60d6515d992a)

![image](https://github.com/user-attachments/assets/17d2dc14-5624-4716-8b4a-96089c2b2d31)

# web01.yml

![image](https://github.com/user-attachments/assets/6ae69c5c-27a8-4cb0-b55a-326ef83ce70d)

![image](https://github.com/user-attachments/assets/ccbd4e38-8e6f-43a4-b8be-7c886b1156cf)

# after create ansible playbooks we will create a Vagrantfile

# Vagrantfile

![image](https://github.com/user-attachments/assets/cb0d9b03-8381-4b37-8e5c-f9d16207cf59)


![image](https://github.com/user-attachments/assets/cc65a98e-38c9-487b-a3f4-9940fc7518ee)

![image](https://github.com/user-attachments/assets/627070b1-df0f-4820-80e8-68c2d9b2e194)

![image](https://github.com/user-attachments/assets/e4e963ae-7c3a-4002-8cdb-5b83d2633364)

![image](https://github.com/user-attachments/assets/43ed03cf-4e1f-4aa2-912a-2aebe7709e04)

# And after creation write in the terminal vagrant up 

![image](https://github.com/user-attachments/assets/38e5661a-0c3e-423a-b399-bae9643e4fed)

![image](https://github.com/user-attachments/assets/d3cf59d9-3875-4576-b5c8-35e04e6f16cd)

