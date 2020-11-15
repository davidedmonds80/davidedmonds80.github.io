---
layout: post
title: "Planning my Own Cloud"
categories: Self-Hosting 
---

## The Goal

I've used cloud services pretty steadily for the last 10 years or so.  My documents, résumés,
pictures, everything really, all lives in the cloud.  As companies and governments get more and more
blatant about their disregard for our privacy in favor of their profits, I've moved from cloud
service, to cloud service.  I've used everything from Google to iCloud, to Microsoft's OneDrive, and
ended up settling on NextCloud hosted in a GPDR compliant country.  Which is good, really good
actually.  Except for one issue, it's *slow*, like dial-up slow.  As a place to archive it's fine,
but for anything I want to use on a semi-speedy basis, it's essentially unusable. (Think finding a
picture from a year ago to paste in a group chat)

So to have an option that is relatively speedy, but still as secure as I can get it, I've come to
the conclusion that I need to self-host my own NextCloud instance.  

Which sounds easy, and can be, assuming you only want to access your data on your home network.
Which is a perfectly viable option for many people. 

I like to be complex, and do things the hard way.  So here's the End State goal:

- Privately hosted [Nextcloud](https://nextcloud.com/) instance
- Privately hosted Website (very very future state)
- Internal DNS via [PiHole](https://pi-hole.net/) for ad blocking
- Reverse Proxy for traffic routing via [Traefik](https://traefik.io/)

I think at this point everything will be running on an old laptop I've got laying around.  It's got
8G of RAM (upgradable) and a Core i5 so for my use case I think it should be able to handle
everything, at least to begin with.  

I'll be running Docker, and I *think* Docker Compose to manage the containers


### The Tools

Starting from the base up:

#### Hardware

The home network is Gig fiber to a Ubiquiti Amplifi mesh router

The Laptop in question is a Dell Latitude E6440 with a Core i5 and (currently) 8 gigs of Ram, with a
relatively small SSD (120G), most of the storage will be hosted on an external 2TB SSD. 

#### Software
- Base Operating System: CentOS
    - As I've mentioned, in my day job I do some Linux Admin type stuff, and I've got a fair amount
      of experience with CentOS in a server role.  It does that very well.  It works, and I'm
      comfortable in the RHEL/Fedora/CentOS space.  I figure I might as well stick with something
      I'm comfortable with. 
- Docker/Docker Compose for container management
    - I'll be using Docker compose for simplicity of managing the containers, for upgrades, repairs
      etc. 
- Nextcloud for most cloud functions
    - NextCloud offers an incredibly simple UI for others to use, as well as compatibility with
      pretty much every OS out there.  In a house with: Windows, Linux, ChromeOS, iOS, iPadOS;
      interoperability and ease of use is a **huge** thing
- PiHole for DNS/Ad Blocking
    - PiHole is great for dropping ad traffic in a blackhole never to report telemetry again.  This
      may end up running on a spare RasperryPi that I have laying around, but my intention at this
      time is to put it on the main server.  

### The Path

This is where things start to get a bit muddy.  This is kind of what I'm thinking right now:
1. Work through some basic docker tutorials
2. Work through some basic docker compose tutorials
3. Add Traefik to the main server, and work with pointing it at different containers
4. Install a NextCloud docker container
5. Install a PiHole container
6. Profit???

All of this is of course subject to whims of fate and time. So who knows what this path will look
like in the end.  I'd like to think that I'm going to continue to update this as I go through the
process, so we'll see how that goes.  

Continue this series [here]({% post_url 2020-10-18-step1 %})    
