# How to setup Jenkins in Ubuntu EC2 instance?

---

# 1\. What is Jenkins?

Jenkins is an open-source continuous integration/continuous delivery and deployment (CI/CD) automation software DevOps tool written in the Java programming language. <mark>It is used&nbsp;</mark> **<mark>to implement CI/CD workflows, called pipelines.</mark>**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674408739518/31e6d054-093d-446b-a1ea-e92f1b1a4853.png align="center")

---

# Download the Dependencies.

* Please follow the steps to install Java, Jenkins, and Maven on the Ubuntu instance. Jenkins, Maven is Java-based applications, so we need to install Java first. 
    
    ### **Change Host Name to Jenkins:**
    
    ```bash
    sudo hostnamectl set-hostname Jenkins
    ```
    

### **Perform update first:**

```bash
sudo apt update
```

### **Install Java:**

```bash
sudo apt install default-jdk -y
```

![](https://1.bp.blogspot.com/-qU4i2pBmiF0/X0_5I0gsSFI/AAAAAAAAC9Y/OpA8kGH9e0Mt2hy3oN4v5bEazBMzkzCvQCLcBGAsYHQ/s1238/Java%2Binstall.png align="left")

### **Maven Installation:**

Maven is a popular build tool used for building Java applications. You can install Maven by executing the below command:

```bash
sudo apt install maven -y
```

* You can type **mvn --version**  
    you should see the below output:
    
    ![](https://1.bp.blogspot.com/-f7BkzrZuqsY/XqI3aaq-L6I/AAAAAAAAB_E/LB9GM2XKMuc1_e4ewHHCPSl0SBaQ5IlcgCLcBGAsYHQ/s1600/mvn%2Bv.png align="left")
    

# Now let's start Jenkins installation

### **Jenkins Setup:**

**<mark>Add Repository key to the system:</mark>**

```bash
wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
```

![](https://2.bp.blogspot.com/-cd1SVp8YoIM/XGMgy9pykrI/AAAAAAAAA1c/XkecewUWbzUMoEDJ_h1-5CiRpFU-q8DAQCLcBGAs/s1600/jenkins%2Binstall%2B1.png align="left")

**<mark>Append Debian package repo address to the system:</mark>**

```bash
echo deb http://pkg.jenkins.io/debian-stable binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list
```

![](https://4.bp.blogspot.com/-cdUxPb8fQYM/XGMg4VLJg6I/AAAAAAAAA1g/cgFbWED0ZCEy7bDhAcmsmrvYVN-NpzJPgCLcBGAs/s1600/jenkins%2Binstall%2B2.png align="left")

**Update Ubuntu package:**

```bash
sudo apt update -y
```

![](https://3.bp.blogspot.com/-9ubM5hn5lxs/XGMhKHD7QSI/AAAAAAAAA1w/MwhXfDKYRJ4b4PVI7JhGgft5jZZ3Mr1RACLcBGAs/s1600/jenkins%2Binstall%2B3.png align="left")

**<mark>Install Jenkins:</mark>**

```bash
sudo apt install jenkins -y
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674406989703/c09e6e7b-ef7a-4a4f-b342-8b343ffb2073.png align="center")

**<mark>Start Jenkins:</mark>**

```bash
sudo systemctl start jenkins
```

**<mark>Check the status of Jenkins:</mark>**

```bash
sudo systemctl status jenkns
```

**<mark>Access Jenkins in a web browser:</mark>**

Now Go to the AWS console. Click on EC2, and click on the running instances link. Connect to your instance using its Public DNS/IP Address.

<mark>Now go to the browser. Enter the public DNS name or public IP address with port no 8080</mark>.  
<mark>http://EC2_public_dns_name:8080</mark>

**Unlock Jenkins:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674407327173/1890cb9d-ad5d-4546-8a88-97f3c1c15041.png align="center")

**Get the initial password from the below file:**

```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

Copy the password and paste it into the browser. Then click on install suggested plug-ins.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674407442030/1944b987-c754-4b87-9071-6046c07b0d61.png align="center")

Also, create user name and password. Enter everything as admin. at least the user name as admin password admin.

![](https://3.bp.blogspot.com/-1a9vEIb0xI0/XGMh0kxggeI/AAAAAAAAA2I/yUqJ0O9ODT4vHqnp9fEiGLpRAoCT-1XEACLcBGAs/s1600/create%2Badmin.png align="left")

Click on Save and Finish. Click on start using Jenkins. Now you should see a screen like below:

![](https://1.bp.blogspot.com/-WOuHvNuQdps/XpKUN3btd1I/AAAAAAAABzc/V6hAhp2A4Q4vee12UxOoOE0omEQmBEbSQCLcBGAsYHQ/s1600/welcome%2Bjenkins.png align="left")

---

# Conclusion

Jenkins is like the soul of the continuous integration process as it builds and tests the app continuously which makes it easier to integrate changes to the process. Most of the process is automated and this saves time and effort which can be used to perform other tasks related to the delivery. It has some issues like the old UI but the benefits like an active opensource community overshadow the little disadvantages. This is why Jenkins is the most popular CI server among developers.

---