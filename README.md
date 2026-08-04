# Cloud Infrastructure - Complete Viva Study Material 🎓

---

## UNIT 1: CLOUD COMPUTING BASICS

### What is Cloud Computing?
Cloud computing is the delivery of computing services like servers, storage, databases, networking, software over the internet ("the cloud") instead of using your own physical hardware.

**Simple answer:** "Using someone else's computers over the internet to store, manage and process data."

---

### Why Cloud Computing?
- No need to buy expensive hardware
- Pay only for what you use
- Access from anywhere
- Scale up or down easily
- High availability and reliability

---

### Characteristics of Cloud Computing (5 essential)
| # | Characteristic | Meaning |
|---|---------------|---------|
| 1 | On-demand self service | Use resources anytime without human interaction |
| 2 | Broad network access | Access from any device anywhere |
| 3 | Resource pooling | Multiple users share same physical resources |
| 4 | Rapid elasticity | Scale up/down instantly based on need |
| 5 | Measured service | Pay only for what you use |

---

### Types of Cloud
| Type | Meaning | Example |
|------|---------|---------|
| Public Cloud | Owned by third party, shared by everyone | AWS, Azure, Google Cloud |
| Private Cloud | Owned and used by single organization | Company's own data center |
| Hybrid Cloud | Mix of public and private | Hospital uses private for patient data, public for website |
| Community Cloud | Shared by specific community | Government departments sharing |

---

### Service Models
| Model | Full Form | What it provides | Example |
|-------|-----------|-----------------|---------|
| IaaS | Infrastructure as a Service | Virtual machines, storage, networking | AWS EC2, S3 |
| PaaS | Platform as a Service | Platform to develop and deploy apps | Google App Engine |
| SaaS | Software as a Service | Ready-to-use software over internet | Gmail, Zoom, Netflix |

**Easy memory trick:** IaaS = Infrastructure (hardware level), PaaS = Platform (developer level), SaaS = Software (user level)

---

### Advantages of Cloud
- Cost saving (no hardware purchase)
- Flexibility and scalability
- Disaster recovery
- Automatic updates
- Collaboration anywhere

### Disadvantages of Cloud
- Internet dependency
- Security concerns
- Vendor lock-in
- Limited control

---

## UNIT 2: VIRTUALIZATION

### What is Virtualization?
Virtualization is the process of creating a virtual (software-based) version of something - like a virtual computer, server, storage, or network - on top of a physical machine.

**Simple answer:** "Running multiple virtual machines on one physical machine."

---

### Key Terms
| Term | Meaning |
|------|---------|
| Host Machine | The physical computer running virtualization software |
| Guest Machine | The virtual machine running inside the host |
| Hypervisor | Software that creates and manages virtual machines |
| VM (Virtual Machine) | A software computer that runs like a real computer |

---

### Types of Hypervisor
| Type | Name | How it works | Example |
|------|------|-------------|---------|
| Type 1 | Bare Metal | Runs directly on hardware | VMware ESXi, Microsoft Hyper-V |
| Type 2 | Hosted | Runs on top of OS | Oracle VirtualBox, VMware Workstation |

**Your experiment used:** Oracle VirtualBox = Type 2 Hypervisor

---

### Types of Virtualization
- **Server Virtualization** - Multiple virtual servers on one physical server
- **Storage Virtualization** - Pooling physical storage from multiple devices
- **Network Virtualization** - Creating virtual networks
- **Desktop Virtualization** - Running desktop OS virtually

---

### Benefits of Virtualization
- Better hardware utilization
- Cost reduction
- Easy backup and recovery
- Isolation between VMs
- Test environments without extra hardware

---

## UNIT 3: ORACLE VIRTUALBOX & VM NETWORKING

### What is Oracle VirtualBox?
Oracle VirtualBox is a free, open-source Type 2 hypervisor that allows you to run multiple operating systems on your computer simultaneously.

---

