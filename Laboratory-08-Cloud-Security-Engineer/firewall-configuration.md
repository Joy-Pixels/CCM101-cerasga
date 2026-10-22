# Checkpoint 6 - Technical Documentation

This document details the UFW (Uncomplicated Firewall) commands executed to secure the Ubuntu server deployed for CloudNova Technologies' client web application. The server was initially exposed to the public internet without any network security controls. The following steps establish a Default Deny policy and selectively allow only the services required for legitimate operation.

## Required Firewall Commands

### 1. Command used to allow SSH

<table>
  <thead>
    <tr>
      <th width="20%">Commands</th>
      <th width="35%">Purpose</th>
      <th width="45%">Figure</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>sudo ufw allow ssh</code></td>
      <td>Permanently allows SSH traffic so administrators can remotely manage the server without being locked out once the firewall is enabled.</td>
      <td><img src="https://github.com/Joy-Pixels/Portfolio/blob/3ac61223cee0c1889fcd804d462ddecd8a19be5f/Lab%208/allow%20ssh.png?raw=true" alt="SSH allowed and firewall activated" width="100%"></td>
    </tr>
  </tbody>
</table>

### 2. Commands used to set the Default Deny policy

<table>
  <thead>
    <tr>
      <th width="20%">Commands</th>
      <th width="35%">Purpose</th>
      <th width="45%">Figure</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>sudo ufw default deny incoming</code><br><code>sudo ufw default allow outgoing</code></td>
      <td>Blocks all incoming traffic by default while allowing the server to initiate outbound connections (e.g., for updates and package downloads), significantly reducing the attack surface.</td>
      <td><img src="https://github.com/Joy-Pixels/Portfolio/blob/3ac61223cee0c1889fcd804d462ddecd8a19be5f/Lab%208/Default%20Deny%20policy.png?raw=true" alt="Firewall activated with Default Deny policy" width="100%"></td>
    </tr>
  </tbody>
</table>

### 3. Command used to allow Port 8080

<table>
  <thead>
    <tr>
      <th width="20%">Commands</th>
      <th width="35%">Purpose</th>
      <th width="45%">Figure</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>sudo ufw allow 8080/tcp</code></td>
      <td>Creates a granular rule that permits legitimate web traffic to the Nginx application running on port 8080, while all other ports remain blocked by the Default Deny policy.</td>
      <td><img src="https://github.com/Joy-Pixels/Portfolio/blob/3ac61223cee0c1889fcd804d462ddecd8a19be5f/Lab%208/sudo%20ufw%20allow.png?raw=true" alt="Port 8080 allowed and application reachable" width="100%"></td>
    </tr>
  </tbody>
</table>

---

### 📍What would happen if `sudo ufw enable` was run before `sudo ufw allow ssh`?

Running `sudo ufw enable` before allowing SSH would activate the Default Deny policy and immediately block all incoming SSH connections, locking the administrator out of the remote server.

<br>

## Additional Verification Commands

<table>
  <thead>
    <tr>
      <th width="20%">Commands</th>
      <th width="30%">Purpose</th>
      <th width="50%">Figure</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>sudo ufw status verbose</code></td>
      <td>Confirms the firewall is active and shows the default policies.</td>
      <td><img src="https://github.com/Joy-Pixels/Portfolio/blob/3ac61223cee0c1889fcd804d462ddecd8a19be5f/Lab%208/firewall-activated.png?raw=true" alt="Output of ufw status verbose" width="100%"></td>
    </tr>
    <tr>
      <td><code>sudo ufw status numbered</code></td>
      <td>Lists the firewall rules with index numbers.</td>
      <td><img src="https://github.com/Joy-Pixels/Portfolio/blob/3ac61223cee0c1889fcd804d462ddecd8a19be5f/Lab%208/firewall-port-allowed.png?raw=true" alt="Output of ufw status numbered" width="100%"></td>
    </tr>
    <tr>
      <td><code>curl http://localhost:8080</code></td>
      <td>Confirms the web application remains reachable after the firewall is enabled.</td>
      <td><img src="https://github.com/Joy-Pixels/Portfolio/blob/3ac61223cee0c1889fcd804d462ddecd8a19be5f/Lab%208/curl.png" alt="Successful curl response after allowing port 8080" width="100%"></td>
    </tr>
  </tbody>
</table>

## Final Firewall State

<table>
  <thead>
    <tr>
      <th width="8%">Rule</th>
      <th width="10%">Port</th>
      <th width="14%">Protocol</th>
      <th width="14%">Action</th>
      <th width="54%">Purpose</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>22</td>
      <td>TCP</td>
      <td>ALLOW IN</td>
      <td>Remote administration (SSH)</td>
    </tr>
    <tr>
      <td>2</td>
      <td>8080</td>
      <td>TCP</td>
      <td>ALLOW IN</td>
      <td>Web application (Nginx)</td>
    </tr>
    <tr>
      <td>3</td>
      <td>22</td>
      <td>TCP (v6)</td>
      <td>ALLOW IN</td>
      <td>Remote administration (SSH) — IPv6</td>
    </tr>
    <tr>
      <td>4</td>
      <td>8080</td>
      <td>TCP (v6)</td>
      <td>ALLOW IN</td>
      <td>Web application (Nginx) — IPv6</td>
    </tr>
  </tbody>
</table>

Default policies:

- **Incoming:** DENY
- **Outgoing:** ALLOW
- **Routed:** DENY
