# How to create EC2 instance using Terraform

---

# What is Terraform?

<mark>Terraform is an open-source tool for provisioning and managing cloud infrastructure. Terraform can provision resources on any cloud platform.&nbsp;</mark> 

<mark>Terraform allows you to create infrastructure in configuration files(tf files) that describe the topology of cloud resources</mark>. These resources include virtual machines, storage accounts, networking interfaces, etc.

![](https://1.bp.blogspot.com/-cArJQhhGfbU/YOdHPQMw_SI/AAAAAAAADko/RKJ-UWUiO9gzwvOBzi6cHqMv8U7q9q3GQCLcBGAsYHQ/s556/Screen%2BShot%2B2021-07-08%2Bat%2B1.42.54%2BPM.png align="center")

# **Pre-requisites:**

* Create an EC2 instance Manually for provisioning the infrastructure using terraform.
    
* Install [Terraform](https://biswajitblogs.hashnode.dev/how-to-install-terraform-on-ubuntu) on your EC2 instance
    
* You can provision resources in the AWS cloud using Terraform in two ways as mentioned below:
    
    1. <mark>AWS Access keys + secret keys (un-secure way)</mark>
        
    2. <mark>IAM Role with AmazonEC2FullAccess Policy. (more secure way)</mark>
        
* **Option 2** is recommended approach as we already installed Terraform on the EC2 instance that is inside the AWS cloud. So we do not need Access Keys + secret keys. <mark>But if you have installed Terraform on your local machine you would need to go with </mark> **<mark>Option 1</mark>**.
    

---

# Let's create AWS EC2 using Terraform

We will see how you can use Terraform to provision an EC2 instance. Please do the below steps for provisioning EC2 instances on AWS:-

### **Step - 1:  Create an IAM role to provision EC2 instance in AWS**

<mark>Go to the AWS console, click on IAM</mark>

![](https://1.bp.blogspot.com/-RReZ721F47U/YN4VcT0W_wI/AAAAAAAADho/HvDpUvjVlkgexsJG37ydLzmxEAksb6BmgCLcBGAsYHQ/s574/Screen%2BShot%2B2021-07-01%2Bat%2B2.19.46%2BPM.png align="center")

<mark>Select AWS service, EC2, and Click on Next Permissions</mark>

![](https://1.bp.blogspot.com/-so95vdebnHo/YN4Vs-JvsiI/AAAAAAAADh0/7fW7oYUeamkQ4-XqYPP_DhacwtTfH1hUgCLcBGAsYHQ/s413/Screen%2BShot%2B2021-07-01%2Bat%2B2.20.54%2BPM.png align="center")

<mark>Type EC2 and choose AmazonEC2FullAccess as policy</mark>

![](https://1.bp.blogspot.com/-N5WAsTdJXmQ/YN4WVYtxqyI/AAAAAAAADh8/54dtVBMGD1oZB6Zgpc1iXPbEddtRRCN-ACLcBGAsYHQ/s563/Screen%2BShot%2B2021-07-01%2Bat%2B2.22.37%2BPM.png align="center")

<mark>Click on Next tags, Next Review give some role name and click on Create role</mark>

![](https://1.bp.blogspot.com/-bHqUL05B67w/YN4XEx8luEI/AAAAAAAADiE/RlC4wVm33d8Y1NxMXd8VqYG0On07Za8WQCLcBGAsYHQ/s984/Screen%2BShot%2B2021-07-01%2Bat%2B2.26.40%2BPM.png align="center")

### **Step - 2: Assign the IAM role to an EC2 instance**

<mark>Go back to the EC2 instance, click on the EC2 instance, Security, Modify IAM role</mark>

![](https://1.bp.blogspot.com/-wK_9Gne-oM0/YN4XnTlzI5I/AAAAAAAADiM/z_aOKlSVQY8R5moffL7xgNQL29mkn0dHwCLcBGAsYHQ/s521/Screen%2BShot%2B2021-07-01%2Bat%2B2.28.41%2BPM.png align="center")

<mark>Type your IAM role name&nbsp;</mark> *<mark>my-ec2-terraform-role</mark>* <mark>&nbsp;and Save it to attach that role to the EC2 instance.</mark>

![](https://1.bp.blogspot.com/-10qb_l7RARQ/YN4YZoCZLII/AAAAAAAADiU/opRm4M_jW6U_lK4rJQVRJoyYjJMgUI81QCLcBGAsYHQ/s789/Screen%2BShot%2B2021-07-01%2Bat%2B2.32.15%2BPM.png align="center")

<mark>Login to the EC2 instance where you have installed Terraform</mark>.

### **Step 3:- Create Terraform files**

<mark>Creating separate directory for terraform files.</mark>

```bash
cd ~

mkdir project-terraform

cd project-terraform
```

**Create Terraform Files:**

make sure you change whatever is covering <mark>Square Bracket</mark> below per your settings.

```bash
sudo vi variables. tf

variable "aws_region" {
       description = "The AWS region to create things in." 
       default     = ["us-east-2"]  #You Can Change Whatever region you want
}

variable "key_name" { 
    description = " SSH keys to connect to ec2 instance" 
    default     =  ["myJan26Key"] #You Can Change Whatever key name U want
}

variable "instance_type" { 
    description = "instance type for ec2" 
    default     =  "t2.micro" 
}

variable "security_group" { 
    description = "Name of security group" 
    default     = "my-jenkins-security-group-2022" 
}

variable "tag_name" { 
    description = "Tag Name of for Ec2 instance" 
    default     = "my-ec2-instance" 
} 
variable "ami_id" { 
    description = "AMI for Ubuntu Ec2 instance" 
    default     = ["ami-0b9064170e32bde34"] #Write Your own AMI-ID
}

#Make sure after your custom changes there is no need for square bracket, i only give it for understanding the concept..
```

<mark>Save the file with </mark> **<mark>ESC </mark>** <mark>then</mark> **<mark> :wq!</mark>** <mark> Command</mark>.

**<mark>Now create main.tf file</mark>**

```bash
sudo vi main.tf

provider "aws" {
  region = var.aws_region
}

resource "aws_vpc" "main" {
  cidr_block = "172.16.0.0/16"
  instance_tenancy = "default"
  tags = {
    Name = "main"
  }
}


#Create security group with firewall rules
resource "aws_security_group" "jenkins-sg-2022" {
  name        = var.security_group
  description = "security group for jenkins"

  ingress {
    from_port   = 8080
    to_port     = 8080
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }

 ingress {
    from_port   = 22
    to_port     = 22
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }

 # outbound rule
  egress {
    from_port   = 0
    to_port     = 65535
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }

  tags= {
    Name = var.security_group
  }
}

resource "aws_instance" "myFirstInstance" {
  ami           = var.ami_id
  key_name = var.key_name
  instance_type = var.instance_type
  vpc_security_group_ids = [aws_security_group.jenkins-sg-2022.id]
  tags= {
    Name = var.tag_name
  }
}

# Create Elastic IP address
resource "aws_eip" "myElasticIP" {
  vpc      = true
  instance = aws_instance.myFirstInstance.id
tags= {
    Name = "jenkins_elastic_ip"
  }
}
```

<mark>Save the file with </mark> **<mark>ESC</mark>** <mark> then </mark> **<mark>:wq!</mark>** <mark> Command</mark>.

### **Step 4:- Execute Terraform Commands**

<mark>Now execute the below command:</mark>

```bash
terraform init
```

![](https://1.bp.blogspot.com/-jpncNag0bQ0/XoYyKNXYKFI/AAAAAAAABrE/LcjGZffvBxcpyimBwGT5pMtBy5v2l0jkgCLcBGAsYHQ/s1600/init.png align="center")

<mark>Execute the below command:</mark>

```bash
terraform plan
```

<mark>the above command will show how many resources will be added.</mark>

**<mark>Plan: 4 to add, 0 to change, 0 to destroy</mark>**

Do you want to perform these actions?  
  Terraform will perform the actions described above.  
  Only 'yes' will be accepted to approve.  
  
  Enter a value: **<mark>yes</mark>**  
Apply complete! Resources: 4 added, 0 changed, 0 destroyed.

**Next, apply the changes to your AWS environment:**

```bash
terraform apply --auto-approve
```

**<mark>Now login to the EC2 console, to see the new instances up and running.</mark>**

**List Resources created by Terraform:-**

<mark>Execute the below command to view a list of the resources created by Terraform</mark>.

```bash
terraform state list
```

![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjcrUqeD0iOYMBjTe7yxKm36uC2NwJhWRdBF-gVqKBGC8yy7revvCxE1IPv5uF1cb8uHbuKa0zMXPHQo8ngTi9T5mhwVIq_w-0-uC3bV0kMgcxmBgec2pkFzV3wXSYAWawxwIYf1ZxaEJv9GvoA0ztL-aqoQzFVuVefIsCXeO_IrMGyNWr8H75HhkKB/s1354/Screen%20Shot%202022-09-13%20at%2011.34.16%20PM.png align="center")

<mark>You should be able to see the EC2 instance up and running in AWS console.</mark>

---

# **How to push Terraform files into GitHub?**

All Terraform files should be checked into version control systems such as GitHub, BitBucket or GitLab. Let us see how to push code changes into GitHub. Make sure you are in the directory where Terraform files are created.

### **Create Remote repo on GitHub**

Create a new repo with the below name, make sure it is a private repo. Also do not click on initialize this repository with a README option.

![](https://1.bp.blogspot.com/-5ogmJN0mSmM/XnGK--psQxI/AAAAAAAABgw/eNm-c-4iY-cpscM7clRLTdkTD8fwJwS_wCLcBGAsYHQ/s1600/create%2Binfra%2Brepo.png align="center")

<mark>Note down the remote URL as highlighted below</mark>:

![](https://1.bp.blogspot.com/-Y_YS4k53tAE/XnGNKPSc52I/AAAAAAAABhM/Vew0A8bmwb0J_I_Pm14OwtvrHria80JbQCLcBGAsYHQ/s1600/add%2Bremote%2Brepo.png align="center")

**Note:**  
<mark>If you have any issues in uploading .tf files, you may not have created ssh-keys and uploaded them into GitHub. Create ssh keys using the ssh-keygen command:</mark>

```bash
ssh-keygen
```

<mark>This should generate both public and private keys.</mark>

<mark>Copy the public keys by executing the below command:</mark>

```bash
sudo cat ~/.ssh/id_rsa.pub
```

### **Initialize the directory first**

```bash
git init .
```

<mark>The above command will create a local git repository.<br>Now add terraform files.</mark>

```bash
git add *.tf
```

<mark>Then commit it with the below command:</mark>

```bash
git commit -m "Added terraform files"
```

<mark>Add Your remote repository URL with the local repo and execute the below command:</mark>

```bash
git remote add origin <your remote repo URL>
```

### **Now push the code into GitHub**

```bash
git push -u origin master
```

**<mark>Now Login to GitHub to view the Terraform files</mark>**

<mark>You may get this error if you have not uploaded ssh keys into GitHub/BitBucket.</mark>

![](https://1.bp.blogspot.com/-FB_tYIJagCo/YOcuxCvggYI/AAAAAAAADkQ/nwhj2BtYzccClOtiK7c13oqnOt-LvND_ACLcBGAsYHQ/s831/Screen%2BShot%2B2021-07-08%2Bat%2B11.57.13%2BAM.png align="center")

**So make sure you upload SSH keys into your SCM.**

---

# Conclusion

Terraform makes it easy for administrators to provision cloud resources in AWS. Using Terraform’s command files, you can automate provisioning to reduce the overhead of manually creating instances in the AWS dashboard.

---