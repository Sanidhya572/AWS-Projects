# ☁️ AWS Cloud Projects

<p align="center">
  <strong>Hands-on AWS projects focused on Cloud Computing, Networking, Security, Serverless Architecture, and Application Deployment.</strong>
</p>

<p align="center">
  <a href="https://github.com/Sanidhya572/AWS-Projects">
    <img src="https://img.shields.io/badge/AWS-Cloud-orange?logo=amazon-aws" alt="AWS">
  </a>
  <img src="https://img.shields.io/badge/Level-Beginner%20to%20Intermediate-blue" alt="Level">
  <img src="https://img.shields.io/badge/Focus-Cloud%20Engineering-success" alt="Focus">
</p>

---

## 📌 About This Repository

This repository contains a collection of **hands-on AWS cloud projects** built to develop practical knowledge of cloud infrastructure, networking, security, serverless computing, storage, databases, and application architecture.

The projects progress from **AWS fundamentals and networking concepts** toward **integrated cloud architectures**, including a complete serverless three-tier web application.

Each project focuses on understanding **how AWS services work together in real-world cloud environments**, rather than learning individual services in isolation.

---

## 🗺️ AWS Learning Path

The projects in this repository follow a progression from foundational AWS concepts to integrated architectures:

```text
AWS Fundamentals
       │
       ▼
┌──────────────────────┐
│ VPC & Networking     │
│ Subnets              │
│ Route Tables         │
│ Internet Gateway     │
│ Security Groups      │
│ Network ACLs         │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│ Compute & Resources  │
│ EC2                  │
│ Public / Private     │
│ Subnets              │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│ Security             │
│ IAM                  │
│ Policies             │
│ Access Control       │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│ Storage & Delivery   │
│ S3                   │
│ CloudFront            │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│ Serverless           │
│ Lambda               │
│ API Gateway          │
│ DynamoDB             │
└──────────┬───────────┘
           │
           ▼
┌────────────────────────────┐
│ Three-Tier Cloud           │
│ Application Architecture   │
└────────────────────────────┘
```

---

# 📂 Projects

## 1. 🔹 Virtual Private Cloud (VPC)

**Focus:** AWS Networking Fundamentals

Learned how to create and configure a custom Amazon VPC and establish the foundational components required for AWS networking.

**Key Concepts:**

* VPC
* CIDR blocks
* Subnets
* Route Tables
* Internet Gateway
* Basic network architecture

👉 [View Project](./Virtual%20Private%20Cloud)

---

## 2. 🔹 VPC Traffic Flow & Security

**Focus:** Network Security

Explored how network traffic flows within a VPC and how AWS networking controls can be used to regulate communication.

**Key Concepts:**

* Route Tables
* Security Groups
* Network ACLs
* Inbound & outbound traffic
* Stateful vs. stateless network controls

👉 [View Project](./VPC%20Traffic%20Flow%20and%20Security)

---

## 3. 🔹 Creating a Private Subnet

**Focus:** Private Network Architecture

Created private subnet infrastructure and explored how workloads can operate without direct exposure to the public internet.

**Key Concepts:**

* Public vs. private subnets
* Route tables
* Network isolation
* Private workloads
* Secure cloud architecture

👉 [View Project](./Creating%20a%20Private%20Subnet)

---

## 4. 🔹 Launching VPC Resources

**Focus:** Compute & Networking

Deployed AWS resources within the VPC environment and explored how compute resources interact with public and private network configurations.

**Key Concepts:**

* Amazon EC2
* VPC
* Public & private subnets
* Security Groups
* Network connectivity

👉 [View Project](./Launching%20VPC%20Resources)

---

## 5. 🔹 Static Website Hosting with Amazon S3

**Focus:** Cloud Storage & Web Hosting

Configured Amazon S3 to host a static website and explored the relationship between object storage, website hosting, and access policies.

**AWS Services:**

* Amazon S3
* Bucket Policies

**Key Concepts:**

* Object storage
* Static website hosting
* Bucket configuration
* Access control
* Public access considerations

👉 [View Project](./Static%20Website%20Hosting%20using%20S3)

---

## 6. 🔹 Cloud Security with IAM

**Focus:** Identity & Access Management

Explored AWS Identity and Access Management and how permissions can be controlled using users, roles, and policies.

**AWS Service:**

* AWS IAM

**Key Concepts:**

* IAM Users
* IAM Roles
* IAM Policies
* Permissions
* Access control
* Principle of least privilege

