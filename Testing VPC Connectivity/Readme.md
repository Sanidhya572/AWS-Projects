# 🌐 Testing VPC Connectivity (AWS Project)

This project provides a **detailed, step-by-step guide** to setting up a Virtual Private Cloud (VPC) in AWS and testing connectivity between public and private EC2 instances as well as to the internet.  

---

## ✍️ Project Objective

In this project, I will:  
- Verify **connectivity between EC2 instances** (Public ↔ Private).  
- Validate **internet access from the Public Subnet**.  
- Recap the **VPC setup** from scratch to ensure everything is configured properly.  

---

## ✅ Prerequisites

Before starting, make sure you have:  

- An **AWS account** with access to the Management Console.  
- A VPC (`NextWork VPC`) with Public and Private subnets.  
- An Internet Gateway attached to the VPC.  
- Configured **Route Tables, Security Groups, and NACLs**.  
- One EC2 instance in the **Public Subnet** (`NextWork Public Server`).  
- One EC2 instance in the **Private Subnet** (`NextWork Private Server`).  

---

## 🛠️ Step-by-Step Implementation

### **Step 1: Create a VPC**
1. Go to **VPC Dashboard** → *Your VPCs* → *Create VPC*.  
2. Choose **VPC only**.  
3. Enter Name: `NextWork VPC`.  
4. Enter CIDR block: `10.0.0.0/16`.  
5. Click **Create VPC**.  

---

### **Step 2: Create Subnets**
1. VPC Dashboard → *Subnets* → *Create Subnet*.  
2. Select VPC = `NextWork VPC`.  
3. Create **Public Subnet**:  
   - Name = `Public 1`  
   - AZ = Select one  
   - CIDR = `10.0.0.0/24`  
   - Enable *Auto-assign Public IPv4*.  
4. Create **Private Subnet**:  
   - Name = `Private 1`  
   - AZ = different from Public subnet (optional redundancy)  
   - CIDR = `10.0.1.0/24`  
   - Leave *Auto-assign Public IPv4* disabled.  

---

### **Step 3: Create an Internet Gateway**
1. VPC Dashboard → *Internet Gateways* → *Create*.  
2. Name = `NextWork IG`.  
3. Attach it to `NextWork VPC`.  

---

### **Step 4: Configure Route Tables**
1. Create **Public RT**:  
   - Associate with Public Subnet.  
   - Add route → `0.0.0.0/0` → Target = IGW.  
2. Create **Private RT**:  
   - Associate with Private Subnet.  
   - No internet route added.  

---

### **Step 5: Create Security Groups**
1. Public SG = `NextWork Public SG`:  
   - Inbound: allow SSH (22), HTTP (80).  
   - Outbound: allow all.  
2. Private SG = `NextWork Private SG`:  
   - Inbound: allow traffic only from Public SG.  
   - Outbound: allow all.  

---

### **Step 6: Create Network ACLs**
1. Public NACL = `NextWork Public NACL`:  
   - Allow inbound/outbound HTTP, SSH, ICMP.  
2. Private NACL = `NextWork Private NACL`:  
   - By default blocks all → add ICMP inbound/outbound for internal traffic.  
   - Restrict external internet access.  

---

### **Step 7: Launch EC2 in Public Subnet**
1. EC2 Console → *Launch Instance*.  
2. Name = `NextWork Public Server`.  
3. AMI = Amazon Linux 2023, Type = t2.micro.  
4. Network = `NextWork VPC`, Subnet = `Public 1`.  
5. Enable *Auto-assign Public IP*.  
6. Security Group = `NextWork Public SG`.  
7. Key Pair = `NextWork Key Pair`.  
8. Launch.  

---

### **Step 8: Launch EC2 in Private Subnet**
1. EC2 Console → *Launch Instance*.  
2. Name = `NextWork Private Server`.  
3. Same AMI and instance type.  
4. Network = `NextWork VPC`, Subnet = `Private 1`.  
5. Disable *Auto-assign Public IP*.  
6. Security Group = `NextWork Private SG`.  
7. Launch.  

---

### **Step 9: Verify Resources**
- Confirm `NextWork VPC`, subnets, IGW, RTs, SGs, and NACLs exist.  
- Ensure both EC2 instances are in *running* state.  

---

### **Step 10: Connect to Public Server**
1. Select `NextWork Public Server` in EC2 Console.  
2. Click *Connect* → *EC2 Instance Connect*.  
3. SSH in as `ec2-user`.  
4. If it fails, check inbound rules for SSH (22).  

---

### **Step 11: Test Connectivity Between Instances**
1. Copy Private Server’s IPv4 address.  
2. From Public Server terminal:  
   ```bash
   ping <Private IPv4 Address>
