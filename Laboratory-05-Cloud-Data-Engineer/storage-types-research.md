# Checkpoint 2 - Research: Types of Cloud Storage

## Comparison Table

> A quick overview of how the three main cloud storage types differ in how they store data, what they're best for, and which cloud services provide them.

<table>
  <thead>
    <tr>
      <th width="16%" align="left" valign="top">Storage Type</th>
      <th width="28%" align="left" valign="top">Description</th>
      <th width="28%" align="left" valign="top">Primary Use Case</th>
      <th width="28%" align="left" valign="top">Cloud Provider Example</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="left" valign="top">🧱 <strong>Block Storage</strong></td>
      <td align="justify" valign="top">Block storage cuts data into small fixed-size pieces called blocks, each with its own address, and the computer puts them back together when needed. It's like plugging a <strong>raw hard drive</strong> into a server where the computer reads and writes blocks just like a normal disk.</td>
      <td align="justify" valign="top">Best for apps that need to <strong>read and write small pieces of data very fast</strong>, like <strong>databases</strong> and <strong>virtual machine disks</strong>, because speed matters a lot for them.</td>
      <td align="justify" valign="top">
        • <strong>Amazon EBS:</strong> Works like an external hard drive for EC2 instances; you can resize it and boost speed anytime.<br><br>
        • <strong>Azure Managed Disks:</strong> Microsoft's version of managed virtual hard drives for Azure VMs, easy to scale and maintain.<br><br>
        • <strong>Google Persistent Disks:</strong> Durable block storage for Google Compute Engine VMs, good for databases and system drives.
      </td>
    </tr>
    <tr>
      <td align="left" valign="top">📁 <strong>File Storage</strong></td>
      <td align="justify" valign="top">File storage saves data in folders and files, each with a name and a path, and many computers can open the same file system at the same time. It's like a <strong>shared network drive</strong> in an office where everyone opens the same folders and works on the same files, just like on their own computer.</td>
      <td align="justify" valign="top">Best for <strong>teamwork and sharing</strong>, like sharing design files, code, or config files, where many people or servers need to see and edit the same files at once.</td>
      <td align="justify" valign="top">
        • <strong>Amazon EFS:</strong> A shared drive that many EC2 instances can mount at once; grows automatically as you add files.<br><br>
        • <strong>Azure Files:</strong> Fully managed file shares in the cloud, accessible via SMB or NFS from many machines.<br><br>
        • <strong>Google Filestore:</strong> A high-performance shared file system for Google Cloud VMs, great for apps needing fast shared access.
      </td>
    </tr>
    <tr>
      <td align="left" valign="top">📦 <strong>Object Storage</strong></td>
      <td align="justify" valign="top">Object storage saves data as single units called "objects," each holding the data, a unique ID (Key), and extra info (metadata), with no folders and files found using the Key through HTTP APIs. It's like a <strong>huge parcel warehouse</strong> where each file is a parcel with a unique pickup code and labels, and you get it by showing the code.</td>
      <td align="justify" valign="top">Best for storing <strong>huge amounts of unstructured data</strong>, like user-uploaded images, videos, backups, and logs. Space is almost unlimited, it's cheap, and files can be reached from anywhere via URL.</td>
      <td align="justify" valign="top">
        • <strong>Amazon S3:</strong> The most popular object storage; extremely durable (11 nines) and lets clients upload directly via pre-signed URLs.<br><br>
        • <strong>Azure Blob Storage:</strong> Microsoft's object storage for massive unstructured data; great for images, videos, and backups with tiered pricing.<br><br>
        • <strong>Google Cloud Storage:</strong> Google's object storage with strong global performance and easy integration with CDNs and analytics tools.
      </td>
    </tr>
  </tbody>
</table>

## Why Object Storage Is the Best Choice for User-Uploaded Images

Your main need is to store user's uploaded images data that comes in **large amounts, is written once and almost never changed, and needs to be shown quickly to users around the world via URL**. Object storage (like Amazon S3, Azure Blob Storage, or Google Cloud Storage) is built exactly for this kind of data. It grows almost without limit, costs much less than block or file storage, and images can be served straight from HTTP URLs or a CDN without going through your server. By saving only the object storage URL in your database, you keep the database small and fast while letting the storage layer do what it does best.

<br>

## References

Nurudeen, M. (n.d.). *Cloud storage explained: Object, block, and file storage*. Medium. https://medium.com/@mustaphanurudeen488/cloud-storage-explained-object-block-and-file-storage-0cf9a44a3564
