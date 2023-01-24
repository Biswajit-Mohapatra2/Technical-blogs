# How To Setup Jenkins using BootStrap Scripts in AWS EC2 Instance while Launching

---

# **What is a bootstrap script in aws?**

If you want to execute some commands during boot up(launch), you can execute them easily by loading the script in the user data section during the EC2 launch. Bootstrap scripts run only once - when the instance is instantiated for the 1st time.

<mark>Please follow the below steps to create an EC2 instance.&nbsp; We will be installing Java, Maven and Jenkins during boot-up</mark>.

**How to create an EC2 instance in the AWS console?**

**What is an EC2 instance?** 

It is a virtual server provided by AWS. Amazon Elastic Compute Cloud (Amazon EC2) provides scalable computing capacity in the Amazon Web Services (AWS) Cloud. Using Amazon EC2 eliminates your need to invest in hardware upfront, so you can develop and deploy applications faster. You can use Amazon EC2 to launch as many or as few virtual servers as you need, configure security and networking, and manage storage. Amazon EC2 enables you to scale up or down to handle changes in requirements or spikes in popularity, reducing your need to forecast traffic.

<mark>We will be using this EC2 to set up Jenkins.&nbsp;Please follow the below steps to create an EC2 instance</mark>.

# **Pre-requisites:**

## Shell script for setting up Jenkins in Ubuntu instance

```bash
#!/bin/bash
# Shell script for installing Java, Jenkins and Maven in Ubuntu EC2 instance

# Command for installing Java 11
sudo apt-get update
sudo apt-get install default-jdk -y

# Command for installing maven
sudo apt-get install maven -y

# Script for Jenkins installation

#Add Repository key to the system
wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -

#  Append debian package repo address to the system
echo deb http://pkg.jenkins.io/debian-stable binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list
 
sudo apt-get update
# Install Jenkins

sudo apt-get install jenkins -y

echo "Jenkins installed successfully.."
```

---

# ***Steps:***