### Network Adapter Types in VirtualBox
| Mode | How it works | Use case |
|------|-------------|---------|
| NAT | VM shares host's IP, can access internet but not reachable from outside | Default, internet access |
| Bridged | VM gets its own IP on same network as host | VM acts like separate machine on LAN |
| Host-Only | VM can only talk to host, not internet | Testing between host and VM |
| Internal | VMs can talk to each other only | Isolated network testing |

---

### Your VM Experiment Explained
**What you did:**
1. Created 2 VMs in VirtualBox - **047_KaliLinux** and **047_Shyam Prasath S**
2. Both configured with NAT + Intel PRO/1000 MT Desktop adapter
3. Ran `ifconfig` in Kali Linux - saw eth0 and eth1 interfaces
4. Ran `ipconfig` in Windows host - saw VirtualBox host-only adapter IP 192.168.56.1
5. Pinged 192.168.56.1 from Windows - 4 replies, 0% packet loss
6. Pinged 192.168.56.1 from Kali Linux - 4 replies, 0% packet loss

**What it proves:** Guest VM and Host machine can communicate over the network ✅

---

### Important Commands
| Command | OS | Purpose |
|---------|-----|---------|
| `ifconfig` | Linux/Kali | Shows network interfaces and IP addresses |
| `ipconfig` | Windows | Shows IP configuration |
| `ping -n 4 192.168.56.1` | Windows | Ping 4 times to test connectivity |
| `ping 192.168.56.1` | Linux | Ping to test connectivity |

---

### Viva Q&A - VM Networking
**Q: What is NAT in networking?**
A: NAT stands for Network Address Translation. It allows the VM to share the host machine's IP address to access the internet, but the VM is not directly reachable from outside.

**Q: What is the difference between NAT and Bridged?**
A: NAT shares host's IP (VM hidden behind host). Bridged gives VM its own IP on the same network (VM visible as separate device).

**Q: What is ifconfig?**
A: ifconfig (interface configuration) is a Linux command used to display and configure network interfaces including IP address, netmask, and MAC address.

**Q: What is 192.168.56.1?**
A: It is the default IP address of the VirtualBox host-only network adapter on the Windows host machine.

**Q: What does 0% packet loss mean?**
A: It means all ping packets sent were received successfully - perfect network connectivity with no data loss.

---

## UNIT 4: AMAZON WEB SERVICES (AWS)

### What is AWS?
Amazon Web Services is a cloud computing platform provided by Amazon that offers over 200 services including computing, storage, databases, networking, AI, and more.

**AWS is an example of:** Public Cloud + IaaS + PaaS + SaaS

---

### Core AWS Services (for your exam)

#### Amazon EC2 (Elastic Compute Cloud)
- Virtual servers in the cloud
- You choose OS, CPU, RAM, storage
- Pay per hour/second of usage
- Like renting a computer in Amazon's data center

#### Amazon S3 (Simple Storage Service)
- Object storage service
- Store any type of file (images, videos, HTML, backups)
- Highly scalable and durable (99.999999999% durability)
- Used for static website hosting, backups, data lakes

---

### EC2 Key Terms
| Term | Meaning |
|------|---------|
| Instance | A virtual server (like one computer) |
| AMI (Amazon Machine Image) | Template with OS and software for launching instance |
| Instance Type | Size of the server (CPU + RAM) - e.g. t3.micro |
| Key Pair | SSH login credentials (.pem file) |
| Security Group | Firewall rules controlling inbound/outbound traffic |
| Public IP | IP address to access instance from internet |
| Private IP | Internal IP within AWS network |
| Region | Geographic location of data centers - e.g. ap-south-2 Hyderabad |

---

### EC2 Instance Types
| Family | Purpose | Example |
|--------|---------|---------|
| t3.micro | General purpose, free tier | Your experiment |
| c5 | Compute optimized | High CPU tasks |
| r5 | Memory optimized | Databases |
| p3 | GPU instances | Machine learning |