👉 [View Project](./Cloud%20Security%20with%20IAM)

---

## 7. 🔹 Website Delivery with CloudFront

**Focus:** Content Delivery & Performance

Configured Amazon CloudFront to distribute website content globally while using Amazon S3 as the origin.

**AWS Services:**

* Amazon CloudFront
* Amazon S3

**Key Concepts:**

* CDN
* Origins
* Edge locations
* Content distribution
* Website performance
* Caching

👉 [View Project](./Website%20Delivery%20with%20CloudFront)

---

## 8. 🔹 APIs with Lambda & API Gateway

**Focus:** Serverless Computing

Built a serverless API using AWS Lambda and Amazon API Gateway.

**AWS Services:**

* AWS Lambda
* Amazon API Gateway

**Key Concepts:**

* Serverless architecture
* API endpoints
* Lambda functions
* Event-driven execution
* HTTP request/response flow

👉 [View Project](./API%27s%20with%20Lambda%20and%20API%20Gateway)

---

## 9. 🔹 Fetch Data with Lambda & DynamoDB

**Focus:** Serverless Data Access

Created a DynamoDB-based data layer and used AWS Lambda to retrieve data.

**AWS Services:**

* AWS Lambda
* Amazon DynamoDB

**Key Concepts:**

* NoSQL databases
* DynamoDB tables
* Lambda integration
* Data retrieval
* Serverless backend architecture

👉 [View Project](./Fetch%20Data%20with%20AWS%20Lambda)

---

# 🚀 10. Three-Tier Web Application

**Focus:** Integrated Serverless Cloud Architecture

This project brings together multiple AWS services to create a complete three-tier web application.

### Architecture

```text
                    👤 USER
                       │
                       ▼
              ┌─────────────────┐
              │   CloudFront    │
              │      CDN        │
              └────────┬────────┘
                       │
                       ▼
              ┌─────────────────┐
              │       S3        │
              │ Presentation    │
              │      Tier       │
              └────────┬────────┘
                       │
                       ▼
              ┌─────────────────┐
              │  API Gateway    │
              │    API Layer    │
              └────────┬────────┘
                       │
                       ▼
              ┌─────────────────┐
              │     Lambda      │
              │   Logic Tier    │
              └────────┬────────┘
                       │
                       ▼
              ┌─────────────────┐
              │    DynamoDB     │
              │    Data Tier    │
              └─────────────────┘
```

### AWS Services

| Tier         | AWS Services             |
| ------------ | ------------------------ |
| Presentation | Amazon S3 + CloudFront   |
| Logic        | AWS Lambda + API Gateway |
| Data         | Amazon DynamoDB          |

### Concepts Demonstrated

* Three-tier architecture
* Serverless application design
* Static website hosting
* API development
* Serverless compute
* NoSQL database integration
* Cloud-based application communication
* Separation of application layers

👉 [View Project](./Three%20Tier%20Web%20Application)

---

# 🔗 11. VPC Peering

**Focus:** VPC-to-VPC Connectivity

Explored how separate VPC environments can communicate using VPC Peering.

**Key Concepts:**

* VPC Peering
* Route Tables
* CIDR considerations
* Private network communication
* Inter-VPC connectivity

👉 [View Project](./VPC%20Peering)

---

# 🧪 12. Testing VPC Connectivity

**Focus:** Network Troubleshooting

Tested connectivity between resources within the AWS networking environment to understand how routing and security controls affect communication.

**Key Concepts:**

* Network connectivity
* Routing
* Security Groups
* Network ACLs
* Troubleshooting AWS networking

👉 [View Project](./Testing%20VPC%20Connectivity)

---

# 🧰 AWS Services Covered

Throughout these projects, I have worked with the following AWS services and concepts:

### 🌐 Networking

* Amazon VPC
* Subnets
* Route Tables
* Internet Gateway
* VPC Peering
* Security Groups
* Network ACLs

### 💻 Compute

* Amazon EC2
* AWS Lambda

### 🔐 Security

* AWS IAM
* IAM Policies
* IAM Roles
* Security Groups
* Network ACLs

### 📦 Storage & Content Delivery

* Amazon S3
* Amazon CloudFront

### 🔌 API & Serverless

* Amazon API Gateway
* AWS Lambda

### 🗄️ Databases

* Amazon DynamoDB

### 🏗️ Architecture

