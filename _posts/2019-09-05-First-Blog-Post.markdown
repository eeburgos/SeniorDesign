---
layout: "post"
title: "First Blog Post 9/05"
---
This is my first blog post for CIT 480, Senior Design.

Our first meeting for this class was two weeks ago, August 24th. Since then, for this class, we have had one lab assignment, Lab A, which introduced me to Docker Containers.

For this first assignment, the goal was to set up a Docker container on our local machine. My laptop is a PC running Windows 10. Though I had not worked with Docker prior to this assignment, I knew that running Docker on Windows was not the easiest and involved a longer set up compared to using MacOS or Linux. Because of this prior knowledge, I decided to install Linux on a separate partition on my HDD.

I decided that I would use Ubuntu as my Linux Distro. I went to the Ubuntu website and grabbed their LTS release, Ubuntu 18.04 Bionic Beaver. I created a 40GB partition on my HDD using Windows Disk Manager, used a utility known as Rufus to create a bootable USB from the Ubuntu ISO. Then followed the installation, powering down my laptop, powering it back on, entering the boot menu and selecting my bootable USB. The installation wizard was pretty straight forward, just as it has been when installing a VM, the only portion that needed careful attention was making sure the OS was set to install on the newly created partition and not the Windows partition. After the installation was complete, my laptop was capable of dual booting Windows and Ubuntu. Then it was finally time to set up Docker.

The installation of Docker was pretty straight forward. But before installing, I SSH'd into CSUN's "Sandbox" shell server through the terminal to test connectivity. Following a successful login, I then prepped my Ubuntu instance to install Docker. First I added the Docker repository by following the instructions on the Docker website. Once the repos were installed I was able to use the command:

sudo apt-get install docker-ce docker-ce-cli containerd.io

to install Docker. To make sure Docker was installed properly pulled my first Docker Image, Hello-World, then ran it using:

sudo docker run --name hello-world hello-World

then started the container with:

sudo docker start hello-World

Now that Docker was installed and working properly I had to pull a Docker Image from Professor Fitzgerald's directory on the Sandbox Server. To do this I used Secure Copy Protocol (SCP). After placing the docker image into a directory separate directory, I started the a the new container from the Dockerfile and entered into it as root and created a new user with the command:

adduser eeb29246 -gecos NULL

I then exited the container and logged back in with the new User I created then pulled a script from Professor Fitzgerald's directory in the Sandbox once again. The script was then ran in the container. This same script was also downloaded and ran on my own instance on the Sandbox server which links the two together. This was the ultimate goal of the assignment, to link up the Docker Container with my own instance on CSUN's sandbox server.  
