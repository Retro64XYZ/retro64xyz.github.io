---
layout: post
title: "Introduction To TAILS"
date: 2018-05-12T04:52:43-07:00
author: RetroMe
summary: >
  Introduction To TAILS is a two-hour course designed to provide an overview of
  how TAILS OS works, what it is good for, and when you may wish to use it.
  This will touch on some of the tools made available in the OS, how to try it
  out, and some of the events surrounding the system. This focuses mainly on
  the TAILS project proper.
categories: computers
thumbnail: fa-desktop
tags:
 - tor
 - freenet
 - i2p
 - operating systems
 - tails
 - phoenix linux users group
---

## Performance Objective

At the conclusion of the course the student will be able to:

1. Identify what TAILS OS is.

2. Identify one reason you may wish to use TAILS OS.

3. Explain how TAILS OS works.

4. Describe one method to install TAILS OS.

5. Describe a security event in relation to TAILS OS.

## Introduction

[The Amnesic Incognito Live System.](https://tails.boum.org/) is a live
operating system that you can boot from USB or DVD. The intentions of this
project are to assist users in preserving their privacy and anonymity when you
wish to circumvent censorship, leave no trace, or use cryptographic tools. The
tails project 

## How does TAILS Work

TAILS is a live operating system. This means it is a complete bootable computer
installation that can run off of CD-ROM, USB, or similar means. There are many
operating systems that allow you to boot from USB and run the OS without
causing changes to the host computer. However, the real claim to fame that
TAILS has is the deep integration with TOR and the bundled availablity of the
TOR Browser. TAILS previously offered I2P as an alternative to TOR but removed
this capability due to difficulty with finding maintainers for the I2P
component of the project and the rapid pace in which vulnerabilities are found.

You can easily build a live operating system from any number of linux
distributions and could theoretically install TOR as a component of that OS. If
you feel confident in setting up an operating system and installing TOR, I
believe it would make some sense to roll your own. If you are not confident
then you should look at tools like TAILS to provide a ready made solution that
provides some reasonable levels of privacy.

## How To Install

You can choose to install TAILS using two methods. One method would be to
install the OS on a thumb drive or CD. This method is simple and is the
expected method of deployment.

### Method One

1. [Get Etcher](https://etcher.io/)

2. [Download TAILS](https://tails.boum.org/install/download/index.en.html)

3. Burn the OS to a USB drive using Etcher

### Method Two

1. [Download TAILS](https://tails.boum.org/install/download/index.en.html)

2. Create a virtual machine with no hard drive

3. Boot from the ISO into a virtual machine

## How To Setup

TAILS is relatively simple to use and requires little or no setup. TOR is set
to activate on boot and you can begin surfing the web shortly after you gain
access to the OS and connect to a wireless network or hard wired network. The
purpose of using something like TAILS is to give you a basic and relatively
safe method of working with TOR with a reasonable amount of security.

## Why use TAILS

## How to secure your thumb drive

Don't loose it. Don't allow others to grab it.

## Is TAILS fool proof

No. TAILS is a simplified method of deploying TOR on a computer while greatly
reducing your local foot print. Is it fool proof? Absolutely not. Your online
activity is relatively obvious and your use of TAILS does raise red flags. You
should not expect TAILS to provide any aditional protection over a local copy
of TOR unless you are ready to change your method of surfing the internet
drastically.

### Things to do to enhance security with TAILS

1. Do not mix identities with TAILS

2. Do not use TAILS or TOR from your home network

3. Do not use compromised hardware

4. Do not expect privacy from nation state level attacks

5. No software is perfect

6. Your VPN may be connected to you by your payment method

## Answers

1. TAILS OS is an Amnesic Operating System used to provide privacy anonymity.

2. TAILS provides an easy to use copy of Tor and includes many tools that may
   be useful to someone wishing to surf the internet using Tor.

3. TAILS OS is an operating system that is programmed with a number of tools
   that allow users to connect to the internet over Tor without saving any
   information to a hard drive for later retrieval. 

4. TAILS OS is normally installed on a USB thumb drive as a 'live' operating
   system. 

5. TAILS OS has and does sometimes suffer from 0-Day exploits and this has
   caused much debate on when and how these issues should be reported.

## Conclusion

TAILS is a great tool for individuals who do not have the technical skills
necessary or the time to setup and deploy TOR securely. You can use TAILS in
combination with good operational security and smart behavior to provide
maximum levels of anonymity online.

## Final Recommendations

1. Use Linux.

2. Use Freenet.

3. Contribute to a privacy enhancing project. I recommend Freenet. Pick one.

4. Develop relationships and build your own 'Darknet'. Network in the real world.

5. Contribute to Open Source Projects. 

[scaleways]: https://www.scaleway.com/ 'Web Hosting'
[gittor]: https://gitweb.torproject.org/tor.git 'The Tor Project GIT' 
[keelog]: http://www.keelog.com/ 'Hardware Key Loggers'
[hidesock]: http://archive.is/qsFob 'Hidden Socks'
[vulnsforsale]: http://archive.is/H5aux 'Not for Sale - Vulnerabilities in Tails'
[tailswarn]: https://tails.boum.org/doc/about/warning/index.en.html 'Tails warnings'
