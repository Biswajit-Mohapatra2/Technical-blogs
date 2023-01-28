# How to setup Ansible on Ubuntu

---

# What is Ansible?

Ansible is the #1 configuration management tool. It can also be used for infrastructure provisioning as well. or You can use Ansible in a combination with Terraform which can take care of infra automation and Ansible can do configuration management.

### **Ansible Architecture**

![Basic components of an Ansible environment include a control node, an inventory of managed nodes, and a module copied to each managed node.](https://docs.ansible.com/ansible/latest/_images/ansible_basic.svg align="center")

### **Ansible concepts**

* **Control-Node:**
    
    The machine from which you run the Ansible CLI tools (`ansible-playbook` , `ansible`, `ansible-vault` and others). You can use any computer that meets the software requirements as a control node - laptops, shared desktops, and servers can all run Ansible. Multiple control nodes are possible, but Ansible itself does not coordinate across them, see `AAP(`Ansible Automation Platform`)`for such features.
    
* **Managed Node:**
    
    Also referred to as ‘hosts’, these are the target devices (servers, network appliances or any computer) you aim to manage with Ansible. Ansible is not normally installed on managed nodes unless you are using `ansible-pull`, but this is rare and not the recommended setup.
    
* **Inventory**:
    
    A list of managed nodes provided by one or more ‘inventory sources’. Your inventory can specify information specific to each node, like IP address. It is also used for assigning groups, which both allow for node selection in the Play and bulk variable assignment. Sometimes an inventory source file is also referred to as a ‘hostfile’.
    
* **Playbooks:**
    
    They contain Plays (which are the basic unit of Ansible execution). This is both an ‘execution concept’ and how we describe the files on which `ansible-playbook` operates. Playbooks are written in YAML and are easy to read, write, share and understand.
    
* **Modules:**
    
    The code or binaries that Ansible copies to and executes on each managed node (when needed) to accomplish the action defined in each Task. Each module has a particular use, from administering users on a specific type of database to managing VLAN interfaces on a specific type of network device. You can invoke a single module with a task, or invoke several different modules in a playbook. Ansible modules are grouped in collections.
    

<mark>The best way to install Ansible for Ubuntu is to add the </mark> **<mark>project's PPA (personal package archive)</mark>** <mark>to your system</mark>. <mark>You also would need the Boto framework for provisioning resources in the AWS cloud</mark>.

![](https://1.bp.blogspot.com/-ZDtWSyXtIcU/XqYSWx1n_fI/AAAAAAAACAU/InaCcAVwuL0kMR4vcpHkN90mi5RSRlADQCLcBGAsYHQ/s1600/ansible-boto.png align="center")

# ***Pre-requisites:***

<mark>Create a new Ubuntu EC2 instance for installing Ansible, just open port 22.</mark>

**<mark>Update the Repository by including the official project’s PPA(personal package archive):</mark>**

```bash
sudo apt update -y

sudo apt-add-repository -y ppa:ansible/ansible
```

![](https://1.bp.blogspot.com/-1NWUMtdkXis/XOr6syEroeI/AAAAAAAABFw/2hGPrOYoF4U3SqfhpwzEqZ4a0NZfJ0qqgCLcBGAs/s1600/Screen%2BShot%2B2019-05-26%2Bat%2B3.44.00%2BPM.png align="center")

<mark>Then you need to refresh the package by executing the below command:</mark>

```bash
sudo apt update -y
```

![](https://1.bp.blogspot.com/-8hUp4IQW4M0/XOr68_olmWI/AAAAAAAABF0/LKwwsAIG-lcBmo61airkcSgmi7har0JOwCLcBGAs/s1600/Screen%2BShot%2B2019-05-26%2Bat%2B3.45.11%2BPM.png align="center")

---

# **Now let's install Ansible:**

<mark>Now install ansible by executing the below command:</mark>

```bash
sudo apt install ansible -y
```

<mark>Then install Package manager for python:</mark>

```bash
sudo apt install python-pip -y
```

### **Install Boto Framework - AWS SDK**

```python
sudo pip install boto boto3
```

<mark>Ansible will access AWS resources using boto SDK</mark>.

```bash
sudo apt install python-boto -y

pip list boto | grep boto
```

![](https://1.bp.blogspot.com/-z3USkUQnzXg/X5seYZNNWGI/AAAAAAAADG0/QEMr-UGgH-0nt4eHugyhRpCQSaIWlZwIACLcBGAsYHQ/s1020/pip%2Blist.png align="center")

**<mark>Ignore the warning in Red color</mark>**<mark>.</mark>

<mark>Now check the version of the ansible by executing the below command</mark>:

```bash
ansible --version
```

![](https://1.bp.blogspot.com/-ZdFH2rj4t1A/X5sd5x1dghI/AAAAAAAADGs/aIN_go_XSEIbNXWsRizAPdG4q_s9XclXgCLcBGAsYHQ/s1624/ansible%2Bv.png align="center")

---

# Conclusion:

As a last thought, I conclude that Ansible exists to offer a straightforward and effective package for configuration management and automation. Being new to the software application market, Ansible faces tough competition from renowned sources.

In this article, I have tried my best to cover as maximum as possible important aspects of Ansible to make you aware of this technology in the best possible way.