<div align="center">

<img src="https://github.com/Joy-Pixels/Portfolio/blob/429e0856c0236bbb46fbfce0bac854a72b7e270c/AWS%20Logo.jpg" width="80"/>

# Amazon Web Services (AWS)

</div>

<p align="justify">
This document provides a research overview of Amazon Web Services (AWS), one of the world's leading cloud platforms. It covers AWS's background, global infrastructure, management console, four core services, key advantages, and typical enterprise use cases.
</p>

---

## Brief Overview

<p align="justify">
Amazon Web Services (AWS) is Amazon's cloud computing service. It started in 2006. AWS is the biggest and most popular cloud provider today. It offers more services than any other provider things like servers, storage, databases, networking, AI tools, and more. AWS is known for its maturity, reliability, and the sheer scale of its global customer base, ranging from startups to large enterprises and government agencies.
</p>

## Global Infrastructure

<p align="justify">
AWS spreads its data centers around the world in groups called <b>Regions</b> (large areas like "US East" or "Asia Pacific"). Each Region is made up of smaller parts called <b>Availability Zones (AZs)</b>. Each AZ has its own power, cooling, and network, so if one AZ has a problem, the others keep working. AWS has many Regions around the world, and each one usually has at least 3 AZs. AWS also has <b>edge locations</b> (through a service called CloudFront) that help deliver content faster to users, and <b>Local Zones</b> for apps that need very low delay. Because of this setup, companies can build apps that stay online even if something fails in one area.
</p>

## Cloud Management Console

<p align="justify">
The <b>AWS Management Console</b> is a website where you can control and manage all your AWS services in one place. When you log in, you land on the <b>AWS Console Home</b> page. From there, you can:
</p>

- Search for any AWS service
- Check notifications
- Open **AWS CloudShell** (a built-in command-line tool)
- View your account and billing info
- Customize your settings

## Four (4) Core Services

1. **Amazon EC2 (Elastic Compute Cloud)** – Provides virtual servers in the cloud that can be resized anytime, making it ideal for hosting websites or running applications that need dedicated server power.

2. **Amazon S3 (Simple Storage Service)** – Gives you a place to store files online, such as photos, videos, or backups, and it automatically grows as more data is added — commonly used for storing user-uploaded files, backing up data, or hosting static website files like HTML pages.

3. **Amazon RDS (Relational Database Service)** – A managed database service where AWS handles the setup, updates, and backups for you, supporting popular databases like MySQL, PostgreSQL, and SQL Server, typically used to store organized data such as user accounts, orders, or inventory records.

4. **AWS IAM (Identity and Access Management)** – Controls who can access your AWS account and what actions they're allowed to take, which is useful for giving a developer access only to the servers they need while keeping billing information restricted to admins.

## Three (3) Advantages

1. **Most services to choose from** – AWS offers more types of servers, storage, databases, and tools than other providers, so you can pick exactly what fits your project.

2. **Biggest global network** – AWS has more data centers around the world than other cloud providers, making apps faster and more reliable no matter where users are.

3. **Trusted by all kinds of users** – Startups, big companies, and even government agencies use AWS. It also has strong security features to keep data safe.

## Typical Enterprise Use Cases

- Hosting scalable web and mobile application backends
- Big data analytics and data lakes (using services like Amazon Redshift and AWS Glue)
- Disaster recovery and backup
- Machine learning model training and deployment (Amazon SageMaker)
- Enterprise migration of legacy on-premises workloads to the cloud

---

## References

- Amazon Web Services. (n.d.). *Cloud computing services*. https://aws.amazon.com/
- Amazon Web Services. (n.d.). *AWS documentation*. https://docs.aws.amazon.com/
