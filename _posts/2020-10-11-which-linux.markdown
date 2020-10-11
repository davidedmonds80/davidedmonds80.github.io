---
layout: post
title: "Choosing a Linux Distro"
categories: Beginners
---
## So Many choices, so few computers

As I mentioned there are literally thousands of Linux distributions floating around the internet, so
how is someone new to the world of Linux supposed to know which one is right for them? It can seem
overwhelming at first glance, but lets take a look at a few things, like what makes up a "distro"
(That's the cool way to say distribution), what different distros offer, and what really matters
when choosing a distro to install.  

## What is a distro, exactly?

Let's start with the basics, what, exactly, is a Linux distribution?  

[Wikipedia](https://en.wikipedia.org/wiki/Linux_distribution) has this to say:
> A Linux distribution (often abbreviated as distro) is an operating system made from a software collection that is based upon the Linux kernel and, often, a package management system. Linux users usually obtain their operating system by downloading one of the Linux distributions, which are available for a wide variety of systems ranging from embedded devices (for example, OpenWrt) and personal computers (for example, Linux Mint) to powerful supercomputers (for example, Rocks Cluster Distribution).
<br>A typical Linux distribution comprises a Linux kernel, GNU tools and libraries, additional software, documentation, a window system (the most common being the X Window System), a window manager, and a desktop environment. 

So a Linux distro is really just a collection of software, libraries, combined with a version(s) of
the Linux kernel.  All packaged together to make a working operating system.  

The major differences between distros really boil down to the package manager, the default Desktop
Environment (we'll get to what that is in a bit), and what software comes included.  

### Package Managers

The package manager is just the tool used to install software that doesn't come bundled with the
distribution.  There is great debate about which package manager is the "best", and like all things
opinion, there is no one right answer. It really comes down to what
features/options/widgets/gadgets/geegaws are included, and what matters to the user.  All packages
managers do the same thing: they find software in a repository and install it on the computer, they
also update the software when new versions come out.  

Some have a GUI (Graphical User Interface) so you don't have to remember the exact commands to type
into a terminal, which is nice for those that like the pointy-clicky method for interacting with
their computers. Most modern Linux distros include a package manager with a GUI, but not all. 

*A word of advice to new users: Don't let a GUI package manager option determine your decision, if
you're going to use Linux, you might as well get over being afraid of the terminal, you **will**
need it at some point* 

### Desktop Environments

This is the thing that makes a computer look a certain way, it's how the desktop background is
applied, what the icons and colors are, and most include file managers, text editors, those nifty
bars that show you what applications are open and what time it is, and all the other stuff that
makes up the majority of user interactions with a computer.  At some point I'll expound ad nauseam
about Desktop Environments. Not here though, I will provide a quick list and description of each of
them though:

- [Gnome](https://www.gnome.org/) Definitely different than Windows or OSX, lots of stuff included,
  not lightweight at all
- [XFCE](https://xfce.org/) Pretty lightweight, very customizable, very solid set of software
  included
- [Cinnamon](https://en.wikipedia.org/wiki/Cinnamon_(desktop_environment)) Very similar to Windows,
  very solid, based on an older version of Gnome, but still updated and maintained regularly
- [MATE](https://mate-desktop.org/) also based on an older version of Gnome, again still very
  popular and well maintained.  
- [KDE](https://kde.org/) Another very popular DE with a good looking interface, and lots of very
  nice themes, animations, and looks.  

There are several more, which I'll cover in another post, but these are 5 of the more popular
options.  

Something important to remember: You can install pretty much any Desktop Environment on any distro,
so even if a distro ships with a DE you don't like, you can change it to one that you do like,
pretty easily.  


## My Recommendations

This post is likely to become pretty big over time, and I absolutely detest being forced to read
7,000 words to find the information I want.  So I'm going to put my generic recommendations right
here, kinda near the top. 

### [Ubuntu](https://ubuntu.com/)

Ubuntu is pretty universally recommended for new Linux users, with good reason.  The company that
manages it (Canonical) is stable and has been around for a long time.  It's not going anywhere, it's
incredibly popular, and I don't know that I've come across software for Linux that won't run on it.
It uses the Gnome desktop environment by default, which is very good looking, yet doesn't attempt to
emulate either the Windows or the OSX look and feel.  

Ubuntu is a `stable` release which means updates are packaged and made available in intervals, but
they are pretty well tested by the time they're released.  So the software will be a little slow,
but things shouldn't break when they get updates. 

If you're new, and just want to see what this "Linux thing is all about", use Ubuntu.  

### [Fedora](https://getfedora.org/)

Fedora is another very solid choice for new users, especially people that are interested in working
in IT, or in supporting Linux in an enterprise environment.  Fedora is the bleeding edge of what
will become Red Hat Enterprise Linux (RHEL), which is very widely used by large companies,
especially in the U.S. (Ubuntu/Canonical seems to have more of the market share in other countries,
though RHEL is still widely used)

Fedora uses the DNF package manger which is very solid, and pretty much all Linux software is available in the RPM format used by the DNF package manager. 

Fedora is also a `stable` release, but packages seem to be released faster than Ubuntu.  

If your new and think you want to work on Linux for a living, give Fedora a try, or if you're new
and just want something simple that works, it's a good option in that scenario as well.


### [EndeavourOS](https://endeavouros.com/)

EndeavourOS is a very different beastie than my other two generic recommendations. It's a new
distro (at the time of this writing it's been around for just over a year) but it is based on a
distro that's been around for a long time, so even if the EndeavourOS team called it quits (unlikely
I believe) an installed instance of EdeavourOS could be used pretty easily.  EndeavourOS is based on
Arch, a `rolling` release distro, which means packages are available essentially as soon as the
developers make them available to the public.  Arch is known for being difficult to install (I've
never tried it, but there are tutorials and guides to make it easier), EndeavourOS however has a
"click next" type installer which makes it very simple to install, and it works quite well in my
experience.  

If you want to play, and get a chance to really break things, or if you're running very new hardware
this really might be the choice for you. 

### Do Not Install Kali
> I'm new to Linux and I want to install Kali, how do I do it? 

This is a question I've seen countless times.  The answer is that you don't.  Kali is not a Linux
distro meant to be used daily, it's not meant for new users, it's just not.  

According to the team that maintains Kali:
> If you are unfamiliar with Linux generally, if you do not have at least a basic level of competence in administering a system, if you are looking for a Linux distribution to use as a learning tool to get to know your way around Linux, or if you want a distro that you can use as a general purpose desktop installation, Kali Linux is probably not what you are looking for.

Yes.  I know.  It looks cool on Mr. Robot.  You can make any version of Linux look like that.  Yes
it's got `l33t h@x0r` tools.  You can install those on just about any distro.  (You shouldn't unless
you understand what they're for and how they work though.)

Kali is a tool which has a very specific use case, if you meet that use case, I'm willing to bet
you're not reading this website looking for basic Linux information. 

If you want to use Kali, you should have enough knowledge to figure out how to install it with out
asking for help on Reddit.  

*I know it comes up in reference to "security and Linux" a lot.  It's not that kind of security.
It's a tool to see how secure a network is.  If you're looking to hide your activity on the
internet, you want [QubesOS](https://www.qubes-os.org/)*


## Distro Options

If you want some more information, or want to know more about different distros, I'm going to try to
keep this section updated, with the distros I come across that I see frequently.  This is not a
comprehensive list by any means, just some info on the distros I see referenced frequently with some
information about them.  

### Stable vs Rolling

There are two major types of release/update cycles:
- Stable:  Stable doesn't mean "won't break" it just means releases for the distro (not
  applications) are packaged together and sent out in one big chunk, so you get things like: `Ubuntu
  20.04 Focal Fossa` which will have all of the core things that make up the Distro in one single
  update package, where the system is upgraded from the old version to the new version.  These
  updates are generally tested together and in theory everything should play nicely. Like all things
  computery, that may not always hold true.  The applications not considered part of the core distro
  will still be updated when the app developers make their updates available, so updates will still
  happen outside of the major release for the distro.
- Rolling:  Rolling release cycles are just that, constant (by comparison to stable) updates, when a
  part of the kernel is updated, the package is made available and users can update just that
  little piece.  This does mean that there is a potential for things to not work quite right with a
  specific system configuration, but these things are generally quickly identified and documented.
  Personally I've never had a problem with a rolling release, but I'm just one person. 


### How My List is formatted

Many distros are based on a different distro, or upstream distro, which can also be installed, so as
I go through this list I'll use different level headings to show if a distro is forked from another
major distro or not.  It looks like this:

### Top Level Distro

#### Fork of the top level Distro

##### Fork of the Fork


Each Heading will be a Link to the distro home page which will have more information than I'm going
to include, and more up to date information.  While I could copy and paste that information here,
that seems silly, and frankly I don't want to.  What I will do is make it easy for you to go find
information, and make your own decisions.  

### [Debian](https://www.debian.org/intro/about)
Debian is one of the longer running distros, and is what Ubuntu is forked from.  Very solid, though
it's not as user friendly as Ubuntu. 

All of the Debian forks listed below are stable releases using the `apt` package manager, and all
have access to the same repositories. 

#### [Ubuntu](https://ubuntu.com)
Probably one of the most widely used distros ever (for desktop users), run by Canonical it's a very
very popular distro.  It's so widely used that most of the time when I find instructions for how to
do something in Linux the instructions default to Ubuntu.  Most software is packaged for Ubuntu,
    which makes using it day to day quite simple.  The default desktop environment is Gnome though
    there are specific images for for other DEs

##### [Mint](https://linuxmint.com/)
Mint came about as an Ubuntu fork, and has grown to have it's own dedicated following, the Mint team
is responsible for the Cinnamon desktop environment.  Mint is a truly great distribution for helping
someone transition to Linux from windows, as many of the Windows behaviours (bottom left "start
menu", right click on the desktop, etc.) are replicated in Cinnamon.  It also uses the same package
manager, and repositories for Ubuntu, which means there's a huge quantity of software easily
available, as well as many guides for how to do things, or solve problems on the internet. 

##### [Xubuntu](https://xubuntu.org/)
This is Ubuntu with the XFCE Desktop Environment

##### [Lubutnu](https://lubuntu.net/)
This is Ubuntu with the LXDE/LXQT Desktop Environment, which makes the distro very lightweight. 

##### [Kubuntu](https://www.kubuntu.org/)
This is Ubuntu with the KDE Desktop Environment

### The Red Hat Family
I'm grouping 3 distros together here, although they're not exactly forked from each other, they are
all related. 

#### [Red Hat Enterprise Linux (RHEL)](https://www.redhat.com/en)
Red Hat is one of the giants in the Linux world.  In the U.S. I would guess there are more RHEL
servers installed than any other, by a wide margin. 

RHEL is available and can be installed as a workstation, but it's not Free, it's $99 for a license at the time of this writing, you can buy it [here](https://www.redhat.com/en/store/linux-platforms) if that something that interests you.  Personally I wouldn't. RHEL is really meant to be a server operating system

#### [Fedora](https://getfedora.org/en/)
Fedora is really solid stable release distro (It's what I'm currently using) Gnome is the default
desktop environment that ships with it. [Fedora Spins](https://spins.fedoraproject.org/) offer several other options for desktop environments

Fedora is the upstream source for a lot of the packages that go into RHEL, but it is technically a
different project and RHEL isn't really forked from it.  If it were a Facebook status relationship
it would be "It's Complicated." Fedora is really the best option for those that are interested in
understanding and working with RHEL, and want to try it as a workstation.  

#### [CentOS](https://www.centos.org/)
CentOS is essentially the free version of RHEL. It's primary use case is as an appliance or server,
it's not really geared towards being a workstation. The source code is provided by Red Hat, and my
understanding is that CentOS is used as a test bed for some RHEL features.  If you want to host your
own server of some sort, this is an excellent choice, since many of the things you might want to do
have been done by large companies, the odds that you'll be able to find an answer for any problems
you encounter are very high. 

### [Open Suse](https://www.opensuse.org/)
Suse Linux is one of the older Linux distributions around, it's been used in the corporate world for
a long time, and there are still services that use it almost exclusively.  OpenSuse is the free
version of Suse.  (Big shocker there, I know) Suse uses a different package manager than the
Fedora/Red Hat/CentOS ecosystem, but that package manager does use RPM files, which means just about
anything that will run on the RHEL type distros will work with Suse.  It's a bit of a niche distro,
but it does have something very few (if any) other do, both a rolling and a stable release version.
Which makes it very useful for people that are developing for or supporting Suse servers.  It's
fairly newbie friendly, and has strong community support, if not a huge community of users. 

### I use [Arch](https://www.archlinux.org/) btw
Arch Linux and "I use Arch btw" have become a bit of a meme on the internet.  There was a point in
time when Arch users were known to tell people at every opportunity that they used Arch, it was
viewed by some as a badge of honor.  That is because Arch is not something that is easy to install,
or manage. If installing Linux is riding a bicycle installing Arch is like getting a box of parts
that have to be assembled. In other words you have to read carefully and follow directions, and understand what your machine is doing to successfully install Arch.  If you want to learn about how your operating system works, Arch is a great choice, it's a rolling release distro which ensures the very latest packages are available, and it provides really granular control of your machine.  

Arch has brought one of the single best resources to the Linux community in the [ArchWiki](https://wiki.archlinux.org/index.php/Main_page) This is a truly fantastic resource for anyone using Linux.  Go ahead and bookmark it.  While the instructions are all geared towards Arch users, the information typically applies across the board, even if the specific instructions don't. 

#### [EndeavourOS](https://endeavouros.com/)
Arch with training wheels, well mostly just Arch with a GUI "click next" installer, you still get
all of the benefits (and challenges) of a rolling release with a simple install method. The
installer provided by the EOS team allows for granular control of the packages, or a simple
"recommended" install option.  The installer works well, and will have you up and running pretty
quickly.  

#### [Manjaro](https://manjaro.org/)
If EndeavourOS is arch with training wheels, Manjaro is a tricycle.  While Manjaro is still
technically a rolling release the team behind Manajaro often holds packages back for a week or so to
hopefully catch any major failures before they're released to the Manjaro community.  As a result
the distro is fairly stable.  

### [Gentoo](https://www.gentoo.org/)
To stretch an analogy to the point of breaking, if Arch is a bicycle you have to assemble, Gentoo is
a pile of metal that has to be formed in to parts to be assembled into a bicycle.  It is designed to
be **exactly** what you need and nothing more, nothing less.  Being this granular requires some
additional work on your part.  Again, once you get it working, you will know in great detail how
your machine works.  

### [Linux from Scratch (LFS)](http://www.linuxfromscratch.org/)
LFS is not a pile of metal to build a bicycle, LFS is a list of locations of ore, instructions on
how to mine the ore, create the parts, and assemble the bicycle.  LFS is really more of a training
tool than an actual distro meant to be used.  LFS is a fantastic way to learn about how Linux works
at a very low level. 
