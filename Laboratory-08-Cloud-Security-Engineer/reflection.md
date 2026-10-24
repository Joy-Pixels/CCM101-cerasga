# 📖 Mission Reflection

Completing this mission helped me see that cloud security is not just a one-time task but something that needs constant attention. It also showed me how easily an unprotected server can be taken advantage of.

A host-based firewall protects a server even if the network perimeter is already broken because it works directly on the machine itself. It filters traffic at the operating system level, acting like a final guard that only lets approved connections through. Even if an attacker gets inside the network, the firewall still blocks anything that is not explicitly allowed.

Managing open ports is important for reducing a server's attack surface because every open port is another way in. Each service that is running could have weaknesses, and the more services that are exposed, the easier it is for an attacker to find a way inside. By closing ports that are not needed and allowing only the required ones, I greatly reduced the number of entry points an attacker could use.

In a real company, leaving a database port like 3306 for MySQL open to the public internet is very dangerous because it allows anyone to try to break into the database. A database should only be reachable through a private network or a secure connection. If it is exposed publicly, it can lead to stolen data, ransomware attacks, or even full system takeover.

This mission changed how I think about how easy it is for a server to be compromised. Before this activity, I did not realize that just a few missing steps could leave a server completely open. Watching the firewall block everything by default and then allowing only specific ports helped me understand why careful configuration matters so much.

With eight missions finished, my GitHub Cloud Computing Portfolio now looks organized and professional. Each laboratory builds on the one before it, and the consistent documentation and evidence show my growth as a cloud practitioner.
