# Networking Interview
Questions

---

## Basic Networking Interview Questions

### 1\. What is the network?

A network is usually an **informally interconnected group** or association of different entities like a person, computers, radio stations, etc.

For example, Dominos has a network of 1232 branches across India. As the name suggests the computer network is a system of peripherals or computers interconnected with each other and has a standard communication channel established between them to exchange different types of information and data.

### 2\. Explain different types of networks.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674049131489/2224720f-589e-4478-bc74-0ca57753c4f3.png align="center")

### 3\. Explain LAN (Local Area Network)

**LANs** are widely used to connect computers/laptops and consumer electronics which enables them to share resources (e.g., printers, fax machines) and exchange information. When LANs are used by companies or organizations, they are called **enterprise networks**. There are two different types of LAN networks i.e. wireless LAN (no wires involved achieved using Wi-Fi) and wired LAN (achieved using LAN cable). Wireless LANs are very popular these days for places where installing wire is difficult. The below diagrams explain both wireless and wired LAN.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674049347626/25a44cda-88cb-4710-a5fb-512a5e4937fe.png align="center")

### 4\. What is VPN (Virtual Private Network) and What are the advantages of using a VPN?

VPN or the Virtual Private Network is a private WAN (Wide Area Network) built on the internet. It allows the creation of a secured tunnel (protected network) between different networks using the internet (public network). By using the VPN, a client can connect to the organization’s network remotely.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674049485403/281a1c9c-6a93-4f3c-a4ff-9e9702179937.png align="center")

Below are a few advantages of using a VPN:

* VPN is used to connect offices in different geographical locations remotely and is cheaper when compared to WAN connections.
    
* VPN is used for secure transactions and confidential data transfer between multiple offices located in different geographical locations.
    
* VPN keeps an organization’s information secured against any potential threats or intrusions by using virtualization.
    
* VPN encrypts the internet traffic and disguises the online identity.
    

### 5\. What is the network topology? Define different types of network topology

Network topology is a physical layout of the network, connecting the different nodes using the links. It depicts the connectivity between the computers, devices, cables, etc.

**The different types of network topology are:**

**Bus Topology:**

* All the nodes are connected using the central link known as the bus.
    
* It is useful to connect a smaller number of devices.
    
* If the main cable gets damaged, it will damage the whole network.
    
    ![Bus Topology](https://cdn.hashnode.com/res/hashnode/image/upload/v1674049842693/d4589e63-682a-4ee0-af9f-c480150abb5f.png align="center")
    
    **Star Topology:**
    
* All the nodes are connected to one single node known as the central node.
    
* It is more robust.
    
* If the central node fails the complete network is damaged.
    
* Easy to troubleshoot.
    
* Mainly used in home and office networks.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674050029361/f9605d7b-1753-4bac-8cb7-4cc6876eb6e1.png align="center")
    
    **Ring Topology:**
    
* Each node is connected to exactly two nodes forming a ring structure.
    
* If one of the nodes is damaged, it will damage the whole network.
    
