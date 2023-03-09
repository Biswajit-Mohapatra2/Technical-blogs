---
title: "Create new EC2 instance in AWS cloud using Ansible Playbook"
datePublished: Sun Jan 29 2023 15:46:17 GMT+0000 (Coordinated Universal Time)
cuid: cldhk0y4l000209k00vjo3iv1
slug: create-new-ec2-instance-in-aws-cloud-using-ansible-playbook
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1675004897122/26982e5e-e491-4f9b-ac15-2a71fbe400be.png
tags: aws, ansible, hashnode, blogswithcc, wemakedevs

---

---

We will learn how to create Ansible Playbook for provisioning a new EC2 instance in the AWS cloud. Please follow the below steps in the machine where you have installed Ansible.

![](https://1.bp.blogspot.com/-g20rwtkBLDQ/YPB5vPk2pCI/AAAAAAAADmM/StR8itQoL_U4gmfl8sJdTKi_vOLitJTgwCLcBGAsYHQ/s566/Screen%2BShot%2B2021-07-15%2Bat%2B1.08.37%2BPM.png align="center")

# **Pre-requisites:**

[**Ansible is installed and Boto is also**](https://biswajitblogs.hashnode.dev/how-to-setup-ansible-on-ubuntu) **installed on the** Ubuntu EC2 instance.

<mark>Make sure you create an IAM role with&nbsp;the AmazonEC2FullAccess policy and attach the role to an EC2 instance</mark>.

![](https://1.bp.blogspot.com/-cZ9tPnVMqGU/YPB4PGWzWDI/AAAAAAAADmE/r2ERljoyAyY6PjBI7T486tD4lRDhboNcACLcBGAsYHQ/s534/Screen%2BShot%2B2021-07-15%2Bat%2B1.01.54%2BPM.png align="center")

# **Steps to create an EC2 instance using Ansible:**

Login to the EC2 instance using Git bash or ITerm/putty where you installed Ansible. Execute the below command:

**<mark>Edit Ansible hosts or inventory files:</mark>**

```bash
sudo vi /etc/ansible/hosts
```

<mark>Add the below two lines at the end of the file:</mark>

```bash
[localhost]
local
```

![](https://4.bp.blogspot.com/-_vWRo1PX0Dg/XCRRzKpNn2I/AAAAAAAAAnU/WrhhnT_-vB4M5XLVAwzIez6b9a-bTl_OACLcBGAs/s1600/Screen%2BShot%2B2018-12-26%2Bat%2B10.14.48%2BPM.png align="center")

```bash
cd ~

mkdir playbooks 
 
cd playbooks/
```

## **Create Ansible playbook**

```bash
sudo vi create_ec2.yml
```

```yaml
---
 - name:  provisioning EC2 instances using Ansible
   hosts: localhost
   connection: local
   gather_facts: False
   tags: provisioning

   vars:
     keypair: MyEC2Key        #Create Your Own KeyPair
     instance_type: t2.small
     image: ami-020db2c14939a8efb   #Write your own AMI id 
     wait: yes
     group: webserver
     count: 1
     region: us-east-2     #Write your suitable region
     security_group: my-jenkins-security-grp  
   
   tasks:

     - name: Task # 1 - Create my security group
       local_action: 
         module: ec2_group
         name: "{{ security_group }}"
         description: Security Group for webserver Servers
         region: "{{ region }}"
         rules:
            - proto: tcp
              from_port: 22
              to_port: 22
              cidr_ip: 0.0.0.0/0
            - proto: tcp
              from_port: 8080
              to_port: 8080
              cidr_ip: 0.0.0.0/0
            - proto: tcp
              from_port: 80
              to_port: 80
              cidr_ip: 0.0.0.0/0
         rules_egress:
            - proto: all
              cidr_ip: 0.0.0.0/0
       register: basic_firewall
     - name: Task             # 2 Launch the new EC2 Instance
       local_action:  ec2 
                      group={{ security_group }} 
                      instance_type={{ instance_type}} 
                      image={{ image }} 
                      wait=true 
                      region={{ region }} 
                      keypair={{ keypair }}
                      count={{count}}
       register: ec2
     - name: Task             # 3 Add Tagging to EC2 instance
       local_action: ec2_tag resource={{ item.id }} region={{ region }} state=present
       with_items: "{{ ec2.instances }}"
       args:
         tags:
           Name: MyTargetEc2Instance
```

![](https://2.bp.blogspot.com/-fopvg-RVjzQ/XCRS3f17B3I/AAAAAAAAAno/DzEcS8u8CgARiDh4-TwMtXycW-KLwPBaACLcBGAs/s1600/Screen%2BShot%2B2018-12-26%2Bat%2B10.19.06%2BPM.png align="center")

<mark>now execute the ansible playbook by:</mark>

```bash
sudo ansible-playbook create_ec2.yml
```

![](https://1.bp.blogspot.com/-N3ugduvLL7c/XCRSgzV8z-I/AAAAAAAAAnc/J8u_-qACSlQtJe4vLT0DeZwt5_wtQ741QCLcBGAs/s1600/Screen%2BShot%2B2018-12-26%2Bat%2B10.17.17%2BPM.png align="center")

***<mark>Fix the warnings by executing the below command:</mark>***

```python
pip install --upgrade requests==2.20.1
```

![](https://1.bp.blogspot.com/-u7VW6U6-gV0/XqYYhKqhPMI/AAAAAAAACAg/G2vYLQJlxxAZ9RlpZBgabjq_BX4sN1pCwCLcBGAsYHQ/s1600/url%2Blib.png align="center")

<mark>If everything is good, you should see the new instance created on the AWS console. make sure you can connect to that instance.</mark>

**That's it!! That is how you create a new EC2 instance using Ansible.**

---

# Conclusion

<mark>Ansible and Terraform together form a flexible workflow for spinning up servers with the needed software and hardware configurations. Running Ansible directly as part of the Terraform deployment process allows you to have the servers up and bootstrapped with dependencies for your development work and applications much faster</mark>.