---
layout: post
title: "Step 1-Laying the Groundwork"
categories: Self-Hosting
---

## From the Bottom Up

Knowing where I want to go, means I know exactly where I need to start.  I've got the hardware, but
it's currently running EndeavourOS, and that's not going to work for me.  I want to run it on
CentOS, and knowing I'll be accessing it remotely, means I should be able to do a minimal install of
CentOS on the hardware and attach my external storage as part of the file system.  

## The Process  

My Goal here was to:
- Install CentOS 7
- Install Docker
- Test the docker install
- Install Docker Compose
- Test the basics to make sure Docker & Docker Compose were working as intended.

> No plan survives contact with the <s>Enemy</s> Computer

### The Operating System

I had a whole stack of issues getting CentOS to work, everything from struggles with bad USB drives
(maybe?) to the machine sleeping whenever it felt like it.  I suspect most of those struggles were
my own doing, nonetheless...off with it's head!!  As it were.  

I did actually get CentOS kinda working, and I got docker installed, but I screwed up the install
process and ended up installing the entire OS on my external drive, which was a not-good thing.  

I ended up using Fedora Server[^F32] instead of CentOS. The install process seemed to go more smoothly,
perhaps because I'd fixed some of the bugs in my process, but whatever the reason may be, I
currently have Fedora 32 installed on my laptop, which is hardwired[^wifi] to a dumb switch hanging off my
router.  Nifty.  DHCP reservation with a name gives me pseudo-DNS access to my laptop, including the
Fedora Server GUI which I really didn't know was a "thing".  The GUI is pretty nice, but mostly
useless for what I need, it works well and all, but I prefer the command line for most things, but I
do like the pretty pictures and graphs it gives me.  


When I re-installed Fedora for the (I think 7<sup>th</sup>) last time I managed to setup the drives the correct
way.  

Volume Groups:

![enterprise_vols](/assets/ent_vgs.png)

The Main OS Volume Group:

![fedora_vg](/assets/ent_fedora_vg.png)

The Data Volume Group:

![data_vg](/assets/ent_data_vg.png)

<sup>*Note the pretty pictures from the Fedora Server GUI.  Ain't they pretty?*</sup>

I've got two VGs, one for the data, and another for the OS type files. In this case they are on
separate physical drives.  This should in theory allow me to expand if I need more storage by simply adding an additional drive(s), this should also allow the system to boot in the event something happens to the external drive, or it doesn't mount right.  The internal drive will host most of the crucial functions this server will be handling, while the external will be used for data storage, i.e. my NextCloud storage. 

I also setup key-based authentication on my server to allow me to authenticate from my laptop to the
server without having to type in a password.  While you can use the `ssh-copy-id` method, I
actually used the Fedora Server GUI for that, which worked like a champ, but I couldn't find a way
to prevent password based SSH attempts in the GUI.  Removing that was easy enough (see the command
reference I used in the references section. [^sshd]) 

### Docker!

Thankfully Docker provides a very solid install guide for installing the docker-engine[^dock-guide]
unfortunately the base install process doesn't quite work for Fedora 32.  With some very very clever
Google-fu, googling the error, led me to an open Bug report[^bug], with an additional step needed to complete the install, once that was done: 

```bash
sudo docker run hello-world

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
```

BOOM!  Docker installed.


## Resources


[^F32]: [Fedora 32](https://getfedora.org/en/server/download/)

[^wifi]: We're not going to talk about wifi. OK? 

[^sshd]:  The tutorial I used can be found [here](https://ostechnix.com/configure-ssh-key-based-authentication-linux/) but the short version is: Put the key file on the remote server, turn off password based authentication in the `/etc/ssh/sshd_config` file, and restart ssh. 

[^dock-guide]:  The Install guide can be found [here](https://docs.docker.com/engine/install/fedora/)

[^bug]: The issue stems from the fact that cgroups v2 isn't supported by containerd 1.3 or lower.  The fix recommended by the docker team can be found [here](https://github.com/docker/for-linux/issues/955#issuecomment-694825085)


