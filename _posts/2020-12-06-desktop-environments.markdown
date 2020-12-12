---
layout: post
title: "Choosing a Desktop Environment"
categories: Beginners Customization Configuration
---

## What is a Desktop Environment

If you're coming from the Windows or Mac/OSX world you're familiar with desktop environment.  You
probably haven't ever thought about it beyond setting a background image or wallpaper, or rearranging
your application icons in a funny pattern.  The graphical desktop has been around for a very long
time, and at this point it's one of the fundamental pieces of using a computer.  

With both Windows and OSX you don't really get much of a choice when it comes to which Desktop
Environment you get.  In Windows you get the start menu button in the bottom left corner of the
screen, the bar on the bottom of the screen where all of your open applications live, a nifty little
recycle icon on the desktop etc.  The Windows desktop environment is more than just that though.

You may be familiar with using the Command Prompt to do some things, or PowerShell even.  You get
the same Image viewer, task manager, and lots of other tools that might not seem to be part of the
"desktop", they are part of the basic "Windows Experience" that millions of people have become
familiar with over the last 30 years or so.  

The Desktop Environment (DE for short) comes with all kinds of little things that make
using a computer easier.  They'll typically include at least (but not limited too): 

- A Terminal
- A wallpaper setting tool
- An image viewer
- A graphical file manager
- Customization Options
- Panel 
- Session manager

Some DEs include tools to connect with your Android phone, or music players, email clients, and the
list can go on and on and on.....

This may all seem pretty obvious, but it's not something people tend to think about.  It's something
important to keep in mind when preparing to install a Linux distro on your machine, and even more
important to think about when distro hopping.[^hopping] Frequently I see new Linux users trying to
compare one distro to another, but really what they're comparing is a feature of one DE to another.  

## Comparing Desktop Environments

The DE is essentially the one thing you will interact with when it comes to you actually using your
computer.  It will control how you open applications, what your desktop looks like, where the
buttons are, how the system notifies you about things, in short: The DE controls *how* you interact
with your computer.  

I've heard a couple of the more well-known Linux YouTube personalities offer the opinion that which
distro you choose is essentially irrelevant and that it's more important to pick a DE that you like,
and that works for you. I would almost completely agree with that, and for someone just dipping
their toes in the vast ocean that is Linux, I'd say picking the DE is substantially more important
than which distro someone uses.  

With that in mind I'll share some of my thoughts on some of the more popular DEs, and try to make
some basic comparisons about them.  Ultimately choosing the "right" DE is up to you, but hopefully I
can provide some info to help you determine which DE might be the best for you.  

As with all things Linuxy, there is not really a single right answer, and the choice doesn't have to
be permanent.  You can try multiple DEs and find the one that works best for you. There are plenty
of other options beyond the four I've listed below, I encourage you to do your own research, and
while I've included videos for each of them, check out the individual project websites, the
information below is really just intended to be a starting point. 

### Gnome

Lets start with the Elephant in the Linux user space.  Gnome is extraordinarily popular, it's the
default DE for several major Distros (Ubuntu and Fedora among others).  It's fully fleshed out and
offers what many would consider a fantastic user experience.  

Gnome has a very unique look, and provides some truly fantastic tools for getting things done.  It
integrates well with cloud services like Google providing a seamless experience for end users.  

This is a 5 minute walkthrough of the latest version of Gnome (at the time of this writing Gnome 3)
{% include youtubePlayer.html id="BB7pBRi9Bbk" %}

For more information check out the project's webpage:  [Gnome.org](https://www.gnome.org/)

### KDE 

KDE is another very popular, well-built, fully featured DE.  The project has been around for quite
some time, and they've one of the best looking DEs out there.  The Plasma desktop is truly good
looking, and offers a ton of customization options, and lots of really cool features.  They offer a
giant [list of applications](https://apps.kde.org/) that integrate tightly with the DE, offering a
really good user experience.  

One of the more interesting features KDE offers is the KDE connect feature which allows integration
between an Android phone and the computer. 

A quick tour of the latest version from KDE: 

{% include youtubePlayer.html id="h_YdaFNsPBE" %} 

As always check out the [project website](https://kde.org/) for more information

### Cinnamon

Cinnamon is kind of an outlier in this list.  It is one of the few DEs that doesn't have a dedicated
project (it's built and maintained by the [Linux Mint team](https://linuxmint.com/)), it is
available for most distros. In my opinion, one of the best things about Cinnamon, is that it feels a
lot like Windows.  It makes transitioning to Linux a bit easier for those who aren't looking for
something wildly different.  I actually used Cinnamon and Linux Mint for quite sometime, and found very few
negative things to whine about, it was a very solid option, and is still something I recommend for
many people.  

Have another 5 minute video tour: 

{% include youtubePlayer.html id="TBSwFc6hkLY" %}

For more information about Linux Mint and Cinnamon click [here](https://linuxmint.com/)

### XFCE

The XFCE project prides itself on making a lightweight DE, that is still fully featured.  All of the
basic important things are there.  Admittedly, it's not the best looking DE when it's installed, but
it is incredibly customizable, and with some tweaking it can look very good.  

Another quick video:

{% include youtubePlayer.html id="9ABYlcmqQ-Q" %}

The XFCE project actually has very nice tour of version 4.14 [here](https://xfce.org/about/tour)

## Other Options

Fully packaged desktop environments are probably the most commonly used options, but there are other
options:
- No Desktop at all.  Interacting with the machine only through a terminal interface is very common
  with servers.
- Window managers. These are tools that provide a method for having graphical displays running, but
  do not function as a full desktop environment.  This can provide more control over the user experience, but takes a bit more configuration than a typical DE. I will cover some of the window manager options and configuration in another post. 

## Further Reading

[What is Linux]({% post_url 2020-10-03-what-is-linux %})                                                                                                                                                         

[Why should you use Linux]({% post_url 2020-10-04-why-linux %})

[Which Linux should you use?]({% post_url 2020-10-11-which-linux %})

### Footnotes
[^hopping]: Distro hopping is changing from one distro to another, something many people do, especially when first starting out with Linux.  Generally it's done in an effort to find the "perfect distro". 
