# ☁️ Multi-Zone High Availability Cloud Solution on AWS **(Web Application)
**
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

Each stack sets up:
- EC2 instances across Availability Zones
- VPCs, subnets, internet gateways, and route tables
- Application Load Balancer and Target Groups
- Route 53 DNS health checks and failover policies
- Auto Scaling Groups and CloudWatch alarms

---

## 🧪 Test Scenarios

Two high availability configurations were validated:

1. **Active-Active Architecture**
   - Simulated EC2 failure in Frankfurt (AZ1)
   - Load balancer automatically redirected traffic
2. **Active-Passive Architecture**
   - Primary instance failure in Paris triggered Route 53 DNS failover to backup

🎬 Video demos for both scenarios are available in the linked Google Drive folder.

---

## 📊 Cost Analysis

| Architecture     | Availability        | Monthly Cost (Est.) |
|------------------|---------------------|----------------------|
| Active-Active    | Real-time failover  | ~$270                |
| Active-Passive   | DNS failover        | ~$33                 |

For detailed calculations, see the cost breakdown Excel sheet in the Google Drive.

---

## 🧰 Technologies Used

- **Amazon EC2**
- **Amazon Route 53**
- **Elastic Load Balancing (ALB)**
- **AWS CloudFormation (IaC)**
- **Amazon CloudWatch**
- **Amazon CloudFront** (for performance optimization)

---

## 📷 Architecture & Diagrams

System design diagrams (if available) can be found in the `/assets` folder.

---

## 🏁 How to Deploy

To deploy either stack:

1. Open the AWS Console
2. Navigate to **CloudFormation > Create stack**
3. Upload either:
   - `cloudformation/Frankfurt Region.yaml` *(for eu-central-1)*
   - `cloudformation/Paris Region.yaml` *(for eu-west-3)*
4. Provide any required parameters
5. Monitor progress under the **Events** tab

---

## 📬 Contact

- 📧 Email: [Ghazy.ame@gmail.com](mailto:Ghazy.ame@gmail.com)  
- 💼 LinkedIn: [www.linkedin.com/in/ghazyame](https://www.linkedin.com/in/ghazyame)

---

## 📜 License

This project is provided for learning and demonstration purposes. Please credit the author if you reference or reuse it.
