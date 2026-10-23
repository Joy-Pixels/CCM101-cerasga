# Checkpoint 2 - Security Audit Report 

This report documents the core cloud security concepts applied during Mission 8. These principles guided the decision to deploy a web application, audit its exposed services, and configure a host-based firewall with a strict Default Deny policy.

<br>

## The Principle of Least Privilege (PoLP)

The Principle of Least Privilege (PoLP) is a security concept that restricts access rights for users, applications, and systems to the bare minimum needed to complete their tasks. In cloud environments, applying PoLP to user accounts is essential because it reduces the impact of compromised credentials—an attacker who gains access to a low‑privilege account cannot escalate to administrative control. For example, a CI/CD pipeline should only be allowed to deploy to specific resources, not manage billing or IAM policies.

<div align="center">
  <img src="https://www.techtarget.com/rms/onlineimages/hierarchy_of_polp_account_types-f.png" alt="Hierarchy of PoLP account types" width="500">
</div>

*Figure 1: Hierarchy of account types illustrating the Principle of Least Privilege, where permissions increase only as necessary for specific roles.*

---

## Attack Surface

The term “attack surface” refers to the total number of ways an attacker could try to break into a system, including open ports, running services, user accounts, and software vulnerabilities. When applied to a virtual machine, the attack surface is essentially the sum of all network‑accessible services and their configurations—every open port is a potential entry point. Reducing the attack surface by closing unused ports and limiting access is one of the most effective ways to harden a server.

<div align="center">
  <img src="https://gkaccess.com/wp-content/uploads/2020/01/Attack-vector_GateKeeper_security_compliance_proximity_authentication-scaled.jpg" alt="Attack vector and security compliance" width="500">
</div>

*Figure 2: Visual representation of attack vectors and the importance of reducing exposed entry points to harden a system.*

---

## Default Deny Policy

A Default Deny policy is a firewall configuration that blocks all traffic by default and only allows traffic that is explicitly permitted. It is safer than trying to block specific hackers individually because it does not depend on knowing every possible threat—any traffic that is not explicitly allowed is automatically denied. This approach enforces a “deny by default” mindset, ensuring that even if a new service is accidentally exposed, it remains protected unless an administrator deliberately creates an allow rule.

<div align="center">
  <img src="https://tuxcare.com/wp-content/uploads/2025/02/default-deny-vs-default-allow-firewall-policy.png.webp" alt="Default deny vs default allow firewall policy" width="500">
</div>

*Figure 3: Comparison of Default Deny versus Default Allow firewall policies, highlighting why denying all traffic by default is the more secure approach.*

---

## References

- TechTarget. (n.d.). *Hierarchy of PoLP account types* [Image]. Retrieved from https://www.techtarget.com/rms/onlineimages/hierarchy_of_polp_account_types-f.png
- GateKeeper Security. (2020). *Attack vector and security compliance* [Image]. Retrieved from https://gkaccess.com/wp-content/uploads/2020/01/Attack-vector_GateKeeper_security_compliance_proximity_authentication-scaled.jpg
- TuxCare. (2025). *Default deny vs default allow firewall policy* [Image]. Retrieved from https://tuxcare.com/wp-content/uploads/2025/02/default-deny-vs-default-allow-firewall-policy.png.webp