---

### Security Groups
- Act as virtual firewall for EC2 instances
- Control inbound (incoming) and outbound (outgoing) traffic
- Rules specify: Protocol, Port, Source IP

**Your experiment:**
- SSH rule: Port 22 - for terminal access
- HTTP rule: Port 80 - for website access in browser

---

### Your EC2 Experiment Explained
**What you did step by step:**
1. Opened EC2 console in AWS
2. Launched instance named "das" with Ubuntu 24.04 LTS, t3.micro
3. Created key pair "shyam-s" and downloaded .pem file
4. Set security group rules - SSH (22) and HTTP (80)
5. Fixed .pem file permissions using icacls commands
6. Connected via SSH: `ssh -i shyam-s.pem ubuntu@18.61.202.218`
7. Updated packages: `sudo apt update`
8. Installed Apache: `sudo apt install apache2 -y`
9. Started Apache: `sudo systemctl start apache2`
10. Created webpage at `/var/www/html/index.html`
11. Verified website by visiting public IP in browser

---

### S3 Key Terms
| Term | Meaning |
|------|---------|
| Bucket | Container to store objects (like a folder) |
| Object | Any file stored in S3 |
| ACL (Access Control List) | Controls who can access objects |
| Object URL | Public web address to access the file |
| ARN | Amazon Resource Name - unique identifier |
| Static Website | Website with only HTML/CSS - no server-side code |

---

### Your S3 Experiment Explained
**What you did:**
1. Created bucket "shyam-prasath-s-html-demo-2026" in Hyderabad region
2. Disabled "Block all public access"
3. Uploaded cloud-pb1.html file
4. Enabled ACLs in Object Ownership settings
5. Granted "Everyone (public access)" Read permission via ACL
6. Got public Object URL
7. Opened URL in browser - website loaded successfully

---

### EC2 vs S3 - Key Difference
| Feature | EC2 | S3 |
|---------|-----|-----|
| Type | Compute (Virtual Server) | Storage |
| Use case | Run applications, websites with backend | Store files, host static websites |
| Access | Via SSH (terminal) | Via AWS Console or URL |
| Website type | Dynamic or Static | Static only |
| Cost basis | Per hour running | Per GB stored |

---

## UNIT 5: APACHE WEB SERVER

### What is Apache?
Apache (Apache2) is a free, open-source web server software. It serves web pages to users when they visit your website.

**Full name:** Apache HTTP Server
**Port:** 80 (HTTP)

---

### Apache Commands You Used
```bash
sudo apt update                    # Update package list
sudo apt install apache2 -y        # Install Apache
sudo systemctl start apache2       # Start Apache service
sudo systemctl enable apache2      # Auto-start on reboot
sudo systemctl status apache2      # Check if running
sudo nano /var/www/html/index.html # Edit webpage
ls -l /var/www/html                # List files
```

### What is /var/www/html?
It is the default web root directory of Apache. Any HTML file placed here is served as a website when someone visits your server's IP address.

---

## UNIT 6: IMPORTANT VIVA QUESTIONS & ANSWERS

### Cloud Computing
**Q: Define cloud computing.**
A: Cloud computing is the on-demand delivery of IT resources like compute, storage, and databases over the internet with pay-as-you-go pricing.

**Q: What are the 3 service models?**
A: IaaS (Infrastructure), PaaS (Platform), SaaS (Software).

**Q: What is the difference between public and private cloud?**
A: Public cloud is owned by a third party and shared by multiple organizations. Private cloud is owned and used exclusively by one organization.

**Q: Give examples of cloud providers.**
A: Amazon Web Services (AWS), Microsoft Azure, Google Cloud Platform (GCP).

---

### Virtualization
**Q: What is a hypervisor?**
A: A hypervisor is software that creates and manages virtual machines by abstracting the hardware resources of the host machine.

