# How to install Terraform on Ubuntu

---

# What is terraform?

<mark>HashiCorp Terraform is an infrastructure as a code tool that lets you define both cloud and on-prem resources in human-readable configuration files that you can version, reuse, and share.</mark> You can then use a consistent workflow to provision and manage all of your infrastructure throughout its lifecycle. Terraform can manage low-level components like computing, storage, and networking resources, as well as high-level components like DNS entries and SaaS features.

## **How does Terraform work?**

<mark>Terraform creates and manages resources on cloud platforms and other services through its application programming interfaces (APIs). Providers enable Terraform to work with virtually any platform or service with an accessible API.</mark>

![Terraform creates and manages cloud platforms and services through their APIs](https://developer.hashicorp.com/_next/image?url=https%3A%2F%2Fcontent.hashicorp.com%2Fapi%2Fassets%3Fproduct%3Dterraform%26version%3Drefs%252Fheads%252Fv1.3%26asset%3Dwebsite%252Fimg%252Fdocs%252Fintro-terraform-apis.png%26width%3D2048%26height%3D644&w=3840&q=75 align="left")

**<mark>The core Terraform workflow consists of three stages:</mark>**

* **Write:** You define resources, which may be across multiple cloud providers and services. For example, you might create a configuration to deploy an application on virtual machines in a Virtual Private Cloud (VPC) network with security groups and a load balancer.
    
* **Plan:** Terraform creates an execution plan describing the infrastructure it will create, update, or destroy based on the existing infrastructure and your configuration.
    
* **Apply:** On approval, Terraform performs the proposed operations in the correct order, respecting any resource dependencies. For example, if you update the properties of a VPC and change the number of virtual machines in that VPC, Terraform will recreate the VPC before scaling the virtual machines.
    

![The Terraform workflow has three steps: Write, Plan, and Apply](https://developer.hashicorp.com/_next/image?url=https%3A%2F%2Fcontent.hashicorp.com%2Fapi%2Fassets%3Fproduct%3Dterraform%26version%3Drefs%252Fheads%252Fv1.3%26asset%3Dwebsite%252Fimg%252Fdocs%252Fintro-terraform-workflow.png%26width%3D2038%26height%3D1773&w=3840&q=75 align="left")

---

# Terraform Installation on Ubuntu

Terraform is used for provisioning infrastructure on Cloud. you don't need to create manually any resources in AWS.

![](https://1.bp.blogspot.com/-yACcpOTW-c4/YZpxqWQH77I/AAAAAAAAD00/nIsA5GtPvScMj-SeVCLfZ4NBEzGkPhAsQCLcBGAsYHQ/s1284/Screen%2BShot%2B2021-11-21%2Bat%2B10.19.04%2BAM.png align="left")

### **Create a working directory**

```bash
sudo mkdir -p /opt/terraform

cd /opt/terraform
```

### **Download Terraform from Hasicorp website**

```bash
sudo wget https://releases.hashicorp.com/terraform/1.3.7/terraform_1.3.7_linux_386.zip
```

### **Install unzip utility and Unzip Terraform Zip file**

```bash
sudo apt-get install unzip -y

sudo unzip terraform_1.3.7_linux_386.zip
```

### **Add terraform to PATH**

```bash
sudo mv /opt/terraform/terraform /usr/bin/
```

### **Verify Terraform version**

```bash
terraform -version
```

> This should show a version of Terraform