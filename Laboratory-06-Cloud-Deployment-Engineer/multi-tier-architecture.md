# Checkpoint 2 - Research: Multi-Tier Architecture

Before diving into the deployment, it helps to understand what a multi-tier architecture actually is and why it matters. This research breaks down the two-tier model, explains the role of each tier, and shows why separating the web and database into different containers makes the system more reliable and professional.

---

## What is a Two-Tier Architecture?

A Two-Tier Architecture is basically when an application is split into two parts that talk to each other: a **client side** that people see and use, and a **database side** that stores all the important information. The client sends a request, the database processes it and sends back the result. It's called "two-tier" because there are only two main layers doing the work. In this mission, the Nextcloud container is the client side, and the MariaDB container is the database side, and they're connected using Docker Compose. So instead of one big messy program doing everything, we have two separate pieces working together, which makes the whole system easier to manage.
<br>
<br>

<p align="center">
  <img src="https://media.geeksforgeeks.org/wp-content/uploads/20240907155154/2.png" alt="Two-Tier Architecture Example" width="500">
</p>

> *The diagram above shows how the client (user interface) communicates directly with the database server. This is the basic structure of a two-tier architecture.*

---

## The Web / Application Tier

The Web/Application Tier is like the "face" of the system. It's the part users actually see and click on. When someone opens their browser and goes to the Nextcloud page, this tier is what responds to them. It shows the login screen, the file list, the buttons, everything. It handles all the HTTP requests coming from the browser and decides what to show next. But here's the important thing: it doesn't actually store any of the data permanently. It just shows stuff and passes requests along to the database when it needs real information. In our case, this is the **Nextcloud container** running on port `8080`. I think of it like a receptionist. It greets you, handles your questions, and only bothers the records room when it actually needs to look something up.

---

## The Database Tier

The Database Tier is like the "brain" or "memory" of the system. Its whole job is to **store and protect persistent data**, the stuff that has to survive even if the server restarts. That means user accounts, passwords, file names, file sizes, who owns what, and who's allowed to see what. It handles all the actual reading and writing of data, makes sure nothing gets corrupted, and responds to queries from the web tier. In our deployment, this is the **MariaDB container**, and it just sits quietly in the background. Users never interact with it directly, and only the Nextcloud container is allowed to talk to it. It's like the records room in a building. You can't just walk in, you have to go through the receptionist first.

---

## Why Separate Them?

Keeping the web server and database in separate containers is way better than cramming them into one, because **each side can be fixed, upgraded, or scaled on its own without messing up the other**. If the university gets more students and the database starts slowing down, we can give the database container more power without touching the web container at all. And if the web container crashes or gets hacked, the database and all its data are still safe in a separate place. It also makes the system more secure, since users can never directly reach the database. Honestly, before this lesson I thought putting everything in one container was simpler, but now I see that separating them is what makes a system actually reliable and professional. It's like having different departments in a company instead of one person trying to do every single job.

---

## References

GeeksforGeeks. (2016, August 13). *Types of DBMS architecture*. https://www.geeksforgeeks.org/dbms/dbms-architecture-2-level-3-level/

GeeksforGeeks. (2022, February 21). *Three-tier client server architecture in distributed system*. https://www.geeksforgeeks.org/computer-networks/three-tier-client-server-architecture-in-distributed-system/

GeeksforGeeks. (2024). *Two-tier architecture diagram* [Image]. https://media.geeksforgeeks.org/wp-content/uploads/20240907155154/2.png
