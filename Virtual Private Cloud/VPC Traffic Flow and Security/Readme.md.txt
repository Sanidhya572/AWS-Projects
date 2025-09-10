# 🚀 VPC Traffic Flow and Security - Step-by-Step Documentation  

This project provides a **comprehensive, step-by-step guide** for setting up and securing an **Amazon VPC**.  
It builds upon the earlier project *"Build a Virtual Private Cloud"* and extends it with **traffic flow** and **security configurations**.  

---

## 📌 Steps to Build and Secure the VPC  

### ✅ Step 1: Create a VPC  
Set up a new Virtual Private Cloud in AWS.  
**Actions:**  
- Log in to AWS Management Console.  
- Search for **VPC** and select it.  
- Navigate to **Your VPCs** → **Create VPC**.  
- Select **VPC only** option.  
- Enter Name tag: `NextWork VPC`.  
- Enter IPv4 CIDR block: `10.0.0.0/16`.  
- Click **Create VPC**.  

---

### ✅ Step 2: Create Subnets  
Divide your VPC into subnets for better resource organization.  
**Actions:**  
- From VPC Dashboard → **Subnets** → **Create subnet**.  
- Choose VPC: `NextWork VPC`.  
- Enter Subnet name: `Public 1`.  
- Select Availability Zone.  
- Enter CIDR block: `10.0.0.0/24`.  
- Enable **Auto-assign public IPv4 address**.  
- Save changes.  

---

### ✅ Step 3: Create an Internet Gateway  
Attach an Internet Gateway to your VPC for internet access.  
**Actions:**  
- Go to **Internet Gateways** → **Create internet gateway**.  
- Name: `NextWork IG`.  
- Attach to VPC: `NextWork VPC`.  

---

### ✅ Step 4: Create a Route Table  
Define how traffic flows in your VPC.  
**Actions:**  
- Go to **Route Tables** → **Create route table**.  
- Name: `NextWork-RouteTable`.  
- Associate with VPC: `NextWork VPC`.  
- Add route: `0.0.0.0/0 → Internet Gateway`.  
- Associate with subnet: `Public 1`.  

---

### ✅ Step 5: Create a Security Group  
Control inbound/outbound traffic for your resources.  
**Actions:**  
- Go to **Security Groups** → **Create security group**.  
- Name: `NextWork-SG`.  
- Associate with VPC: `NextWork VPC`.  
- Inbound rules:  
  - HTTP (Port 80) → Anywhere (0.0.0.0/0)  
  - SSH (Port 22) → Anywhere (0.0.0.0/0)  
- Outbound rules: Allow all traffic.  

---

### ✅ Step 6: Create a Network ACL  
Provide subnet-level security with a Network ACL.  
**Actions:**  
- Go to **Network ACLs** → **Create network ACL**.  
- Name: `NextWork-NACL`.  
- Associate with VPC: `NextWork VPC`.  
- Configure inbound rules: Allow HTTP, HTTPS, SSH.  
- Configure outbound rules: Allow all.  
- Associate with subnet: `Public 1`.  

---

## 🌍 VPC Resource Map  

Here’s how a request flows through the VPC:  

1. 💻 **Client/User**: User enters your website URL in a browser.  
2. 🚪 **Internet Gateway (NextWork IG)**: Request goes through the internet to your IG.  
3. 🌐 **VPC (NextWork VPC)**: IG forwards the request into the VPC.  
4. 🚏 **Route Table**: Routes traffic to the EC2 instance in the public subnet.  
5. 📋 **Network ACL (NextWork NACL)**: Inbound rules allow HTTP/HTTPS/SSH traffic.  
6. 🥅 **Public Subnet (Public 1)**: Traffic flows into the subnet.  
7. 👮 **Security Group (NextWork-SG)**: Checks inbound rules → allows HTTP (80).  
8. 😮‍💨 **EC2 Instance**: Web server processes the request & prepares a response.  
9. 🔁 **Response Flow**: Data flows back via Security Group → Subnet → NACL → Route Table → VPC → Internet Gateway → User’s browser.  

---

## 📖 Summary  

By following this guide, you’ve successfully:  
- Created a **VPC** with public subnets.  
- Attached an **Internet Gateway**.  
- Configured **Route Tables**.  
- Applied **Security Groups** and **Network ACLs** for traffic filtering.  
- Understood the **end-to-end flow** of requests in your AWS network.  

🎉 Congrats! Your VPC is now secure and internet-ready! 🚀  

---
