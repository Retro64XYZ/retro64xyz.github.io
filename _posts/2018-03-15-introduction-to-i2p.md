---
layout: post
title: "Introduction To I2P"
date: 2018-03-13T15:52:43-07:00
author: RetroMe
summary: >
  Introduction To I2P is a two-hour course designed to provide an
  introduction to I2P, uses for anonymous browsing tools, and why privacy
  matters. It will focus on the practical uses for I2P, how others may
  attempt to unmask you, and why tools like I2P are applicable to the
  public.
categories: computers
thumbnail: fa-desktop
tags:
 - tor
 - freenet
 - i2p
 - phoenix linux users group
---

## Performance Objective

At the conclusion of the course the student will be able to:

1. Identify what I2P is.

2. Identify one reason why we should block javascript.

3. Explain how I2P works.

4. Explain how I2P is different than Tor.

## Introduction

[The I2P Project.](https://geti2p.net/en/)

I recommend watching the [I2P Con 2015 Playlist.][i2pcon] There were plans for
a 2016 I2P Con but it does not appear to have come to fruition. There are no
other I2P-centric conventions as far as I know.

I did speak to users on the IRC chat room for #i2p-dev and was provided some
excellent information from the developers. This talk was reviwed by the I2P
staff and a request to confirm facts was made. No changes in content were
solicited or made due to reputation or any other concerns.

```
│09:53:57       i2pr | [Irc2P/psi] some important notes to add, i2p is a network layer, it provides an anonymous layer 3    │
│                    | (on the osi stack)                                                                                   │
│09:54:10       i2pr | [Irc2P/psi] no one else does that as far as i have seen                                              │
│09:54:48       i2pr | [Irc2P/psi] i2p can do anonymous anycast too, like 1 destination in multiple servers                 │
│09:54:58 Retro64XYZ | psi: That network layer is what simplifys connection of so many tools into the i2p network; am I     │
│                    | correct in saying that?                                                                              │
│09:55:01       i2pr | [Irc2P/psi] which again, no one else can do as far as i have seen :^)                                │
│09:55:15       i2pr | [Irc2P/psi] not quite                                                                                │
│09:55:26       i2pr | [Irc2P/psi] it makes the network harder to optimize                                                  │
│09:55:39       i2pr | [Irc2P/psi] but it gives a LOT of flexibility to app developers                                      │
│09:56:12       i2pr | [Irc2P/psi] idk if it makes it simpler, it's just different                                          │
│09:58:56       i2pr | [Irc2P/psi] also due to lack of regular funding our product is a bit lack luster compared to tor     │
│09:59:13       i2pr | [Irc2P/psi] we don't have money to pay devs to maintain a browser                                    │
│09:59:27       i2pr | [Irc2P/psi] it's mostly randos in their spare time                                                   │
│09:59:41       i2pr | [Irc2P/psi] (more randos desired)                                                                    │
│09:59:49       i2pr | [Irc2P/psi] we need more of everything (tm)
```

## How does I2P Work

I2P functions with several essential concepts. The first is the strict
separation between software (router) and endpoint (destination). The act of
running I2P is not a secret usually. The activity being participated in and the
destination of that activity is the hidden information that is being protected
by I2P. The second important concept is the tunnel. The tunnel is the
connection being made from one computer to another within the I2P network. All
tunneling is performed in a unidirectional manner. You have outbound tunnels
and inbound tunnels. The first computer, client or server, is usually referred
to as the gateway.

The concept of the network database is also important to I2P. The netDb is used
to transfer metadata about the network. The information being shared is the
routerInfo and the leaseSets. The routerInfo will give routers the data
necessary for reaching a particular router. This data includes transport
addresses, public keys, and additional but unmentioned data about the network.
The leaseSet will provide the information necessary for contacting a particular
destination. The leases(plural!) within the leaseSet will specify tunnel
gateways and works as a map for reaching a destination.

>* Inbound gateway for a tunnel that allows reaching a specific destination.
>* Time when a tunnel expires.
>* Pair of public keys to be able to encrypt messages (to send through the tunnel and reach the destination).

A router will send routerInfo to the netDb directly while the leaseSets are
sent through outbound tunnels. This is done because a leaseSet must be sent
anonymously or it will correlate the router with the leaseSet.

Further information on I2P [function][i2pfunction] is found within the
excellent documentation provided by the I2P project.

## How To Install

1. [Review the code][githubi2p] on the GitHub platform! You don't have an
   excuse. You need to stop and look at the tool, how it is made, and who is
   making it.

2. [Acquire hosting][scaleways] on an external platform. You have a lot of
   options.  I prefer scaleway as a platform because they are off shore. Pick
   your favorite country, pick a provider, and get a VPS. A $3.00 'starter
   cloud' is a sufficient package for hosting a I2P install.

3. [Get the installer][installi2p] and get it onto your VPS. The process
   will look like the following.

	```
	$ wget 'https://download.i2p2.de/releases/0.9.33/i2pinstall_0.9.33.jar' -O new_installer_offline.jar;
	$ java -jar new_installer_offline.jar;
	```

4. We will want to run the software locally. This can be done with a tunnel.
   Run this command on your local machine.

	```
	$ ssh -L 7657:127.0.0.1:7657 YOURSERVERIPHERE
	```

5. We will also want to gain access to I2P sites locally. These are also known
   as eepsites. This requires access to port 4444.
	```
	$ ssh -L 4444:127.0.0.1:4444 YOURSERVERIPHERE
	```

5. We then open a browser on our local machine and surf over to
   http://localhost:7657

6. You will then want to surf over to Configuration->Network and get your port.
   You can then open this UDP port in your firewall.

## How To Setup

Setting up I2P can be remarkably simple. You will install the application and
then connect to it as you would with some thing like Freenet. Configuration is
also fairly simple to start with. Properly opening the port for your connection
in your firewall is one of the more difficult tasks. Your main goal is to make
the 'Network:' icon to the left of the screen state 'OK' as well as to gain
green stars next to your local tunnels. I found I2P to be very verbose in
recommendations as well as in identifying issues or problems. I believe I2P to
have excellent documentation and very good levels of hand holding for new
users.

## Who Made I2P

I2P is made up of many anonymous [users][i2pteam] who contribute time and
effort to better the tool. The vast majority of these users appear to be taking
their privacy very serious and many of them work under pseudonym. The original
creator was known as 'jrandom' which is a generic term used in many books to
denote the user. Development began in 2003 and started around the same time
that Tor development began. At some point, jrandom vanished, see [jrandom's AWOL Announcement](https://geti2p.net/en/misc/jrandom-awol)
and the entire project very nearly came to a crashing halt. Over time, it was salvaged and the
I2P project was able to continue development.


## What does I2P do

The initial purpose of the Invisible Internet Project was to provide a secure
and anonymous method to communicate with users over IRC. I2P evolved from the
Invisible Internet Project and is now intended to provide anonymous
peer-to-peer communication for Usenet, email, IRC, file sharing, web hosting
(http) and telnet. The real purpose of I2P is to provide an anonymous network
layer so that other software can interact through the I2P protocol.

## Garlic Versus Onion

[I2P comparison with TOR.][i2pcompare]{:target="_blank"}

I2P has used the term 'garlic' to represent one of three things. Layered
encryption, bundling messages together, or ElGamal/AES encryption. In order to
understand garlic routing, we must first understand that onion routing consists
of building tunnels, through a series of peers, and then using the tunnel. Each
hop decrypts a piece of the message before passing the rest on, therefore it
works a bit like 'peeling an onion' as the different layers are stripped until
the data ends up at a destination.

In the sense that messages are encrypted for each hop on the journey, onion
routing and garlic routing are the same in concept. The first difference is
that multiple messages are bundled together in I2P. Any number of messages can
be contained in an I2P clove. I2P is unidirectional as mentioned earlier,
meaning the tunnels can only travel in a single direction.

I2P uses garlic routing, bundling, and encryption in three places -

>1. For building and routing through tunnels (layered encryption)
>2. For determining the success or failure of end to end message delivery (bundling)
>3. For publishing some network database entries (dampening the probability of a successful traffic analysis attack) (ElGamal/AES)

You can read more in the excellent [garlic documentation.][garlic] 

## Attack Vectors

[I2P Attacks(PDF).][i2pattacks]{:target="_blank"}

[I2P and Tails were flawed][i2pflawtails]

[Exodus Intelligence][exodusintel] was able to locate flaws in I2P and use
those flaws to unmask users of [Tails][tailslinux].

Some of the [threats][i2pthreats] that I2P are vulnerable to include -

* Brute Force Attacks
* Timing Attacks
* Intersection Attacks
* Denial Of Service Attacks
* Tagging Attacks
* Partitioning Attacks
* Predecessor Attacks
* Harvesting Attacks
* Traffic Identification
* Analysis
* Sybil Attacks
* Buddy Exhausting Attacks
* Cryptography Attacks
* Floodfill Attacks
* Attacks on the Network Database
* Attacks on centralized resources
* Development Attacks
* Implementation Attacks

Of note is that I2P has identified all of these attacks and provides opinions
as well as factual data on how likely you are to experience them, high level
discussion on how they work, and an opinion on the effectiveness of the attack.
I rate them highly for their transparency in monitoring for attacks and
vulnerabilities.

### Operating Systems Suck

All operating systems are should be considered compromised and no amount of
anonymous software will protect you from the vulnerabilities that have been
baked into the hardware and the software. I stand by my statement that if
'they' want you 'they' have you.

#### Linux should be considered compromised.

Due to my training and experience, I do not believe that it is possible for
Linus Torvalds to have refused the American Government if they did seriously
proposition him for a back door into the kernel. I also am a strong believer
that no one person has complete understanding of the kernel and all intricacies
involved. Therefore it is impossible at this point to claim that there are
absolutely no flaws being exploited in the wild.

If Linus Torvalds was 'joking' when he decided to admit to being propositioned
for a backdoor, I feel it was in bad taste and not conducive to building
confidence in the Linux product.

<div class="video-container">
<iframe width="560" height="315" src="https://www.youtube.com/embed/7gRsgkdfYJ8"
	frameborder="0" allowfullscreen></iframe>{: itemprop="associatedMedia" itemscope itemtype="http://schema.org/VideoObject"}
</div>

#### Windows should be considered compromised.

Microsoft has a long and storied history of extremely good relationships with
the NSA and are suspected of providing them access to systems.

[Windows NSA Back Door.][nsabackdoorwindows]

[_NSAKEY for Windows.][nsakeywindows]

[Germany Hates TPM.][germanytpm]

### Your hardware sucks too by the way

Suspicion over the level of assistance that hardware makers provide different
governments is high. We know that China installs spying tools into their
products on a relatively regular basis. We can also expect others to do the
same for the US. 

[Chip Proof Of Concept - Analog Attacks.][analogchips]

[Intel Management Engine Flaws.][intelmef]

## Privacy Threats

There are seven companies that provide the backbone to the internet.
Intergovernmental agreements would simplify the act of being able to spy on
different products. In addition, almost 40% of all web hosting is performed
within the United States with Germany being a close second in market share at
18%. A negligible 7% of hosting is done in China. I urge you to learn about
[PRISM](https://prism-break.org/en/) and how the US Government has stated under
oath that all parties involved were, contrary to their claims, complicit in
spying.

Please also view info on [PRISM](https://en.wikipedia.org/wiki/PRISM_%28surveillance_program%29#The_slides) on Wikipedia.

[Just sniff the wire.][sniffwire]

[The internet backbone.][backbone]

## Content

I2P uses .i2p sites or 'eepsites' in a manner similar to how you may find a
.onion site on the Tor network. This TLD denotes that the website is available
only from the I2P network. These are also known as hidden sites. The I2P
project chose the [Eclipse Jetty webserver][jettywiki] as their default method
of communication. It supports PHP, MYSQL, and can serve Javascript. You can
learn more about Jetty at the [project home for Jetty][jettyhome]. You should
minimize your vulnerability footprint by using a browser that does not include
support for javascript or flash. You should not download PDF files or any other
external file format.

## Answers

1. I2P is a peer-to-peer platform that appears to regularly tout a strong
   connection to cyptocurrency and dark markets.

2. An example of a [Javcascript exploit is found here][cveexploit] with more
   [information][cvenist] provided by the NIST.

3. I2P functions by allowing users to anonymously share files, browse, chat,
   and more through the use of the I2P protocol.

4. Tor uses onion routing while I2P uses garlic routing. Tor is more focused on
   accessing servers outside the Tor network while I2P attempts to minimize
   connections to the clear net.

## Conclusion

I2P is designed as a primarily internal network with the intention to make
minimal bridging to the clear net possible. I2P is an anonymous network layer
and is designed to facilitate the use of supporting software. This means that
you must use I2P in conjunction with other tools in order to attain anonymous
communication. You will rely on a web browser, tunnels, IRC Client, or any
number of file sharing applications in order to make use of the I2P protocol.
This also means that your vulnerability foot print will be different depending
on what tools you employ to support your I2P use. Every application you use
increases the possibility that you are vulnerable.

I believe that the I2P project has many positive aspects and while no project
is perfect, their documentation is second to none. I feel that their decision
to allow javascript, php, and other tools increases their ability to garner
favor with the web 2.0 crowd but detracts from the security of the tool due to
the increased vulnerability foot print inherent in those technologies.

I2P is extremely popular with the alternative currency crowd and it is easy to
see that I2P provides an excellent set of tools for interacting with that
technology. While there are vulnerabilities within the technology and a host of
peoples who are toiling away in an attempt to disrupt or harm the network, they
have worked diligently to provide an acceptable product that I feel is worth
using for any one who does not need to rely on the tool for their life.

## Final Recommendations

1. Register a PGP key.

2. Use Linux.

3. Contribute to a privacy enhancing project. I recommend Freenet. Pick one.

4. Develop relationships and build your own 'Darknet'. Network in the real world.

5. Contribute to Open Source Projects. 

[githubi2p]: https://github.com/i2p/i2p.i2p 'Github I2P project'
[scaleways]: https://www.scaleway.com/ 'Good web hosting'
[installi2p]: https://geti2p.net/en/download 'I2P installer'
[i2pflawtails]: http://archive.is/uXAVb 'I2P tails zero day' 
[i2pattacks]: /../assets/pdf/i2p-practical-vulns.pdf 'I2P Attacks'
[i2pcompare]: /../assets/pdf/onion_routing_chalmers.pdf 'Onion Routing with TOR, Garlic with I2P'
[jettywiki]: https://en.wikipedia.org/wiki/Jetty_(web_server) 'Jetty Wikipedia'
[jettyhome]: https://www.eclipse.org/jetty/ 'Jetty Project Home'
[exodusintel]: https://www.exodusintel.com/ 'Exodus Intelligence Threats'
[tailslinux]: https://tails.boum.org/ 'The Amnesic Live System'
[i2pthreats]: http://archive.is/WtNSL 'The I2P threat model'
[i2pfunction]: http://archive.is/hBtNQ 'How I2P works'
[cveexploit]: https://cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1690 'Javascript exploit CVE-2013-1690'
[cvenist]: http://archive.is/bD8PQ 'The NIST infor for the CVE 2013-1690'
[i2pcon]: https://www.youtube.com/watch?v=NTv9kxD4Ipk&list=PLDlBIvHwDyf8XpZndYB9bBjXZAngacu0G 'I2P convention'
[i2pteam]: https://geti2p.net/en/about/team 'The I2P team'
[nsabackdoorwindows]: http://archive.is/Ep39w 'NSA Backdoor in Windows'
[nsakeywindows]: http://archive.is/xXxOm 'The NSA Keys'
[germanytpm]: http://archive.is/MDKKA 'Germany does not like trusted computing'
[analogchips]: http://archive.is/oQmNC 'Analog attacks in chips'
[intelmef]: http://archive.is/fs2Gm 'Intel Management Engine Issues'
[sniffwire]: http://archive.is/OOUNm 'Sniffing the wire'
[backbone]: http://archive.is/Gnyme 'The internet backbone'
[garlic]: http://archive.is/k7PVe 'How garlic works'