* It is used very rarely as it is expensive and hard to install and manage.
    
    ![Ring Topology](https://cdn.hashnode.com/res/hashnode/image/upload/v1674050181458/1e0feaa1-59f5-4e87-87de-18144321a7b9.png align="center")
    
    **Mesh Topology:**
    
* Each node is connected to one or many nodes.
    
* It is robust as failure in one link only disconnects that node.
    
* It is rarely used and installation and management are difficult.
    
    ![Mesh Topology](https://cdn.hashnode.com/res/hashnode/image/upload/v1674050306014/582b7c8d-d849-4fa9-8f63-103548a1d7ea.png align="center")
    
    **Tree Topology:**
    
* A combination of star and bus topology also know as an extended bus topology.
    
* All the smaller star networks are connected to a single bus.
    
* If the main bus fails, the whole network is damaged.
    
    ![Tree Topology](https://cdn.hashnode.com/res/hashnode/image/upload/v1674050442600/976aae52-f4c2-4411-b787-d56cda6a2042.png align="center")
    
    **Hybrid:**
    
* It is a combination of different topologies to form a new topology.
    
* It helps to ignore the drawback of a particular topology and helps to pick the strengths from others.
    
    ### 6\. What is an IPv4 address? What are the different classes of IPv4?
    
    <mark>An IP address is a 32-bit dynamic address of a node in the network. An IPv4 address has 4 octets of 8-bit each with each number with a value up to 255</mark>.
    
    IPv4 classes are differentiated based on the number of hosts it supports on the network. There are five types of IPv4 classes and are based on the first octet of IP addresses which are classified as <mark>Class A, B, C, D, or E</mark>.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674059171861/5809e09a-a24f-4a3b-bf9b-4f22a457040e.png align="center")

### 7\. What are Private and Special IP addresses?

**Private Address:** For each class, there are specific IPs that are reserved specifically for private use only. This IP address cannot be used for devices on the Internet as they are non-routable.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674051871037/ca738c62-6b18-4027-9b2b-7fc65b751875.png align="center")

**Special Address:** IP Range from 127.0.0.1 to 127.255.255.255 are network testing addresses also known as loopback addresses are a special IP address.

### 8\. What are the different types of VPNs?

A few types of VPNs are:

* **Access VPN:** Access VPN is used to provide connectivity to remote mobile users and telecommuters. It serves as an alternative to dial-up connections or ISDN (Integrated Services Digital Network) connections. It is a low-cost solution and provides a wide range of connectivity.
    
* **Site-to-Site VPN:** A Site-to-Site or Router-to-Router VPN is commonly used in large companies having branches in different locations to connect the network of one office to another in different locations. There are 2 sub-categories:
    
* **Intranet VPN**: Intranet VPN is useful for connecting remote offices in different geographical locations using shared infrastructure (internet connectivity and servers) with the same accessibility policies as a private WAN (wide area network).
    
* **Extranet VPN:** Extranet VPN uses shared infrastructure over an intranet, suppliers, customers, partners, and other entities and connects them using dedicated connections.
    

### 9\. What are nodes and links?

**Node:** Any communicating device in a network is called a Node. The node is the point of intersection in a network. It can send/receive data and information within a network. Examples of the node can be computers, laptops, printers, servers, modems, etc.

**Link:** A link or edge refers to the connectivity between two nodes in the network. It includes the type of connectivity (wired or wireless) between the nodes and protocols used for one node to be able to communicate with the other.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674052264625/5492bdd3-3bfb-42f3-85e8-2e9c28e92045.png align="center")

## Intermediate Interview Questions

### 1\. Describe the OSI Reference Model

Open System Interconnections (OSI) is a network architecture model based on the ISO standards. It is called the OSI model as it deals with connecting the systems that are open for communication with other systems.

The OSI model has seven layers.

* Create a new layer if a different abstraction is needed.
    
* Each layer should have a well-defined function.
    
* The function of each layer is chosen based on internationally standardized protocols.
    

### 2\. Define the 7 different layers of the OSI Reference Model

Here are the 7 layers of the OSI reference model:

![OSI Layers](https://cdn.hashnode.com/res/hashnode/image/upload/v1674054810607/27deba67-7bc6-499c-aad2-5cbbb430e223.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674055061219/cf087a18-dd55-44cc-9daa-70fd52d7bd51.png align="right")

### 3\. Describe the TCP/IP Reference Model

It is a compressed version of the OSI model with only 4 layers. It was developed by the US Department of Defence (DoD) in the 1860s. The name of this model is based on 2 standard protocols used i.e. TCP (Transmission Control Protocol) and IP (Internet Protocol).

### 4\. Define the 4 different layers of the TCP/IP Reference Model

<table><tbody><tr><td colspan="1" rowspan="1"><p><strong>Layers</strong></p></td><td colspan="1" rowspan="1"><p><strong>Description</strong></p></td></tr><tr><td colspan="1" rowspan="1"><p>DataLink</p></td><td colspan="1" rowspan="1"><p>Decides which links such as serial lines or classic Ethernet must be used to meet the needs of the connectionless internet layer.</p></td></tr><tr><td colspan="1" rowspan="1"><p>Internet</p></td><td colspan="1" rowspan="1"><p>The internet layer is the most important layer which holds the whole architecture together. It delivers the IP packets where they are supposed to be delivered.</p></td></tr><tr><td colspan="1" rowspan="1"><p>Transport</p></td><td colspan="1" rowspan="1"><p>Its functionality is almost the same as the OSI transport layer. It enables peer entities on the network to carry on a conversation.</p></td></tr><tr><td colspan="1" rowspan="1"><p>Application</p></td><td colspan="1" rowspan="1"><p>It contains all the higher-level protocols.</p></td></tr></tbody></table>

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674055565536/9cfee06b-5932-460d-8794-62a05eb748ea.png align="center")

