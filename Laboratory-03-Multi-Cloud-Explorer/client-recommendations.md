<div align="center">

<sub>- CHECKPOINT 4 -</sub>

# Client Recommendations

</div>

<p align="justify">
This document presents cloud platform recommendations for four client scenarios received by CloudNova Technologies. Each recommendation identifies the most suitable cloud provider based on the client's business requirements, along with supporting justification and relevant services the client could adopt.
</p>

---

## 🚀 Client A – Startup Company

<p align="justify">
<b>Scenario:</b> A startup company wants to launch a new mobile application. Their budget is limited, but they expect rapid growth within the next few years.
</p>

**Recommended Platform:** Amazon Web Services (AWS)

<p align="justify">
AWS is a strong fit for this startup because of its AWS Free Tier and flexible pay-as-you-go pricing, which helps keep costs low while the company is just getting started. Since the startup expects rapid growth, AWS's wide range of scalable services means the company won't need to switch providers as it grows. AWS also has the largest community and the most tutorials, documentation, and third-party tools, which is helpful for a small team without a large IT department. As the app grows, the startup can easily add more advanced services without rebuilding its infrastructure.
</p>

**Services to use:**
- **Amazon EC2** – to host the mobile app's backend
- **Amazon S3** – to store user uploads, images, and backups
- **Amazon RDS** – to manage the app's database as it scales

---

## 🎓 Client B – University

<p align="justify">
<b>Scenario:</b> A university already uses Windows Server, Microsoft 365, and Active Directory. The university wants to migrate some services to the cloud.
</p>

**Recommended Platform:** Microsoft Azure

<p align="justify">
Since the university already uses Windows Server, Microsoft 365, and Active Directory, Azure is the clear choice because of how tightly it integrates with these existing Microsoft tools. Azure allows the university to connect its on-premises Active Directory with Microsoft Entra ID, making it easy to manage student and staff accounts across both cloud and on-site systems. This reduces the need to retrain staff or replace tools they already know. Azure's hybrid cloud tools, like Azure Arc, also make it easier to move services to the cloud gradually instead of all at once.
</p>

**Services to use:**
- **Microsoft Entra ID** – to manage logins and connect with the existing Active Directory
- **Azure Virtual Machines** – to host migrated applications
- **Azure SQL Database** – to move on-premises databases to the cloud

---

## 🤖 Client C – AI Research Company

<p align="justify">
<b>Scenario:</b> A research company develops Artificial Intelligence and Machine Learning applications that require high-performance computing.
</p>

**Recommended Platform:** Google Cloud Platform (GCP)

<p align="justify">
GCP is the best fit for an AI research company because of its strong AI and machine learning tools, plus its high-performance computing capabilities. Google created and still leads the development of Kubernetes, so GCP offers the most mature environment for running large-scale, container-based AI workloads. Tools like Vertex AI and TensorFlow, also developed by Google, make it easier to build, train, and deploy machine learning models. GCP's high-performance private global network also helps speed up large data transfers, which is important for AI workloads that require processing huge datasets.
</p>

**Services to use:**
- **Vertex AI** – to build and train machine learning models
- **Compute Engine** – for high-performance computing power
- **Google Kubernetes Engine (GKE)** – to run and scale AI workloads efficiently

---

## 🛒 Client D – Global E-Commerce Company

<p align="justify">
<b>Scenario:</b> A multinational online shopping company serves customers around the world and requires highly available infrastructure with automatic scaling.
</p>

**Recommended Platform:** Amazon Web Services (AWS)

<p align="justify">
AWS is well suited for a global e-commerce company because of its large number of Regions and Availability Zones around the world, which helps keep the website fast and available no matter where customers are located. AWS also has strong, proven auto-scaling tools that can automatically handle sudden spikes in traffic, such as during sales events. Many major e-commerce companies already trust AWS to handle massive scale and high availability. AWS's wide range of services also makes it easy to add features like personalized recommendations or fraud detection as the business grows.
</p>

**Services to use:**
- **Amazon EC2 with Auto Scaling** – to automatically handle changes in traffic
- **Amazon CloudFront** – to deliver content quickly to customers worldwide
- **Amazon RDS** – to manage product and order data reliably



---

<div align="center">

<sub>- CHECKPOINT 6 -</sub>

## Multi-Cloud Decision Matrix

</div>

<p align="justify">
This section presents a simple decision matrix that recommends the most suitable cloud platform for different business needs. It summarizes the reasoning behind each recommendation, based on the strengths of AWS, Microsoft Azure, and Google Cloud Platform explored throughout this research.
</p>

<div align="center">

| Business Requirement | Recommended Platform | Justification |
|---|---|---|
| Startup Company | AWS | Offers a free tier and flexible pay-as-you-go pricing, plus the widest range of services to support growth without switching providers later. |
| Enterprise Organization | AWS | Most mature and widely adopted platform, with the broadest service catalog and largest global infrastructure to support large-scale operations. |
| Microsoft Environment | Azure | Integrates directly with Windows Server, Active Directory, and Microsoft 365, making it the natural choice for companies already using Microsoft tools. |
| AI / Machine Learning | GCP | Leading AI/ML tools like Vertex AI and TensorFlow, plus strong high-performance computing support for training and deploying models. |
| Kubernetes Deployment | GCP | Created and still leads development of Kubernetes, offering the most mature managed Kubernetes service through GKE. |
| Global Web Application | AWS | Largest number of Regions and Availability Zones worldwide, with proven auto-scaling tools to handle high traffic and stay available globally. |

</div>