**1.** **<mark>Login to the AWS console by clicking this link&nbsp;-:&nbsp;</mark>** [**<mark>https://aws.amazon.com/console/</mark>**](https://aws.amazon.com/console/)

**<mark>Click on All services, Click on Compute --&gt;&nbsp; Click on EC2</mark>**

![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjdMSrr0ZnXXAp0rl06h-OWZ7VXFziWn1cYEAf-hBcciycUh6FYKsFAJtc7g3Zxv2Z9VXu4QI77LhZAjVFYPwhCSSWry0h-wCWkKo8mD_nAys4wp0WqAgu3loVfXWoeZ1_2xvnmUwXEfyBBpcwuwulo3t57sY9os1FVBBMOk9JeBYGtqaVdCN9OpEyp/s1314/Screen%20Shot%202022-05-01%20at%204.22.52%20PM.png align="center")

**2.** **<mark>Click on Launch instance</mark>**

![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEizWxYmW843q5-ku87mgfjDqfG5KSNPwXPDyoVeTtjtrN59nMLHZiPGZjpWaOcH_V1SookbvUVrfF-vsuACdfBZF6tND6z0pT3GU-lTTYJg-Q4mNjxlDjZC40lIHuF2KDmImI2aegg8Vctt_tYDj4VzxYb98GwOULGlpQDHDGAmXjTWahdf4V-LS0WT/s2378/Screen%20Shot%202022-05-01%20at%204.24.01%20PM.png align="left")

**3.** **<mark>Enter Name as Jenkins-EC2 and&nbsp;enter 1 as the number of instances</mark>**

![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgoaKxThUhobUZPhPZRALovaKMXiI64lIPpIgonj59fZ16ik-HX0jB132o7EHQFYDG8xCZg_PIURT2nsJZJE5HrrpwlV_0fdcTaMbdHDBYSbELZckOawTPR17s9I7oYpJ2d2RJx1Jy0swtanMxulokaft0vWsoTagv1_5v8gMIhMbVLbLeyAnwbGxBv/s1802/Screen%20Shot%202022-05-01%20at%204.25.32%20PM.png align="left")

**4.** **<mark>Select Ubuntu and choose Ubuntu server 18.0.4 as AMI</mark>**

![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEimuLA8sz1aigB1nc5iJEW19J4g9KuA7-sZeMJli7vaiwMuqVZOOEZHiGrBLouwU2C8GPbU6la_DzHTptKKvvRP-COneVOp4H-rc0Ly1c3N7GJ8_3GSifjpPbFyQrtjPqfWxgLuizAHpmfm15irUfeN2qx3TGJmnx3X7BQDubkbaz8r2nWatvvx50H4/s1430/Screen%20Shot%202022-05-01%20at%204.26.04%20PM.png align="left")

**5.** **<mark>Enter t2.small as instance type</mark>**

**6\. <mark>You can choose the existing Key Or You Can create new key-pair</mark>**

**7. <mark> Under Network settings, Click Edit</mark>**

![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj3Ei8X-IkfsarxT7q0N-sxQPCU9835rlGDwp55cX8KwSseDulJ415y2LhEZryH5SpWwXUuaqGrl-31krQ4a9c_K4PHaYNPxm5LIPdiZHestM0zdDhNISnH_tsmu7CzellKVvC7FjTftUeVBxEaJ8PtzEedQ9phu4SsZfNGRA1BHsDfar8SDA8hPIpm/s1552/Screen%20Shot%202022-05-01%20at%204.33.22%20PM.png align="left")

**<mark>Add port range as 8080 and select AnyWhere as Source Type, that should enter 0.0.0.0/0 as Source</mark>**

![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj-mKImyLnEZE4zy4G0S-D2SYse-2xsjkF5E-D6dZHzc60hSap3d1VGP_fO2lqgdev9rCY_K8BURsvEXkHYLcMQM2tVBr9Cdp3Xnops698lKdg33FS2wyq0e3V9orvQOH9pee9hLZ2bBd9pmMdf1cpDVVdHIWO43vrCq8oUjDlKw_2-2HQI36ouiWA8/s1512/Screen%20Shot%202022-05-01%20at%204.33.37%20PM.png align="left")

![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEibQHlMMZ9cY_28sZyx4G3dsRyp3gxJlJpgqXpYa_Zlf26xt05DodbOnAuuMv9lwTZA5QvzPV5v9FZaeekwvPUX-HtMnihHlhr6IRN9LXcqv1dQqe6a70OZ3yOHLxouwZy1H4FjIJ82rBs-9KkW8M8fVmYUe6vNkf8Kwrtyb7wS9vgECZ1JCw69TRLn/s1540/Screen%20Shot%202022-05-01%20at%204.34.03%20PM.png align="left")

**8\. <mark>Enter 10 GB as storage Or You can choose any number of Storage</mark>**

![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjZqoMTfKzupJj-LpN09Oos9v3YVezPjEBkFmib3IcJk-zHT1IqrrZjETcWCWo7Vr9OHRcIzEmcsKHRogCcEVxr8uFXNhBoANsVDpt5pvywZlP7p8lfsVZ2du1Oy2r1_xFqikg1r4une6rHYRLNsisYE3W5T99GYQKiH-bCVM0qjDnWwup0dacT-aIS/s1516/Screen%20Shot%202022-05-01%20at%204.38.33%20PM.png align="left")

## ***Steps to add bootstrap script during EC2 launch***

**<mark>Click on Advanced Details:</mark>**

![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiHuv2xzfoeWfR_gFDHLzCbmUv5TFLVeISMyiPq2dhOQDxIHzKOGSoZMg71fz-FhXddlj6ecroyDyFB62WQCawWQc7m3d2_Zl8hoKu8PZPyn1eiwxx-5nY-f1Bm7vMFb7GMLRSN6frEGHP_KgcEGjijz57Tt5oZ5EvSVq5z0RMLyBmJ1SfSYAHSfLTh/s894/Screen%20Shot%202022-09-14%20at%208.19.40%20AM.png align="left")

**<mark>Now go to the User Data section and&nbsp;Copy the script from above Shell script command</mark>**

![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiANIMVmivdnx1-K_EB9mmaS0BIcnKk44HZOr9NkXlgz07jL5QNBgHfWuPESFWtgdkow9QKDgesVpPw_TKtQuohfoNgjejtuwENrtiGXVEWftn48ykYSAc8KvOIqW4QpF9IlGAAoQ02pqGIId6dqIDXQBA2HS8OxAFxqRHeZwNi6AfNaqrNZbonHDau/s1230/Screen%20Shot%202022-09-14%20at%208.20.06%20AM.png align="left")

**9\. <mark>Click on Launch Instance.</mark>**

**<mark>Click on View instances</mark>**

![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhmD_HCe4Wqpl5tNwuRyl7a90JDWcoR5fl6ns47HGpcOjulbhZ-hgpBVmQlhtMzgziL-PAzZk4ouQhDRBR7AFwyFfTWKepCFNm2ux5hxDAKFoJEzZ6FS6Ie1mc0JC4Dx1vECUjyUno_Lnx5ITtdOBYfkvykASMtXXs1xF2dkI8goPxGB8Hy2iWw5-vy/s2628/Screen%20Shot%202022-05-01%20at%204.40.54%20PM.png align="left")

<mark>Now you should be able to view instances in the AWS console.</mark>

<mark>once EC2 is provisioned, you can login and you will be able to see Java, Maven and Jenkins installed in the EC2 instance after the launch.</mark>

**Check the Console Output Logs in the EC2 instance**

Login to an EC2 instance, and type the below command

```bash
tail -f /var/log/cloud-init-output.log
```

This will give the output of the bootstrap execution

Verify if Java got installed.

java -version  
mvn --version

**<mark>Go to the browser and try to access Jenkins in the browser, Jenkins should be coming up.(make sure you open port 8080 in the security rules)</mark>**

![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhoE6-5527pcSmb_Od4gWMxO1exN3PRMAl-xS4xh6Ut6YMRoz2fJeyX_wCPOU4r5FXZY1QgxNQhatnaJvFB4Rj1YTck2b-n1Kd3uJcvOk-onO2Fi1PSvnxg3TW7a6v7B_clDX9pGx4BpZMjdRUHLvurkTJbCEYjyuIAwBfbh4z8IFWkv4EafYZsg5ss/s1958/Screen%20Shot%202022-09-14%20at%208.28.37%20AM.png align="left")

**Enter Jenkins Admin password:**

<mark>Execute the below command as Jenkins user Or admin user to get Jenkins admin password:-</mark>

```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

<mark>Enter the password and click on continue</mark>

<mark>Click on Suggested plug-ins and setup the admin user for Jenkins.</mark>

![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjOuQpQUy2iRqnAnDqbR5gap-rcXUtr7Qu6GpGvFrb9QUfx0heGmUHIEfDBiqnX_DB7iFN21MFGVyYAY5HQ5mY7xpW7ac8jdgj9KtIVbfSTyYCB8vPiUUAeO50gSaXj66e8bVb8Nl9Odu_pJU-HTV5OaXcfkvsvknPWgAzg7ta8wHaRX5yl2LKpu62c/s1930/Screen%20Shot%202022-09-14%20at%208.30.29%20AM.png align="left")

---

# Conclusion

EC2 is popular among Amazon customers because of its quick installations which allow users to access the computing infrastructure within minutes at a low cost. EC2 also lets customers easily increase and decrease their capacity for a long period and has a range of tools to secure data privacy. Finally, EC2 can service customers all around the world.