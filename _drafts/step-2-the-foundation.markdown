---
layout: post
title:  "Step 2: The Foundation"
date:   2020-11-01
categories: Self-Hosting 
---

## Adding a layer

When I started this project I had an idea of my end goal, with some very specific targets I wanted
to hit, but I knew that along the path I would find things that required some adjustment.  For
instance: I figured I'd want to put pi-hole as a DNS server in place, but that was a fairly low
priority for the overall project.  Right up until it wasn't.  I realized while setting up Traefik
and working through a guide on that process that I'd need DNS in place internally for Traefik to be
able to work it's magic effectively. 

So while I was able to get Traefik up and working without DNS, and it's easy enough, it wasn't
working like I intended.  If someone is reading this and following along, I definitely suggest
starting with a DNS server, which makes life a little easier for other things beyond setting up
Traefik.  So that's the order I'll present the project in, even though it's not exactly how I did it. 

Another thing I realized fairly quickly is that I'll want to setup access from outside my LAN sooner
rather than later.  It's easier to troubleshoot a system with fewer moving pieces, so being able to
access a simple tool from both on and off my internal network is a good way to make sure that I've
got things working the way I like. 

## DNS via PiHole

[PiHole](https://pi-hole.net/) is a pretty nifty little project.  A lightweight DNS server that comes with a hefty default
block list just chock-full of Ad serving sites.  Every time a user loads a website with Ads each ad
is linked via DNS to a server delivering that Ad content.  PiHole just dumps those DNS requests in
pit of despair and thus, the end user never sees them.  They've got a lot of good documentation on
their website, and really setting it up is pretty straightforward.  

1. Install PiHole on a device
2. Point a device at the PiHole IP for it's DNS requests
3. Enjoy less ads

The exact steps needed for each piece of that will vary depending on all kinds of things. 

In my case it was a little more complex.  My router will allow me to define the DNS servers
manually, which is a good start, but it doesn't just re-direct DNS queries to the PiHole by default,
which leads to some weirdness, a little DuckDuckGoing and I found a setting that forces the router
to just push all queries to the PiHole[^router].  

It's also recommended to make the PiHole the DHCP server, which is great, except my router doesn't
off a setting to disable the DHCP server, and having two DHCP servers on a network is just a recipe
for disaster.  So again, there was some tweaking for my setup.  This will be the case for most
setups, since each network is going to have it's own quirks.  

## Traefik

[Traefik](https://traefik.io/) is a very cool project, it's a very powerful reverse proxy[^proxy], and it's got a ton of
options.  Which means that it can be very complex to configure, there's a lot going on, and there's
not really a 'point-and-click' install process for it.  This can turn some people off, and that's
totally understandable.  

For me, however, this is more about learning how things work, so why not
push myself and take the more difficult path.  If I was just trying to get a simple service up and
running, Traefik would not be the route I would take. I do plan on setting up multiple services, so
Traefik makes sense, especially since I'm planning on running most of them through Docker.  

Setting up Traefik wasn't especially difficult, and I only came across a single issue.  I used this
[tutorial](https://theorangeone.net/posts/hello-world-with-traefik/) written by TheOrangeOne, a very
knowledgeable individual, especially in the self-hosting arena.  

The single issue I came across was tied to Firewalld, specifically Firewalld doing it's job and
blocking traffic.  Putting in some rules to allow traffic on the needed ports (80, 443, 8080) fixed
the issue, and once I had my DNS up and running like it should, everything worked as intended.  

## OffNet Access

I made the choice to setup my offnet access at this point to simplify troubleshooting.  Once I had a
basic Traefik setup in place and running, I realized it would be easier to setup access into my
server with only a single service running, which will allow me to test access with only a few moving
parts.  

The basic goal for this was to have a VPS setup which will function as a gateway server of sorts
with a static IP I can point external DNS to, and allow that to forward traffic from the public
internet via VPN to my internal server.  

### VPS

To setup a gateway server requires a server.  Preferably with a static IP that can be easily
referenced by the public DNS services.  This is pretty easily done with a number of hosting
providers.  As this server will not really hold any of my personal data I'm not too worried about
the location of the server geographically, other than keeping it relatively close to my actual
location.  

I did some research and price comparison, and I chose [Linode](https://www.linode.com/) as my
hosting provider.  I picked their smallest server option "Nanode" which has 1G of Ram, 1 CPU, and
25G of storage. This should be plenty of power for what I'm trying to do.  I'll only be running two
applications, a proxy server, and a VPN server.  

Something important to remember is that this server is by it's very nature exposed to the internet.
So securing it is priority 1.  As soon as the server was up I:

- Created a non-root user
- Enabled SSH key authentication
- Disallowed root login over ssh
- Disabled password login over ssh
- Installed and configured fail2ban

This, in theory, should keep most of the riff-raff off of it.  I hope.  

### Wireguard

[Wireguard](https://www.wireguard.com/) is a new-ish player in the VPN space, but they are gaining a lot of traction for being easy to configure, and fairly lightweight. 

Again, I followed a basic setup guide from [TheOrangeOne](https://theorangeone.net/posts/wireguard-getting-started/), this is another pretty straightforward setup:

- Install Wireguard on both sides 
- Write the config files for the server and the client[^wg]
- Bring up the wireguard service on the Server
- Bring up the wireguard service on the client

At some point I will educate myself about the firewall well enough to block SSH traffic from
anything outside that VPN IP range on the server as another layer of security.  




## Resources

[^router]: I use an Amplifi Instant mesh setup from Ubiquiti which actually works very well as long  as you don't want to tinker with it too much.  The the WebUI setting `Bypass DNS Cache` has to be enabled, otherwise the router acts as a proxy for DNS requests, submitting the requests and serving them back to the device.  This can be seen in the PiHole logs easily, since the only device that shows up is the router.  

[^proxy]: A reverse proxy just takes inbound traffic and directs it to the correct location/port/service.

[^wg]: Client and server in this case referring to the *Wireguard* Client and server, my home server is the client in this case, and the VPS is the server.
