<div align="center">

<img src="https://github.com/Joy-Pixels/Portfolio/blob/429e0856c0236bbb46fbfce0bac854a72b7e270c/GCP%20Logo.jpg" width="80"/>

# Google Cloud Platform (GCP)

</div>

<p align="justify">
This document provides a research overview of Google Cloud Platform (GCP), one of the world's leading cloud platforms. It covers GCP's background, global infrastructure, management console, four core services, key advantages, and typical enterprise use cases.
</p>

---

## Brief Overview

<p align="justify">
Google Cloud Platform (GCP) is Google's cloud computing service, started in 2008. It runs on the same powerful network that powers Google Search, Gmail, and YouTube. GCP is best known for data analytics, AI and machine learning, and Kubernetes, a tool Google created for managing containerized apps, which it still leads today through its managed service, Google Kubernetes Engine (GKE).
</p>

## Global Infrastructure

<p align="justify">
GCP infrastructure is organized into <b>Regions</b> (independent geographic areas) and <b>Zones</b> (isolated locations within a Region, GCP's equivalent to AWS/Azure Availability Zones). GCP also operates a private global fiber network connecting its data centers, which helps reduce latency between services and improves performance for data-intensive workloads. Google's Premium Tier network routes traffic over this private backbone rather than the public internet whenever possible.
</p>

## Cloud Management Console

<p align="justify">
The <b>Google Cloud Console</b> is the web-based interface for managing GCP projects, resources, and billing this is the page shown in the screenshot above. GCP also gives you other ways to manage things: the <b>gcloud CLI</b> (a command-line tool), <b>Cloud Shell</b> (a free browser-based terminal that comes with tools already installed, so you don't need to set anything up), and client libraries/SDKs for connecting to GCP services through code.
</p>

## Four (4) Core Services

1. **Compute Engine** – Lets you create virtual machines that you can resize as needed, paying only for what you use. This is GCP's version of AWS EC2 or Azure VMs. Commonly used for hosting apps or running workloads that need dedicated computing power.

2. **Cloud Storage** – A place to store files like photos, videos, and backups, similar to AWS S3 or Azure Blob Storage. It grows automatically as you add more data. Ideal for storing backups, media files, or large datasets.

3. **Cloud SQL** – A fully managed database service that supports MySQL, PostgreSQL, and SQL Server, with Google handling maintenance and backups for you. Typically used for storing organized business data like customer or order records.

4. **Google Kubernetes Engine (GKE)** – A managed service for running containerized apps using Kubernetes, the technology Google itself created. Commonly used for running modern apps built from many small, independent services, known as microservices.

## Three (3) Advantages

1. **Strong in AI and data analytics** – Tools like Vertex AI, BigQuery, and TensorFlow make GCP a top choice for businesses working with AI or large amounts of data.

2. **Best Kubernetes support** – Since Google created Kubernetes, GCP offers the most mature and reliable managed Kubernetes experience through GKE.

3. **Fast, reliable global network** – Google's own private network keeps traffic fast and consistent between services and regions worldwide.

## Typical Enterprise Use Cases

- Processing and analyzing big data (using BigQuery, Dataflow, Dataproc)
- Building and deploying AI/machine learning models (using Vertex AI)
- Running containerized apps with Kubernetes (GKE)
- Handling real-time data streams and pipelines
- Supporting media, gaming, or other apps that need fast, high-volume global networking

---

## References

- Google. (n.d.). *Google Cloud*. https://cloud.google.com/
