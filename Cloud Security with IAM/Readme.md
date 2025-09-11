# 🔐 Cloud Security with AWS IAM - Step-by-Step Documentation  
<img width="1742" height="1346" alt="image" src="https://github.com/user-attachments/assets/cf0b2002-1cce-45fb-b59e-c8133245d96f" />


This project demonstrates how to implement **cloud security using AWS IAM**.  
You will:  
- Launch **EC2 instances** for production and development.  
- Create and apply **IAM policies**.  
- Configure an **account alias**.  
- Set up **IAM users and groups**.  
- Test access to ensure proper security controls.  

---

## 📌 Steps to Configure IAM-Based Security  

### ✅ Step 1: Launch EC2 Instances  
Deploy EC2 instances for production and development environments.  

**Actions:**  
- Log in to AWS Management Console.  
- Navigate to **EC2 service** → **Launch instance**.  
- Provide a Name and add tags:  
  - `Env = production`  
  - `Env = development`  
- Select a Free tier eligible AMI and instance type.  
- Proceed without a key pair (*for this project only*).  
- Launch both instances.  

---

### ✅ Step 2: Create an IAM Policy  
Define an IAM policy to allow access to **development instances** but restrict **production instances**.  

**Actions:**  
- Navigate to **IAM** → **Policies** → **Create policy**.  
- Switch to **JSON editor** and paste the policy code.  
- Review the policy structure:  
  - `Version`  
  - `Statement`  
  - `Effect`  
  - `Action`  
  - `Resource`  
  - `Condition`  
- Name the policy: `NextWorkDevEnvironmentPolicy`.  
- Add a description and save.  

---

### ✅ Step 3: Create an AWS Account Alias  
Make sign-in easier with a custom alias.  

**Actions:**  
- In IAM console, go to **Dashboard**.  
- Under **Account Alias**, choose **Create**.  
- Enter alias: `nextwork-alias-yourname`.  
- Save changes.  

---

### ✅ Step 4: Create IAM Users and Groups  
Organize permissions with IAM groups and users.  

**Actions:**  
- Go to **User groups** → **Create group**.  
- Name: `nextwork-dev-group`.  
- Attach the `NextWorkDevEnvironmentPolicy`.  
- Go to **Users** → **Create user**.  
- Enter username: `nextwork-dev-yourname`.  
- Provide console access + password settings.  
- Add user to `nextwork-dev-group`.  
- Save user.  

---

### ✅ Step 5: Test Intern's Access  
Verify that access restrictions are applied correctly.  

**Actions:**  
- Copy **IAM sign-in URL** (with account alias).  
- Open it in an **Incognito browser**.  
- Log in with the new IAM user’s credentials.  
- Test:  
  - Try stopping **production instance** → ❌ should fail.  
  - Try stopping **development instance** → ✅ should succeed.  
- Confirm that access controls are working.  

---

## 📖 Summary  

By following this project, you have:  
- Secured EC2 instances with **IAM policies**.  
- Configured an **account alias** for easier access.  
- Created structured **users and groups**.  
- Validated IAM restrictions with **real tests**.  

🎉 Congrats! You’ve set up **IAM-based cloud security** in AWS.  

---