### 5\. Differentiate OSI Reference Model And TCP/IP Reference Model

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674055710127/97bcc484-b9c7-4c3d-b0ad-f055f43e9b05.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674055775313/9bafb4d4-4ce3-401d-9e4b-7276d26dfdf0.png align="center")

### 6\. What are the HTTP and the HTTPS protocol?

**HTTP** is the HyperText Transfer Protocol which defines the set of rules and standards on how information can be transmitted on the World Wide Web (WWW). <mark>It helps web browsers and web servers communicate</mark>. <mark>It is a ‘stateless protocol’ where each command is independent of the previous command</mark>. <mark>HTTP is an application layer protocol built upon the TCP. It uses port 80 by default</mark>.

**HTTPS** is the HyperText Transfer Protocol Secure or Secure HTTP. It is an advanced and secure version of HTTP. On top of HTTP, SSL/TLS protocol is used to provide security. It enables secure transactions by encrypting communication and also helps identify network servers securely. It uses port 443 by default.

### 7\. What is the SMTP protocol?

SMTP is the **Simple Mail Transfer Protocol**. <mark>SMTP sets the rule for communication between servers. This set of rules helps the software transmit emails over the internet</mark>. It supports both End-to-End and Store-and-Forward methods. It is in always-listening mode on port 25.

![SMTP Protocol](https://cdn.hashnode.com/res/hashnode/image/upload/v1674056097987/48e204bf-feac-48a4-a4ce-98beba586656.png align="center")

### 8\. What is DNS?

DNS is the **Domain Name System**. <mark>It is considered the devices/services directory of the Internet.</mark> It is a decentralized and hierarchical naming system for devices/services connected to the Internet. It translates the domain names to their corresponding IPs. For e.g. [BiswajitMohapatra.com](http://interviewbit.com) to 172.217.164.16. <mark>It uses port 53 by default</mark>.

### 9\. What is the use of a router and how is it different from a gateway?

<mark>The </mark> **<mark>router</mark>** <mark> is a networking device used for connecting two or more network segments. It directs the traffic in the network. It transfers information and data like web pages, emails, images, videos, etc</mark>. from source to destination in the form of packets. It operates at the network layer. <mark>The </mark> **<mark>gateways</mark>** <mark> are also used to route and regulate the network traffic but, they can also send data between two dissimilar networks while a router can only send data to similar networks</mark>.

## Advanced Interview Questions

### 1\. What is the TCP protocol?

**<mark>TCP or TCP/IP</mark>** <mark> is the Transmission Control Protocol/Internet Protocol. It is a set of rules that decides how a computer connects to the Internet and how to transmit the data over the network</mark>. It creates a virtual network when more than one computer is connected to the network and uses the three ways handshake model to establish the connection which makes it more reliable.

### 2\. What is the UDP protocol?

**<mark>UDP</mark>** <mark> is the </mark> **<mark>User Datagram Protocol</mark>** <mark> and is based on Datagrams. Mainly, it is used for multicasting and broadcasting.</mark> Its functionality is almost the same as TCP/IP Protocol except for the three ways of handshaking and error checking. It uses a simple transmission without any hand-shaking which makes it less reliable.

### 3\. Compare TCP and UDP

![Comparison Between TCP/IP And UDP](https://cdn.hashnode.com/res/hashnode/image/upload/v1674056650756/284dcc9b-9b52-4db3-aeb4-6e8093525912.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674056807775/c13b5f38-a2c7-42cf-8683-77f009a9624e.png align="center")

### 4\. What is the ICMP protocol?

**<mark>ICMP</mark>** <mark> is the Internet Control Message Protocol. It is a network layer protocol used for error handling.</mark> It is mainly used by network devices like routers for diagnosing network connection issues and is crucial for error reporting and testing if the data is reaching the preferred destination in time. **<mark>It uses port 7 by default.</mark>**

### 5\. What do you mean by the DHCP Protocol?

DHCP is the **<mark>Dynamic Host Configuration Protocol</mark>**.

<mark>It is an application layer protocol used to auto-configure devices on IP networks enabling them to use TCP and UDP-based protocols.</mark> The DHCP servers auto-assign the IPs and other network configurations to the devices individually which enables them to communicate over the IP network. It helps to get the subnet mask, and IP address and helps to resolve the DNS. **<mark>It uses port 67 by default.</mark>**

### 6\. What is the ARP protocol?

ARP is **<mark>Address Resolution Protocol.</mark>** <mark>It is a network-level protocol used to convert the logical address i.e. IP address to the device's physical address i.e. MAC address</mark>. It can also be used to get the MAC address of devices when they are trying to communicate over the local network.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674057235388/7856e550-e5e9-4a79-8ecd-7cdd2f617508.png align="center")

### 7\. What is the FTP protocol?

FTP is a **<mark>File Transfer Protocol.</mark>** It is an application layer protocol used to transfer files and data reliably and efficiently between hosts. It can also be used to download files from remote servers to your computer. <mark>It uses port 27 by default</mark>.

### 8\. What is the MAC address and how is it related to NIC?

MAC address is the **<mark>Media Access Control address</mark>**. It is a 48-bit or 64-bit unique identifier of devices in the network. <mark>It is also called the physical address embedded with Network Interface Card (NIC) used at the Data Link Layer.</mark> NIC is a hardware component in the networking device using which a device can connect to the network.

### 9\. Differentiate the MAC address from the IP address

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674057502328/ec50a862-c7f5-4db6-aca8-b31bfd826ee7.png align="center")

### 10\. What is a subnet?

<mark>A subnet is a network inside a network achieved by the process called subnetting which helps divide a network into subnets</mark>. It is used for getting a higher routing efficiency and enhances the security of the network. It reduces the time to extract the host address from the routing table.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674057650644/2d6519da-2489-4437-9980-83fe0e69eb40.png align="center")

### 11\. Compare the hub vs switch

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674057715565/97ac5633-f36e-4f54-92c3-0775c1b80013.png align="center")

