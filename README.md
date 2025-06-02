
# 🔐 Secure AWS VPC Architecture 

In this project I  build a **secure Virtual Private Cloud (VPC)** on AWS using only **free-tier resources**. The architecture includes **segmented public and private subnets**, strict access controls using **Security Groups and Network ACLs (NACLs)**. For enhanced security monitoring, I walso enabled AWS GuardDuty for threat detection and set up CloudWatch to monitor EC2 instance metrics and logs. These services help detect unusual behavior and maintain visibility into the environment.

---

## 🌐 Architecture Overview

- ✅ Custom VPC (`10.0.0.0/16`)
- ✅ Public Subnet: Public Host EC2 (SSH entry point)
- ✅ Private Subnet: Private Instance EC2 (only accessible from bastion)
- ✅ Internet Gateway (for outbound access from public subnet)
- ✅ Route Tables for subnet separation
- ✅ Security Groups and NACLs for controlled traffic flow
- ✅ VPC Flow Logs configured (via CloudWatch Logs)
- ✅ GuardDuty enabled for threat detection 

---

## 🧱 Project Components

| Component         | Description |
|------------------|-------------|
| **VPC**          | Custom IPv4 VPC with DNS hostname support |
| **Subnets**      | Public (`10.0.1.0/24`), Private (`10.0.2.0/24`) |
| **EC2 Instances**| 1 Public ( public host instance), 1 Private (private instance ), both `t2.micro` |
| **Routing**      | Internet access via Internet gateway for public subnet; no direct internet for private subnet |
| **Security Groups** | Allow SSH to bastion from my IP; SSH to private only from public host |
| **NACLs**        | Stateless layer blocking all by default except essential traffic |
| **Monitoring**   | VPC Flow Logs + GuardDuty enabled for visibility (basic setup) |

---

## 🔐 Security Measures

- 🔒 **Public EC2** allows SSH only from my IP address
- 🔒 **Private EC2** is not publicly accessible; only the public host instance can connect via SSH
- 🔒 **NACLs** block all unnecessary traffic to/from both subnets
- 🔍 **VPC Flow Logs** provide traffic visibility via CloudWatch Logs
- 🛡️ **GuardDuty** enables passive threat detection 

---

## 📸 Suggested Screenshots to Include

> These prove setup and can be added in a `screenshots/` folder or inline in the README:

- ✅ VPC/subnet layout diagram from AWS Console
- ✅ Bastion SSH session (from local terminal)
- ✅ SSH from bastion → private EC2
- ✅ NACL rule configuration
- ✅ Security Group rules
- ✅ Sample VPC Flow Logs from CloudWatch

---

## 📘 What I Learned

- How to create secure AWS networking environments from scratch
- The difference between **stateful (Security Groups)** and **stateless (NACLs)** firewalls
- Best practices for subnet segmentation and bastion host setups
- Basics of logging and monitoring cloud network traffic
- Practical cloud security principles using **only the Free Tier**

---

## 📌 Tags

`#AWS` `#CloudSecurity` `#VPC`  `#FreeTier` `#EC2` `#GuardDuty` `#FlowLogs` `#Networking`



