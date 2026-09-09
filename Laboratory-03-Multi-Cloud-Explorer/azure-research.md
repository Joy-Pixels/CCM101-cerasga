<div align="center">

<img src="https://github.com/Joy-Pixels/Portfolio/blob/429e0856c0236bbb46fbfce0bac854a72b7e270c/Azure%20Logo.jpg" width="80"/>

# Microsoft Azure

</div>

<p align="justify">
This document provides a research overview of Microsoft Azure, one of the world's leading cloud platforms. It covers Azure's background, global infrastructure, management console, four core services, key advantages, and typical enterprise use cases.
</p>

---

## Brief Overview

<p align="justify">
Microsoft Azure is Microsoft's cloud computing platform. It started in 2010, originally called "Windows Azure." Azure is a great choice for companies that already use Microsoft tools like Windows Server, Active Directory, Microsoft 365, and .NET, because it connects smoothly with all of them. Azure offers many of the same services as AWS, and it's especially good at hybrid cloud mixing on-site servers with cloud services.
</p>

<p align="justify">
Azure makes it easier to build modern apps, whether you run them fully in the cloud or connect them to your existing on-site systems. It helps you build apps that can grow, stay reliable, and are easy to maintain.
</p>

<p align="justify">
Azure works with popular programming languages like .NET, C++, Go, Java, JavaScript, Python, and Rust. It also connects easily with tools developers already use, like VS Code, Visual Studio, IntelliJ, and Eclipse so you can start being productive right away. On top of that, Azure gives you developer tools that make it simpler to build, deploy, and manage your cloud apps.
</p>

## Global Infrastructure

<p align="justify">
Azure's data centers are grouped into <b>Regions</b> (separate areas around the world). Regions are grouped into bigger areas called <b>Geographies</b>, which help companies follow data privacy and legal rules in their country. Some Regions are paired with another Region as a backup, so if something goes wrong, your data can recover from the paired location. Inside each Region, Azure uses <b>Availability Zones</b> — separate physical locations with their own power and network. This way, if one zone has a problem, your app can keep running from another zone. Azure also has a large network of edge locations to deliver content faster, plus a tool called <b>Azure Arc</b> that helps manage resources across on-site systems, other clouds, and Azure all together.
</p>

## Cloud Management Console

<p align="justify">
The <b>Azure Portal</b> is the primary web-based console for creating and managing Azure resources, offering dashboards, resource groups, and cost management tools. Azure also provides <b>Azure CLI</b>, <b>Azure PowerShell</b>, and <b>Azure Cloud Shell</b> for command-line and scripted management, along with the Azure mobile app for on-the-go monitoring.
</p>

## Four (4) Core Services

1. **Azure Virtual Machines** – Let you create virtual servers whenever you need them, and you can make them bigger or smaller depending on how much power your app requires, paying only for what you use. This is commonly used for running business apps, hosting websites, or testing software without buying physical servers.

2. **Azure Blob Storage** – Gives you a place to store large amounts of unstructured data, such as photos, videos, documents, and backups, and it automatically grows as more files are added, making it ideal for storing user uploads, keeping backup copies of important files, or hosting media for a website or app.

3. **Azure SQL Database** – A fully managed relational database where Microsoft handles maintenance, backups, and updates, allowing businesses to focus on their applications instead of managing the database themselves. Typically used for storing structured data like customer records, orders, or inventory.

4. **Azure Active Directory (Microsoft Entra ID)** – Manages who can log in and what they're allowed to access, both in the cloud and on company networks, and it connects closely with a company's existing on-premises Active Directory. Commonly used to let employees sign in once to access multiple company apps, or to control which employees can access sensitive company data.

## Three (3) Advantages

1. **Strong Microsoft integration** – Azure connects smoothly with tools many businesses already use, like Windows Server, Active Directory, Microsoft 365, and .NET, making it an easy fit for companies already using Microsoft products.

2. **Strong hybrid cloud support** – Tools like Azure Arc let a company manage its on-premises servers, other cloud providers, and Kubernetes clusters all from one place in Azure, without needing to move everything to the cloud. Azure Stack goes further by letting a company run actual Azure services on its own hardware.

3. **Trusted by large and regulated organizations** – Because of its deep ties to enterprise Microsoft tools, Azure is widely adopted by large companies, schools, and government agencies that already rely on Microsoft software.

## Typical Enterprise Use Cases

- Migrating on-premises Windows Server and Active Directory environments to the cloud
- Hosting and scaling .NET and enterprise line-of-business applications
- Hybrid cloud deployments that span on-premises and cloud infrastructure
- Enterprise identity and access management across Microsoft 365 and cloud apps
- Business intelligence and analytics via Power BI and Azure Synapse Analytics

---

## References

- Microsoft. (n.d.). *Azure documentation*. https://learn.microsoft.com/en-us/azure/