* Public & Private Network Architecture
* Serverless Architecture
* Three-Tier Architecture
* Cloud Networking
* Application Layer Separation

---

# 🎯 Skills Demonstrated

These projects demonstrate practical exposure to:

* AWS Cloud Fundamentals
* Cloud Networking
* VPC Architecture
* Subnet Design
* Network Security
* IAM & Access Management
* EC2 Deployment
* S3 Website Hosting
* Content Delivery Networks
* Serverless Computing
* API Development
* NoSQL Databases
* VPC Connectivity
* Three-Tier Application Architecture
* Cloud Troubleshooting
* AWS Service Integration

---

# 📈 Learning Progression

| Stage           | Area               | Projects                   |
| --------------- | ------------------ | -------------------------- |
| 🟢 Beginner     | AWS Networking     | VPC, Subnets, Traffic Flow |
| 🟢 Beginner     | Compute            | Launching VPC Resources    |
| 🟢 Beginner     | Security           | IAM                        |
| 🟡 Intermediate | Storage & CDN      | S3, CloudFront             |
| 🟡 Intermediate | Serverless         | Lambda, API Gateway        |
| 🟡 Intermediate | Databases          | DynamoDB                   |
| 🟡 Intermediate | Networking         | VPC Peering & Connectivity |
| 🔵 Integrated   | Cloud Architecture | Three-Tier Web Application |

---

# 🛡️ Security Mindset

Security is an important part of the projects in this repository.

Areas explored include:

* Identity and access management
* IAM policies and permissions
* Network isolation
* Security Groups
* Network ACLs
* Public vs. private resources
* Controlled network traffic
* Separation of application layers

> **Note:** These projects are primarily learning and portfolio projects. Production environments require additional security controls, monitoring, logging, encryption, backup, and governance depending on the workload.

---

# 💡 What I'm Learning

The goal of this repository is not simply to collect AWS projects, but to build an understanding of **how cloud infrastructure works as a system**.

My learning progression is focused on:

```text
AWS Fundamentals
      ↓
Networking
      ↓
Security
      ↓
Compute
      ↓
Storage
      ↓
Serverless
      ↓
Databases
      ↓
Application Architecture
      ↓
Cloud Engineering
```

---

# 🚧 Future Learning Goals

The next stage of this learning journey will focus on deeper cloud engineering concepts such as:

* Infrastructure as Code
* Terraform
* AWS CloudFormation
* AWS CLI
* CloudWatch & CloudTrail
* Load Balancing
* Auto Scaling
* High Availability
* Fault Tolerance
* CI/CD
* Docker
* Containerized applications
* AWS ECS / EKS
* Advanced IAM & security
* Cost optimization
* Monitoring & observability

---

# 🛠️ Tools & Technologies

* **Cloud:** Amazon Web Services (AWS)
* **Version Control:** Git & GitHub
* **Networking:** Amazon VPC
* **Compute:** Amazon EC2, AWS Lambda
* **Storage:** Amazon S3
* **CDN:** Amazon CloudFront
* **API:** Amazon API Gateway
* **Database:** Amazon DynamoDB
* **Security:** AWS IAM, Security Groups, Network ACLs

---

# 🚀 Getting Started

Clone the repository:

```bash
git clone https://github.com/Sanidhya572/AWS-Projects.git
```

Navigate into the repository:

```bash
cd AWS-Projects
```

Each project contains its own documentation and implementation details.

---

# 📚 Repository Structure

```text
AWS-Projects/
│
├── Virtual Private Cloud/
├── VPC Traffic Flow and Security/
├── Creating a Private Subnet/
├── Launching VPC Resources/
├── Static Website Hosting using S3/
├── Cloud Security with IAM/
├── Website Delivery with CloudFront/
├── API's with Lambda and API Gateway/
├── Fetch Data with AWS Lambda/
├── VPC Peering/
├── Testing VPC Connectivity/
├── Three Tier Web Application/
│
└── README.md
```

---

# 👨‍💻 About

**Sanidhya**

Cloud Computing | AWS | Cloud Engineering

This repository documents my hands-on journey into AWS and Cloud Computing, with a focus on building practical infrastructure and understanding how different cloud services work together.

---

## ⭐ If You Find This Useful

If you're also learning AWS or Cloud Computing, feel free to explore the individual projects and use them as learning references.

**Keep learning. Keep building. ☁️🚀**

---

<p align="center">
  <strong>Built with ☁️ AWS + 💻 Curiosity</strong>
</p>
