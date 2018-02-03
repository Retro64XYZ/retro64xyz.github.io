---
layout: post
title: "Introduction To Freenet"
date: 2017-06-11T15:52:43-07:00
author: RetroMe
summary: >
  Introduction To Freenet is a two-hour course designed to provide an introduction
  to Freenet, uses for anonymous browsing tools, and why privacy matters. It will
  focus on the practical uses for Freenet, how others may attempt to unmask you,
  and why tools like Freenet are applicable to the public.
categories: computers
thumbnail: fa-desktop
tags:
 - PGP
 - GPG
 - freenet
 - phoenix linux users group
---

## Performance Objective

At the conclusion of the course the student will be able to:

1. Identify what Freenet is.

2. Identify one reason that privacy matters.

3. Explain how Freenet works.

4. Explain how Freenet is different than Tor.

## Social Security Tip

The [Social Security Administration][ssecurity] is urging people to register in
order to better protect their identities online. Even if you have not yet reach
the age that Social Security is applicable, you may wish to register an account
so that you can prevent others from doing so in your name. This isn't a
guarantee but it can provide some level of defense against scammers and
thieves.

[Brian Krebs][sskrebs] has a break down of an attack and explanation of what
happened on his site.

## Introduction

Censorship-resistant communication. Freenet claims to be a peer-to-peer platform
to enable and promote communication and publishing without the fear of interference.
Freenet provides the ability to browse websites, post to forums, and publish files
while enjoying strong privacy protections. It is a platform for publishing that does not
and cannot silence the user.

## How does Freenet Work

[Kent State University][peernetreview] has a very good explanation of Gnutella,
Bittorrent, and Freenet protocols.

## How To Install

1. [Review the code][githubfreenet] on the GitHub platform! You don't have an
   excuse. You need to stop and look at the tool.

2. [Acquire hosting][scaleways] on an external platform. You have a lot of options.
   I prefer scaleway as a platform because they are off shore. Pick your favorite
   country, pick a provider, and get a VPS. A $3.00 'starter cloud' is a sufficient
   package for hosting a Freenet install.

3. [Get the installer][installfreenet] and get it onto your VPS. The process will
   look like the following.

	```
	$ wget 'https://github.com/freenet/fred/releases/download/build01479/new_installer_offline_1479.jar' -O new_installer_offline.jar;
	$ java -jar new_installer_offline.jar;
	```

4. We will want to run the software locally. This can be done with a tunnel.

	```
	$ ssh -L 8888:127.0.0.1:8888 YOURSERVERIPHERE
	```

5. We then open a browser on our local machine and surf over to http://localhost:8888

## How To Setup

## Censorship

[Daily Stormer][dstormerverge]

## Attack Vectors

## Privacy Threats

The website [Darkode][darkode] was used by criminals to lower the barrier to
entry for cyber criminals. It was once used by people like Brian Krebs of
[Krebs on Security][krebsite] for gathering information in near real time.
Darkode relied heavily on Tor and paranoia for their survival but it was shut
down.

## Answers

1. Freenet is a peer-to-peer platform for censorship resistant communication.
   It uses decentralized data stores to distribute information and also has a
   suite of free software used for publishing available.

2. Privacy matters because it works as a limit on the power that others can
   exert on us. Personal data is valuable and can affect our reputations as
   well as be used to shape our behavior. Personal data can cause great harm.

3. Freenet functions by allowing users to anonymously share files, browse and
   publish freesites, and distribute information in a manner that provides
   protection against censorship. Freenet works as identical nodes that pool
   their storage resources in a censorship resistant manner.

4. Tor is reliant on many different pieces of software and provides access to
   the clearnet while also being more centralised. Freenet is more
   decentralized, provides in-house replacement tools for clearnet behaviors,
   and hosts content in a decentralized way in order to reduce DDOS attacks.

## Conclusion

Privacy, Anonymity, and Authorship Assurance are all important aspects and

## Final Recommendations

1. Register a PGP key. Use [Keybase][KeybaseURL] if you are uncomfortable
   managing it yourself.

[githubfreenet]: https://github.com/freenet/fred 'The Freenet Repo'
[scaleways]: https://www.scaleway.com/ 'A cloud computing platform'
[installfreenet]: https://github.com/freenet/fred/releases/download/build01479/new_installer_offline_1479.jar 'Installer'
[darkode]: http://archive.is/XAlfN 'Darkode used Tor'
[krebsite]: https://krebsonsecurity.com/ 'Brian Krebs Website'
[ssecurity]: https://secure.ssa.gov/RIL/SiView.do 'Social Security Admin'
[sskrebs]: http://archive.is/z13HZ 'Brian Krebs Social Security Warning'
[dstormerverge]: http://archive.is/wR2Vh 'Daily Stormer Blocked'
[peernetreview]: http://archive.is/T32C2 'Tutorial on Gnutella, Bittorrent, and Freenet'
