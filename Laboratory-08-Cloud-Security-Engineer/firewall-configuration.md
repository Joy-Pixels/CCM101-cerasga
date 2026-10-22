# Checkpoint 6 - Technical Documentation

This document details the UFW (Uncomplicated Firewall) commands executed to secure the Ubuntu server deployed for CloudNova Technologies' client web application. The server was initially exposed to the public internet without any network security controls. The following steps establish a Default Deny policy and selectively allow only the services required for legitimate operation.

## Required Firewall Commands

### 1. Command used to allow SSH

| Commands | Purpose | Evidence |
|----------|---------|----------|
| `sudo ufw allow ssh` | Permanently allows SSH traffic so administrators can remotely manage the server without being locked out once the firewall is enabled. | <img src="screenshots/firewall-activated.png" alt="SSH allowed and firewall activated" width="350"> |

### 2. Commands used to set the Default Deny policy

| Commands | Purpose | Evidence |
|----------|---------|----------|
| `sudo ufw default deny incoming`<br>`sudo ufw default allow outgoing` | Blocks all incoming traffic by default while allowing the server to initiate outbound connections (e.g., for updates and package downloads), significantly reducing the attack surface. | <img src="screenshots/firewall-activated.png" alt="Firewall activated with Default Deny policy" width="350"> |

### 3. Command used to allow Port 8080

| Commands | Purpose | Evidence |
|----------|---------|----------|
| `sudo ufw allow 8080/tcp` | Creates a granular rule that permits legitimate web traffic to the Nginx application running on port 8080, while all other ports remain blocked by the Default Deny policy. | <img src="screenshots/firewall-port-allowed.png" alt="Port 8080 allowed and application reachable" width="350"> |

---

### 📍What would happen if `sudo ufw enable` was run before `sudo ufw allow ssh`?

Running `sudo ufw enable` before allowing SSH would activate the Default Deny policy and immediately block all incoming SSH connections, locking the administrator out of the remote server.

<br>

## Additional Verification Commands

| Commands | Purpose | Evidence |
|----------|---------|----------|
| `sudo ufw status verbose` | Confirms the firewall is active and shows the default policies. | See `firewall-activated.png` |
| `sudo ufw status numbered` | Lists the firewall rules with index numbers. | See `firewall-port-allowed.png` |
| `curl http://localhost:8080` | Confirms the web application remains reachable after the firewall is enabled. | See `firewall-port-allowed.png` |

## Final Firewall State

| Rule | Port | Protocol | Action | Purpose |
|------|------|----------|--------|---------|
| 1 | 22 | TCP | ALLOW IN | Remote administration (SSH) |
| 2 | 8080 | TCP | ALLOW IN | Web application (Nginx) |
| 3 | 22 | TCP (v6) | ALLOW IN | Remote administration (SSH) — IPv6 |
| 4 | 8080 | TCP (v6) | ALLOW IN | Web application (Nginx) — IPv6 |

Default policies:

- **Incoming:** DENY
- **Outgoing:** ALLOW
- **Routed:** DENY
