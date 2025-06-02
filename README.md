
# 🔐 Secure AWS VPC Architecture 

In this project I  build a **secure Virtual Private Cloud (VPC)** on AWS using only **free-tier resources**. The architecture includes **segmented public and private subnets**, strict access controls using **Security Groups and Network ACLs (NACLs)**, and basic logging and monitoring setup.

---

## 🌐 Architecture Overview

- ✅ Custom VPC (`10.0.0.0/16`)
- ✅ Public Subnet: Bastion EC2 (SSH entry point)
- ✅ Private Subnet: Internal EC2 (only accessible from bastion)
- ✅ Internet Gateway (for outbound access from public subnet)
- ✅ Route Tables for subnet separation
- ✅ Security Groups and NACLs for controlled traffic flow
- ✅ VPC Flow Logs configured (via CloudWatch Logs)
- ✅ GuardDuty enabled for threat detection (free 30-day trial)

---

## 🧱 Project Components

| Component         | Description |
|------------------|-------------|
| **VPC**          | Custom IPv4 VPC with DNS hostname support |
| **Subnets**      | Public (`10.0.1.0/24`), Private (`10.0.2.0/24`) |
| **EC2 Instances**| 1 Public (host instance), 1 Private (internal instance ), both `t2.micro` |
| **Routing**      | Internet access via IGW; no direct internet for private subnet |
| **Security Groups** | Allow SSH to bastion from my IP; SSH to private only from bastion |
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

## 📁 Folder Structure