### 12\. What is the difference between the ipconfig and the ifconfig?

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674057833147/4b1ea4ce-de19-43f0-bd7f-e2ad4ce8eb83.png align="center")

### 13\. What is the firewall?

<mark>The firewall is a network security system that is used to monitor incoming and outgoing traffic and blocks the same based on firewall security policies</mark>. It acts as a wall between the internet (a public network) and the networking devices (a private network). It is either a hardware device, a software program, or a combination of both.

It adds a layer of security to the network.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674057970940/405ffd02-d064-4846-9358-0ad701d633ad.png align="center")

### 14\. What are Unicasting, Anycasting, Multicasting and Broadcasting?

* **Unicasting:** <mark>If the message is sent to a single node from the source then it is known as unicasting</mark>. This is commonly used in networks to establish a new connection.
    
* **Anycasting:** <mark>If the message is sent to any of the nodes from the source then it is known as anycasting</mark>. It is mainly used to get the content from any of the servers in the Content Delivery System.
    
* **Multicasting:** <mark> If the message is sent to a subset of nodes from the source then it is known as multicasting</mark>. Used to send the same data to multiple receivers.
    
* **Broadcasting:** <mark>If the message is sent to all the nodes in a network from a source then it is known as broadcasting</mark>. DHCP and ARP in the local network use broadcasting.
    

### 15\. What happens when you enter [google.com](http://google.com) in the web browser?

* Check the browser cache first if the content is fresh and present in the cache display the same.
    
* If not, the browser checks if the IP of the URL is present in the cache (browser and OS) if not then request the OS to do a DNS lookup using UDP to get the corresponding IP address of the URL from the DNS server to establish a new TCP connection.
    
* A new TCP connection is set between the browser and the server using three- way handshaking.
    
* An HTTP request is sent to the server using the TCP connection.
    
* The web servers running on the Servers handle the incoming HTTP request and send the HTTP response.
    
* The browser process the HTTP response sent by the server and may close the TCP connection or reuse the same for future requests.
    
* If the response data is cacheable then browsers cache the same.
    
* The browser decodes the response and renders the content.
    

---

# Conclusion

In today’s world, it is very hard to stay away from the Internet and that is what makes networking one of the most important interview topics. As of 2022 if we check the facts, there is a total of 1.3 million kilometers of submarine optical fiber cables set globally to connect the world to the Internet. These cables are more than enough to revolve around the earth more than 100 times.