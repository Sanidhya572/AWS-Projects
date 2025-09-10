# 🌐 Amazon S3 Static Website Hosting - Step-by-Step Documentation  

This project demonstrates how to **host a static website using Amazon S3**.  
You will:  
- Create and configure an **S3 bucket**.  
- Upload **static website files** (HTML, CSS, JS).  
- Enable **S3 static website hosting**.  
- Configure **bucket policies** for public access.  
- Access your website via the **S3 endpoint**.  

---

## 📌 Steps to Host a Static Website on Amazon S3  

### ✅ Step 1: Log in to AWS Management Console  
Access your AWS account to start configuring S3.  

**Actions:**  
- Open your browser and go to [AWS Console](https://aws.amazon.com/console/).  
- Sign in with your **Root user** or **IAM user** credentials.  

---

### ✅ Step 2: Create an S3 Bucket  
Set up an S3 bucket to store website files.  

**Actions:**  
- From AWS Console, search for **S3** and click it.  
- Click **Create bucket**.  
- Enter a unique bucket name: `my-website-demo`.  
- Choose an AWS Region.  
- Uncheck **Block all public access**.  
- Acknowledge the warning.  
- Click **Create bucket**.  

---

### ✅ Step 3: Upload Website Files  
Add your static website files to the S3 bucket.  

**Actions:**  
- Select your bucket → Go to **Objects** tab.  
- Click **Upload** → **Add files**.  
- Select your local `index.html`, `style.css`, etc.  
- Click **Upload** to store them.  

---

### ✅ Step 4: Enable Static Website Hosting  
Turn on static hosting to serve your files over HTTP.  

**Actions:**  
- In the bucket, go to **Properties** tab.  
- Scroll to **Static website hosting** → **Edit**.  
- Select **Enable** → **Host a static website**.  
- Set:  
  - Index document: `index.html`  
  - Error document: `error.html` (optional)  
- Save changes.  

---

### ✅ Step 5: Set Bucket Policy for Public Access  
Grant public read access to website files.  

**Actions:**  
- Go to **Permissions** → **Bucket policy** → **Edit**.  
- Paste the following JSON policy (replace `my-website-demo` with your bucket name):  

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::my-website-demo/*"
    }
  ]
}
