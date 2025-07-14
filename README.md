# ☁️ Multi-Zone High Availability And Scalable Web Application on AWS

This project demonstrates the design, deployment, and validation of a highly available cloud infrastructure using **Amazon Web Services (AWS)**. It features fault tolerance, resilience, and cost-aware architecture across multiple availability zones.

---

## 📁 Project Files

All project documents including the full report and presentation can be accessed here:

📂 **[Project Documents – Google Drive](https://drive.google.com/drive/folders/1s4RSTehuofoVeQBZXWMzj24U16M1cu-F?usp=drive_link)**

Contents:
- 📝 Technical Report (PDF)
- 📊 Presentation Slides (PPTX)
- 🎥 Test Case Demonstration Videos
- 📈 Cost Breakdown & Analysis

---

## ⚙️ Infrastructure Overview

This project uses **Infrastructure as Code** (IaC) via **AWS CloudFormation** to deploy a multi-zone architecture across two regions:

### 📂 CloudFormation Templates
- `cloudformation/Frankfurt Region.yaml` – Deploys infrastructure in **eu-central-1 (Frankfurt)**
- `cloudformation/Paris Region.yaml` – Deploys infrastructure in **eu-west-3 (Paris)**

Each template provisions:
- VPC, subnets, internet gateways, and route tables
- EC2 instances across Availability Zones
- Application Load Balancer and Target Groups
- Auto Scaling Group and CloudWatch alarms

> ⚠️ **Note:**  
> The setup and configuration for **Amazon Route 53 (DNS failover)** and **Amazon CloudFront (content distribution)** were performed **manually via the AWS Console** and are **not included** in the CloudFormation templates.

---

## 🧪 Test Scenarios

Two high availability configurations were validated:

1. **Active-Active Architecture**
   - Simulated EC2 failure in Frankfurt (AZ1)
   - Load balancer automatically redirected traffic
2. **Active-Passive Architecture**
   - Primary instance failure in Paris triggered Route 53 DNS failover to a secondary instance

🎬 Video demonstrations of both scenarios are included in the Google Drive folder.

---

## 📊 Cost Analysis

| Architecture     | Availability        | Monthly Cost (Est.) |
|------------------|---------------------|----------------------|
| Active-Active    | Real-time failover  | ~$270                |
| Active-Passive   | DNS failover        | ~$33                 |

Detailed cost comparisons and usage calculations are included in the cost analysis spreadsheet.

---

## 🧰 Technologies Used

- **Amazon EC2**
- **Amazon Route 53** *(manual setup)*
- **Elastic Load Balancing (ALB)**
- **AWS CloudFormation**
- **Amazon CloudWatch**
- **Amazon CloudFront** *(manual setup)*

---

## 📷 Architecture & Diagrams

 ![Architecture Diagram](Diagrams/Design.png)
### 🖼️ Architecture Diagram: Multi-Region High Availability Web Application

The diagram showcases the deployment architecture of a highly available web application across two AWS regions: **Frankfurt (eu-central-1)** and **Paris (eu-west-3)**, designed to ensure fault tolerance, scalability, and continuous availability.

---

### 🌐 Web Application Architecture – Active-Passive Design

Users access the application via a domain managed by **Amazon Route 53**, which performs DNS-level health checks.

Route 53 routes user traffic to the **primary (active) region** — **Frankfurt** — by default.

The **web application** is hosted on **EC2 instances** within public subnets distributed across two Availability Zones in Frankfurt (`eu-central-1a`, `eu-central-1b`), managed by an **Auto Scaling Group**.

Traffic to application servers is typically served through an **Application Load Balancer (ALB)** (not explicitly shown in the diagram, but part of the setup).

---

### 🔁 Failover to Passive Region

**Paris (eu-west-3)** serves as the **passive backup region**, fully configured but on standby.

Like Frankfurt, it contains two Availability Zones (`eu-west-3a`, `eu-west-3b`) with public subnets and EC2 instances managed by an **Auto Scaling Group**.

In case of failure or unavailability in Frankfurt, **Route 53 automatically fails over** to Paris, redirecting user requests to the standby environment.

---

### ⚙️ Key Features

✅ Web application architecture designed for high availability across multiple AWS regions  
✅ Uses Amazon Route 53 for intelligent DNS routing and health-based failover  
✅ Built-in redundancy and scalability using Auto Scaling Groups in both regions  
✅ Manual configuration of Route 53 failover policies and content delivery through Amazon CloudFront (not shown in the template)  

This design ensures that the web application remains accessible even in the event of a regional outage, making it ideal for **production-grade systems** that require **resiliency** and **minimal downtime**.

---

## 🏁 How to Deploy

To deploy the infrastructure using CloudFormation:

1. Open the AWS Console
2. Go to **CloudFormation > Create stack**
3. Upload one of the templates:
   - `cloudformation/Frankfurt Region.yaml`
   - `cloudformation/Paris Region.yaml`
4. Follow the prompts to complete deployment
5. Configure **Route 53** and **CloudFront** manually after stack creation (as per the report and presentation)

---

## 📬 Contact

- 📧 Email: [Ghazy.ame@gmail.com](mailto:Ghazy.ame@gmail.com)  
- 💼 LinkedIn: [www.linkedin.com/in/ghazyame](https://www.linkedin.com/in/ghazyame)

---

## 📜 License

This project is provided for educational and demonstration purposes. Please credit the author if reused.
