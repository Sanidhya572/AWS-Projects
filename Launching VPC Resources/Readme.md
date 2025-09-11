# 🌐 Launching VPC Resources on AWS
<img width="1009" height="733" alt="image" src="https://github.com/user-attachments/assets/f059c8ca-dbc8-436e-8185-67ccc96a14c4" />


This project provides a **comprehensive, step-by-step guide** for launching resources into your **Amazon Virtual Private Cloud (VPC)**.  
It builds on earlier projects — *Build a Virtual Private Cloud*, *VPC Traffic Flow and Security*, and *Creating a Private Subnet* — and extends them by covering **EC2 instances in public and private subnets** as well as the **VPC wizard**.

---

## 📖 Project Overview

You will learn how to:

- Create a custom VPC and divide it into **public** and **private** subnets  
- Configure **Internet Gateway** and **Route Tables** for traffic flow  
- Apply **Security Groups** and **Network ACLs** for secure access  
- Launch **EC2 instances** in both public and private subnets  
- Use the **Amazon VPC Wizard** for quick provisioning  

---

## 🛠️ Step-by-Step Implementation

### **Step 1: Create a VPC**
- Log in to AWS Management Console → Search for **VPC**  
- Create a VPC only → Name it (e.g., `NextWork VPC`)  
- Assign IPv4 CIDR (e.g., `10.0.0.0/16`)  

---

### **Step 2: Create Subnets**
- Create a **Public Subnet** (`10.0.0.0/24`) → Enable Auto-assign Public IP  
- Create a **Private Subnet** (`10.0.1.0/24`) → Keep private (no public IPs)  

---

### **Step 3: Internet Gateway**
- Create and attach an **Internet Gateway** (e.g., `NextWork IG`) to the VPC  

---

### **Step 4: Configure Route Tables**
- **Public Route Table** → Route `0.0.0.0/0` → Internet Gateway  
- **Private Route Table** → No internet route (kept isolated)  

---

### **Step 5: Security Groups & NACLs**
- Public SG → Allow HTTP (80), HTTPS (443), SSH (22)  
- Private SG → Limited inbound rules  
- Public NACL → Allow web & SSH traffic  
- Private NACL → Restrict inbound/outbound  

---

### **Step 6: Launch EC2 in Public Subnet**
- Launch **Amazon Linux 2** (e.g., `t2.micro`) in **Public Subnet**  
- Enable Public IP + Public Security Group  
- Test connectivity via **EC2 Instance Connect**  

---

### **Step 7: Launch EC2 in Private Subnet**
- Launch **Amazon Linux 2** (e.g., `t2.micro`) in **Private Subnet**  
- No Public IP  
- Accessible only via a **Bastion Host** in the public subnet  

---

### **Step 8: VPC Wizard**
- Use **Launch VPC Wizard** → Choose template (Public + Private Subnets)  
- Review preconfigured subnets, route tables, IGW, and NACLs  
- Compare with manual setup  

---

## 📌 Key Learnings

- Difference between **Public vs. Private Subnets**  
- How to **secure workloads** with Security Groups & NACLs  
- Manual VPC setup vs. **VPC Wizard** automation  
- Deploying **isolated EC2 workloads** with controlled access  

---

## 📬 Author

👤 **Sanidhya Rajguru**  
🔗 [GitHub Profile](https://github.com/Sanidhya572)  

⭐ *If you found this useful, don’t forget to star the repository!* ⭐