**Q: What is the difference between Type 1 and Type 2 hypervisor?**
A: Type 1 runs directly on hardware (bare metal) like VMware ESXi. Type 2 runs on top of an existing OS like Oracle VirtualBox.

**Q: What is a VM snapshot?**
A: A snapshot is a saved state of a VM at a particular point in time, used for backup and recovery.

---

### EC2
**Q: What is Amazon EC2?**
A: Amazon EC2 (Elastic Compute Cloud) is a web service that provides resizable virtual servers (instances) in the cloud.

**Q: What is an AMI?**
A: AMI (Amazon Machine Image) is a pre-configured template containing the OS and software used to launch an EC2 instance.

**Q: What is a security group?**
A: A security group acts as a virtual firewall that controls inbound and outbound traffic to an EC2 instance using rules based on port and protocol.

**Q: What is SSH?**
A: SSH (Secure Shell) is a cryptographic network protocol used to securely connect to a remote server over the internet using a key pair.

**Q: What is a .pem file?**
A: A .pem (Privacy Enhanced Mail) file is a private key file used to authenticate SSH connections to EC2 instances.

**Q: What is t3.micro?**
A: t3.micro is a free-tier eligible EC2 instance type with 2 vCPUs and 1 GB RAM, suitable for low-traffic applications and testing.

**Q: What is the default web directory in Apache?**
A: /var/www/html is the default web root directory in Apache where website files are stored.

---

### S3
**Q: What is Amazon S3?**
A: Amazon S3 (Simple Storage Service) is an object storage service that stores any amount of data and makes it accessible from anywhere over the internet.

**Q: What is a bucket in S3?**
A: A bucket is a container in S3 used to store objects (files). Each bucket has a globally unique name.

**Q: What is an ACL in S3?**
A: ACL (Access Control List) is a mechanism in S3 that defines who can access objects and what actions they can perform (read/write).

**Q: What is static website hosting in S3?**
A: S3 can host static websites (HTML, CSS, JS files) by making objects publicly accessible via a URL without needing a web server.

**Q: What is the difference between EC2 and S3?**
A: EC2 is a compute service (virtual server) used to run applications. S3 is a storage service used to store files. EC2 hosts dynamic websites while S3 hosts static websites.

**Q: What does "Block all public access" mean in S3?**
A: It is a security setting that prevents any public access to S3 bucket objects. It must be disabled to host a public website.

---

### Networking
**Q: What is a public IP address?**
A: A public IP is an IP address accessible over the internet, assigned to your EC2 instance so users can reach it.

**Q: What is port 80?**
A: Port 80 is the default port for HTTP (web) traffic. When you visit a website without specifying a port, your browser automatically uses port 80.

**Q: What is port 22?**
A: Port 22 is the default port for SSH (Secure Shell) connections used to remotely access Linux servers.

**Q: What is HTTP?**
A: HTTP (HyperText Transfer Protocol) is the protocol used for transferring web pages over the internet.

---

## QUICK REVISION CHEAT SHEET

### One-line definitions
- **Cloud Computing** - Delivery of IT services over internet on pay-as-you-use basis
- **IaaS** - Provides virtual hardware (EC2)
- **PaaS** - Provides development platform
- **SaaS** - Provides ready-to-use software (Gmail)
- **Virtualization** - Running multiple VMs on one physical machine
- **Hypervisor** - Software that manages VMs
- **EC2** - Virtual server in AWS cloud
- **S3** - Object storage in AWS
- **AMI** - Template to launch EC2 instance
- **Security Group** - Firewall for EC2
- **Key Pair** - SSH login credentials
- **Apache** - Web server software
- **NAT** - VM shares host IP to access internet
- **Bridged** - VM gets its own IP
- **ifconfig** - Linux command to see IP addresses
- **ping** - Command to test network connectivity
- **SSH** - Secure remote connection protocol
- **ACL** - Access control for S3 objects
- **Bucket** - Container for files in S3
- **Static website** - Website with only HTML/CSS files

---
