# 🤔 Reflection — Mission 4: The Cloud-Native Engineer

This mission taught me a lot about Docker containers and how they are different from Virtual Machines. I learned that containers are faster, lighter, and easier to use, and I can see why many companies are switching to them.

The boot time and setup process of a Docker container is much faster than a Virtual Machine. With a VM, you have to set up the RAM, CPU, and disk, and then install a whole operating system before you can use it. That takes a lot of time. With Docker, you just pull an image and run it, and it starts in seconds. In this mission, my Nginx container started almost right away, while a VM would have taken a minute or more just to boot.

Port mapping is important because containers are closed off from the host by default. Inside the container, Nginx listens on port 80, but you cannot reach it from outside unless you map it. By using `-p 8080:80`, we tell Docker to send traffic from port 8080 on the host to port 80 inside the container. Without this, the web server would run but no one could open it.

When I use `docker rm`, the container is fully deleted. All the data inside it, the files, logs, and any changes are gone forever. This is why containers are meant to be temporary. If you want to keep data, you have to use volumes to store it outside the container.

Containerization changes how developers and IT teams work together. Developers can pack an app with everything it needs into one image, and the IT team can run that same image in production without any problems. This means fewer mistakes and faster releases. It also helps both teams talk to each other more, which is what DevOps is all about.

My GitHub portfolio is growing little by little. Each activity adds new files, screenshots, and proof of what I can do. This mission taught me how to write documentation using Markdown, and my repository now looks more organized and professional. I am proud of how far I have come, and I am excited to keep learning more about cloud computing.
