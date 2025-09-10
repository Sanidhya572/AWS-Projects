# 🚀 Build a Virtual Private Cloud (VPC) in AWS

This project provides a **step-by-step guide** to building a Virtual Private Cloud (VPC) in AWS.  
You’ll create a custom VPC, configure subnets, and attach an Internet Gateway to enable connectivity.  

---

## 📑 Steps Covered
1. [Create a VPC](#step-1-create-a-vpc)  
2. [Create Subnets](#step-2-create-subnets)  
3. [Create an Internet Gateway](#step-3-create-an-internet-gateway)  

---

## 🛠️ Step 1: Create a VPC
Set up a new Virtual Private Cloud in AWS.  

**Actions:**  
- Log in to AWS Management Console.  
- Search for **VPC** in the search bar and select it.  
- In the left-hand navigation pane, choose **Your VPCs**.  
- Click **Create VPC**.  
- Select **VPC only** option.  
- Enter a **Name tag** (e.g., `NextWork VPC`).  
- Enter an **IPv4 CIDR block** (e.g., `10.0.0.0/16`).  
- Click **Create VPC**.  

---

## 🌐 Step 2: Create Subnets
Divide your VPC into subnets for better resource organization.  

**Actions:**  
- From the **VPC Dashboard**, select **Subnets**.  
- Click **Create subnet**.  
- Choose your VPC (`NextWork VPC`).  
- Enter a **Subnet name** (e.g., `Public 1`).  
- Select an **Availability Zone**.  
- Enter an **IPv4 CIDR block** (e.g., `10.0.0.0/24`).  
- Click **Create subnet**.  
- Go to **Edit subnet settings** → enable **Auto-assign public IPv4 address**.  
- Click **Save**.  

---

## 🔗 Step 3: Create an Internet Gateway
Attach an internet gateway to your VPC to enable internet access.  

**Actions:**  
- In the VPC Dashboard, select **Internet gateways**.  
- Click **Create internet gateway**.  
- Enter a **Name tag** (e.g., `NextWork IG`).  
- Click **Create internet gateway**.  
- Select your new gateway → **Attach to VPC** → choose `NextWork VPC`.  
- Confirm and connect.  

✅ Your VPC is now connected to the internet!  

---

## 📌 Next Steps
- Configure **Route Tables**.  
- Add **Security Groups** and **NACLs**.  
- Launch **EC2 instances** inside your VPC.  

---

## 📷 (Optional) Diagram
<img width="989" height="811" alt="image" src="https://github.com/user-attachments/assets/55fe0fce-01d3-4b37-95d4-7285f81ecfad" />



