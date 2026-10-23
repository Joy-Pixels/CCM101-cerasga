# Laboratory 08 — Cloud Security Engineer

## 🛰️ Mission Overview

Congratulations! Your proactive approach to system monitoring has earned you a spot on the elite Cloud Security Team at CloudNova Technologies.

In the cloud, leaving a server unsecured for even a few minutes can lead to automated brute-force attacks and data breaches. Your mission today applies the security concepts you learned in Chapter 8. You will implement the principle of defense in depth by locking down a live server using a host-based firewall.

Using the KillerCoda Playground, you will step into the role of a Cloud Security Engineer. You will deploy a web application, audit the server's open ports, and configure the Uncomplicated Firewall (UFW) to block malicious traffic while allowing legitimate users to access the application.

> Remember: Security is not a product you buy; it is a continuous process you maintain.*

## 🎯 Objectives

At the end of this laboratory activity, you should be able to:

- Understand the concept of the Attack Surface and the Principle of Least Privilege (PoLP).
- Perform a basic security audit of active network ports on a Linux server.
- Configure the Uncomplicated Firewall (UFW) with a Default Deny policy.
- Implement granular port management to selectively allow SSH and HTTP traffic.
- Document firewall rules and security best practices using Markdown.
- Continue expanding your professional GitHub Cloud Computing Portfolio.

## 💻 Commands Executed

| Command | Description |
|---------|-------------|
| `docker run -d --name secure-web-app -p 8080:80 nginx` | Deployed an Nginx web server container on port 8080 |
| `docker ps` | Verified the container is running and mapped correctly |
| `curl http://localhost:8080` | Tested that the web application is reachable |
| `sudo ufw allow ssh` | Permanently allowed SSH (Port 22) for remote administration |
| `sudo ufw default deny incoming` | Set the default policy to block all incoming traffic |
| `sudo ufw default allow outgoing` | Set the default policy to allow all outgoing traffic |
| `sudo ufw enable` | Activated the firewall on system startup |
| `sudo ufw status verbose` | Verified the active firewall status and default policies |
| `sudo ufw allow 8080/tcp` | Allowed TCP traffic on port 8080 for the web application |
| `sudo ufw status numbered` | Listed all firewall rules with index numbers |
| `curl http://localhost:8080` | Confirmed the web application is still reachable after firewall activation |

## 🧰 Skills Learned

1. I learned about attack surfaces and how closing unused ports reduces a server's exposure.

2. I learned about UFW Firewall Management, including how to enable it, check its status, and manage rules.

3. I learned about the Principle of Least Privilege (PoLP) and how a Default Deny policy blocks all traffic unless explicitly allowed.

4. I learned about granular port management by allowing only SSH (port 22) and the web application (port 8080) while keeping everything else closed.

5. I learned about defense in depth and the safe order of operations, such as allowing SSH before enabling the firewall to avoid locking myself out.
