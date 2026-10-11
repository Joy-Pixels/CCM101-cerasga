# Laboratory 5: The Cloud Data Engineer

<br>

## 🎯 Mission Overview
 
Congratulations! Your seamless deployment of containerized web servers has caught the attention of 
the senior architects. You have now been temporarily reassigned to the **Cloud Data Engineering Team** at 
CloudNova Technologies. 

In the cloud, data is everything. However, not all data is stored the same way. While traditional 
computers use hard drives (Block Storage) and shared network drives (File Storage), modern cloud applications 
rely heavily on **Object Storage** to store massive amounts of unstructured data like images, videos, and backups. 
The industry standard for this is Amazon S3, but today, you will deploy your very own S3-compatible cloud 
storage server using an open-source tool called **MinIO**. 

Using your KillerCoda Playground, you will combine your new Docker skills with your cloud storage knowledge to 
deploy a live object storage server, create a storage "bucket," and upload data over the web. 

> Remember: A cloud engineer doesn't just store data; they ensure it is scalable, accessible, and secure. 

---

## 📋 Objectives

By completing this laboratory activity, I was able to:

- Differentiate between Block, File, and Object Storage.
- Deploy an S3-compatible Object Storage server (MinIO) using Docker.
- Access a cloud service through a web interface using port forwarding.
- Create a storage bucket and upload objects (files) to the cloud.
- Document cloud storage operations using Markdown.
- Continue expanding a professional GitHub Cloud Computing Portfolio.

---

## 🛠️ Tools Used

<table>
<tr>
<td width="80" align="center"><h1><img src="https://github.com/Joy-Pixels/Portfolio/raw/f1fc74ab84404cb8fb0ff9f5ec7d3980476a9457/killercoda.png" width="50"></h1></td>
<td>

**KillerCoda:**
KillerCoda is a free, browser-based interactive learning platform that
provides temporary Linux sandbox environments for practicing DevOps,
Kubernetes, and cloud-related skills without needing to install
anything locally. It was used to launch an Ubuntu Playground where
Docker commands were run and the MinIO console was accessed through
the Traffic / Ports tab.

</td>
</tr>
<tr>
<td width="80" align="center"><h1><img src="https://github.com/Joy-Pixels/Portfolio/raw/main/docker.png" width="50"></h1></td>
<td>

**Docker:**
Docker is a platform that packages applications into lightweight,
portable containers. It was used to pull the MinIO image and run the
storage server with port mappings (`-p`) and environment variables
(`-e`) in a single command.

</td>
</tr>
<tr>
<td width="80" align="center"><h1><img src="https://github.com/Joy-Pixels/Portfolio/raw/main/MinIO.png" width="50"></h1></td>
<td>

**MinIO:**
MinIO is an open-source, S3-compatible object storage server. It was
used to create the private `client-photos` bucket and upload test
files through its web console. The community fork `pgsty/minio` was
used because the official image was unavailable.

</td>
</tr>
<tr>
<td width="80" align="center"><h1><img src="https://github.com/Joy-Pixels/Portfolio/raw/main/github.png" width="50"></h1></td>
<td>

**GitHub and Markdown:**
GitHub is a platform for hosting code and tracking changes with Git,
and Markdown is a lightweight language for formatting text. Together
they were used to document each checkpoint and keep the Cloud
Computing Portfolio organized and version-controlled.

</td>
</tr>
<tr>
<td width="80" align="center"><h1><img src="https://github.com/Joy-Pixels/Portfolio/raw/f1fc74ab84404cb8fb0ff9f5ec7d3980476a9457/Claude.jpg" width="50"></h1></td>
<td>

**Claude:**
Claude is an AI assistant developed by Anthropic that can help with
tasks like research, writing, and technical documentation. It was
used for guidance, troubleshooting the MinIO image errors, and
formatting the documentation while working through the laboratory
tasks.

</td>
</tr>
</table>

<br>

---

## 💡 Skills Learned

- Learned how to compare and differentiate block, file, and object storage based on their architecture and use cases.
- Learned how to deploy an S3-compatible object storage server using Docker on a cloud-based Linux environment.
- Learned how to configure a containerized server using environment variables with the `-e` flag.
- Learned how to access and use the MinIO web console to create buckets and upload objects.
- Learned how to troubleshoot Docker image pull failures and resolve them using a community fork.
- Learned how to document technical steps clearly using Markdown, tables, and code blocks.

---

## 📁 Repository Contents

| File | Description |
| :--- | :--- |
| [`storage-types-research.md`](storage-types-research.md) | Comparison of block, file, and object storage |
| [`minio-deployment.md`](minio-deployment.md) | Technical documentation of the MinIO deployment |
| [`reflection.md`](reflection.md) | Mission reflection |
| [`screenshots/`](screenshots/) | Evidence screenshots |
