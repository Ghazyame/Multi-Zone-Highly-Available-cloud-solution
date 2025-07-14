# ☁️ Multi-Zone High Availability Cloud Solution on AWS

This project demonstrates the design, deployment, and validation of a highly available cloud infrastructure using **Amazon Web Services (AWS)**. It features fault tolerance, resilience, and cost-aware architecture across multiple availability zones.

---

## 📁 Project Files

All project documents including the full report and presentation can be accessed here:

📂 **[Project Documents – Google Drive](https://drive.google.com/drive/folders/1s4RSTehuofoVeQBZXWMzj24U16M1cu-F?usp=drive_link)**

Contents:
- 📝 Technical Report (PDF)
- 📊 Presentation Slides (PPTX)
- 💡 Test Case Demonstration Videos
- 📈 Cost Breakdown & Analysis

---

## ⚙️ Infrastructure Overview

This project uses **Infrastructure as Code** (IaC) via **AWS CloudFormation** to deploy:
- Multi-zone EC2 instances
- Public subnets across AZs
- Application Load Balancer
- Route 53 DNS failover
- Auto Scaling Group
- Security Groups and Internet Gateway

📄 CloudFormation template: `cloudformation/Frankfurt Region.yaml` `cloudformation/Paris Region.yaml`

---

## 🧪 Test Scenarios

Two test cases were conducted to validate availability:
1. **Active-Active Architecture**
   - EC2 failure simulated in one AZ
   - Load balancer redirects traffic automatically
2. **Active-Passive Architecture**
   - Primary instance failure triggers Route 53 DNS failover to standby

🎬 Demo videos included in the Google Drive link.

---

## 📊 Cost Analysis

| Architecture     | Availability        | Monthly Cost (Est.) |
|------------------|---------------------|----------------------|
| Active-Active    | Real-time failover  | ~$270                |
| Active-Passive   | DNS failover        | ~$33                 |

For more details, check the Excel file in the `/docs` folder or the linked Drive folder.

---

## 🧰 Technologies Used

- **Amazon EC2**
- **Amazon Route 53**
- **Elastic Load Balancing (ALB)**
- **AWS CloudFormation**
- **Amazon CloudWatch**
- **CloudFront** (optional performance optimization)

---

## 📷 Diagrams & Architecture

System design and flow diagrams can be found in the `/assets` directory.

![Architecture](assets/architecture-diagram.png)

---

## 🏁 How to Deploy

To deploy the infrastructure using the provided CloudFormation template:

1. Log in to your AWS Console
2. Go to **CloudFormation > Create stack**
3. Upload `cloudformation/high-availability-stack.yaml`
4. Follow the prompts and parameters
5. Monitor the deployment under "Events" tab

---

## 📬 Contact

If you'd like to discuss the implementation or collaborate:

- 📧 Email: [your.email@example.com]
- 💼 LinkedIn: [linkedin.com/in/yourprofile](https://www.linkedin.com/in/yourprofile)

---

## 📜 License

This project is for learning and demonstration purposes only. All content is original and authored independently.

