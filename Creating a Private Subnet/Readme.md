# 🔒 Creating a Private Subnet in AWS

This project provides a **step-by-step guide** to setting up a **Private Subnet** inside an **Amazon Virtual Private Cloud (VPC)**.  
It builds on earlier projects — *Build a Virtual Private Cloud* and *VPC Traffic Flow and Security* — and introduces **private networking** for workloads that should not have direct internet access.  

---

## 📖 Project Overview

You will learn how to:

- Create a **VPC** with both public and private subnets  
- Configure **Internet Gateway**, **Route Tables**, and **Security Groups**  
- Set up **Network ACLs (NACLs)** for subnet-level security  
- Keep your private subnet **isolated** (no internet access)  
- Understand the difference between **Public vs Private Subnets**  

---

## 🛠️ Step-by-Step Implementation

### **Step 1: Create a VPC**
- Create a new **VPC** (e.g., `NextWork VPC`) with IPv4 CIDR `10.0.0.0/16`  

---

### **Step 2: Create Subnets**
- **Public Subnet**: `10.0.0.0/24` with **Auto-assign Public IP** enabled  
- Reserved for internet-facing resources  

---

### **Step 3: Internet Gateway**
- Create and attach **NextWork IG** to the VPC for external connectivity (public subnet only)  

---

### **Step 4: Public Route Table**
- Add route: `0.0.0.0/0` → Internet Gateway  
- Associate with **Public Subnet**  

---

### **Step 5: Security Group**
- Create **NextWork-SG**  
- Allow inbound **HTTP (80)**, **SSH (22)**, and other required rules  
- Outbound → allow all traffic (default)  

---

### **Step 6: Public NACL**
- Allow inbound **HTTP, HTTPS, SSH**  
- Outbound → allow all  
- Associate with **Public Subnet**  

---

### **Step 7: Create a Private Subnet**
- Subnet CIDR: `10.0.1.0/24`  
- **Do NOT enable public IP auto-assign**  
- Placed in a different AZ (for redundancy)  

---

### **Step 8: Private Route Table**
- Create **NextWork-Private-RT**  
- Associate with **Private Subnet**  
- ❌ No internet route → remains private  

---

### **Step 9: Private NACL**
- Allow only **internal traffic** (e.g., from public subnet or specific IP ranges)  
- Restrict outbound → prevent internet connectivity  
- Associate with **Private Subnet**  

---

## 📌 Key Learnings

- **Private Subnet** = isolated environment with no direct internet access  
- **Security Layers** → Security Groups (instance-level) + NACLs (subnet-level)  
- **Route Tables** define subnet accessibility  
- Best practice: Place **databases or sensitive workloads** inside private subnets  

---

## 📬 Author

👤 **Sanidhya Rajguru**  
🔗 [GitHub Profile](https://github.com/Sanidhya572)  

⭐ *If you found this project helpful, give it a star on GitHub!* ⭐
