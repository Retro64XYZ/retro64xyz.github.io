---
layout: post
title: "Introduction To Tor"
date: 2018-03-13T15:52:43-07:00
author: RetroMe
summary: >
  Introduction To Tor is a two-hour course designed to provide an
  introduction to Tor, uses for anonymous browsing tools, and why privacy
  matters. It will focus on the practical uses for Tor, how others may
  attempt to unmask you, and why tools like Tor are applicable to the
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

1. Identify what Tor is.

2. Identify one reason you may wish to use Tor. 

3. Explain how Tor works.

4. Explain how Tor began.

## FOSTA - Fight Online Sex Trafficing Act

The [FOSTA bill][fostacongress] was passed by the House of Representatives.
This kills the Craigs List. Any website found to be promoting prostitution or
sex trafficing can now be held responsible for the content within.

## The CLOUD Act Rains On Our Parade

The [CLOUD bill][cloud] is currently in the budget and is being snuck into use
as we speak. This will improve law enforcement access to data found on servers
outside the United States and provide a loop hole to by pass all rights and
protections to privacy. We will now be able to work openly with foreign
intelligence services to spy on United States citizens. We may also accept
'evidence' provided by these agencies. This will allow law enforcement to open
cases and pursue prosecution based on data provided by foreign services legally
(like the Trump Dossier) regardless of merit or whether it appears truthfully.
In the video found below, mentioned is collusion between British and American
spy services in connection with investigating the victims of the Lockerbie
Bombing. This behavior would not be illegal under this new bill it would
appear.

## Protest Fatigue

Can we forever be outraged? How can we stay angry forever? We fought SOPA,
FOSTA, CLOUD, and an endless number of bills each running back to back with the
next in order to manage public attention. People and businesses run out of
money, attention, and outrage. It would also appear that we are loosing every
battle. Network neutrality is a loss. FOSTA will be a loss. We will loose on
the CLOUD bill. What do we do next?


## Introduction

[The Tor Project.](https://www.torproject.org/index.html.en)

## How does Tor Work

Tor works as an internet networking protcol with the intent of anonymizing any
information passed through it. It allegedly provides protection to journalists,
activists, business people, the military, and others. Tor encrypts traffic and
bundles it through a method known as onion routing before passing on this
bundle of information between nodes on the way to the destination. You can use
Tor to communicate internally to the network or you can use the power of an
exit node to access information found on the clearnet. Tor recommends the use
of the Tor Browser, a tool developed with a base in the Firefox web browser
that is recommended for ease of access and use.

[I do not trust Firefox][mozcve] and I do not trust the Tor Browser. I don't
trust any browser. Active exploits of the Tor Browser exist in the wild at this
very moment and large and complex tools like the Tor Browser will continue to
be vulnerable. Full stop.

## How To Install

1. [Review the code][gittor] on their GIT platform! You don't have an
   excuse. You need to stop and look at the tool, how it is made, and who is
   making it. Check their [Github][githubtor] as well.

2. [Acquire hosting][scaleways] on an external platform. You have a lot of
   options.  I prefer scaleway as a platform because they are off shore. Pick
   your favorite country, pick a provider, and get a VPS. A $3.00 'starter
   cloud' is a sufficient package for hosting a Tor install.

3. [Get the installer][installtor] and get it onto your VPS. The process
   will look like the following.

	```
	$ apt install tor 
	```

4. We will want to run the software locally. This can be done with a tunnel.
   Run this command on your local machine.

	```
	$ ssh -L 7657:127.0.0.1:7657 YOURSERVERIPHERE
	```

5. We will also want to gain access to Tor sites locally. These are also known
   as eepsites. This requires access to port 4444.
	```
	$ ssh -L 4444:127.0.0.1:4444 YOURSERVERIPHERE
	```

5. We then open a browser on our local machine and surf over to
   http://localhost:7657

6. You will then want to surf over to Configuration->Network and get your port.
   You can then open this UDP port in your firewall.

## Docker Install Alternatives

[Option One](https://blog.jessfraz.com/post/routing-traffic-through-tor-docker-container/)

[Option Two](https://hub.docker.com/r/dperson/torproxy/)

## RUNNING TOR MAKES YOU A TARGET

The use of Tor has been a deciding factor in [investigating you][tortarget]. 

## DO NOT RUN AN EXIT NODE FROM YOUR HOUSE

<div class="video-container">
<iframe width="560" height="315" src="https://www.youtube.com/embed/AXGkJ92l_lE"
	frameborder="0" allowfullscreen></iframe>{: itemprop="associatedMedia" itemscope itemtype="http://schema.org/VideoObject" }
</div>

When discussing Tor and the manner in which many individuals complain about
harassment due to their participation as an exit router, we need to look at the
laws concering [accomplice liability][accomplicelaw]. You should also read more
about [accomplice law][accomplicelaw2].

Tor is used to commit crimes. The open net is used to commit crimes. Cars,
planes, trains, and even banjos have been used by criminals or became
instruments in crimes. We don't try to ban them, spy on people for owning them,
or worry that our neighbors may be serial 'pumpernicklers'. In 1988 a murder
was commited in Britain in which a man was beaten to death with bread. But
privacy is a fearful thing and those who wish to retain their right to privacy
are considered strange, scary, or weird.

However, when law enforcement is investigating a crime and they trace the
criminal activity to your home, they will want to better understand why your
home is being used for criminal behavior. Providing an exit node and
advertising that your home is used to traffic child pornography is going to
grab law enforcement attention. Those privacy advocates who provide exit nodes
do so at the risk of their traffic being marked as hostile or as a carrier of
illegal traffic.

Do not run an exit node from your home and if you decide to run an exit node on
a server owned by a hosting company, make sure you pick a company that
understands what you are doing and how to handle law enforcement requests for
information.

## How To Setup

## Who Made Tor

Tor was originally developed as a method for the United States Government to
provide bi-directional communications over the internet where the source and
destination are hidden from view. The Department Of Defense, Naval
Intelligence, and Darpa deployed Tor in order to protect their assets and to
hide their activities. It was never intended as a tool for dissidents or as a
tool to protect users from government spying. It was created to facilitate
spying while using the noise produced by others to mask their behavior.

Using Tor makes you into the smoke screen that supports the mission at hand.
Tor is not shy about revealing [military applications][militaryapplicationstor]
for their tool on their site. Tor is first and foremost a military and US
Government orientated tool and provides benefits such as anonymous
communication to the public as a side effect of that mission.

## Tor Financials

You can learn about the [financial][torfinancials] status of the Tor Project
from their tax statements.

## What does Tor do

## Spying is old hat

<div class="video-container">
<iframe width="560" height="315" src="https://www.youtube.com/embed/itqMwuB8gOk"
	frameborder="0" allowfullscreen></iframe>{: itemprop="associatedMedia" itemscope itemtype="http://schema.org/VideoObject" }
</div>

I recommend watching this video called "Secret Maps Of Britain" by Mark Thomas.
It is fascinating to watch it with the knowledge we have today. The "conspiracy
theories" that are presented like turning off the internet during crisis,
sharing data while spying, or editing maps to hide data is common place today
but was considered secretive knowledge when this video was made.

## Attack Vectors

Setting up servers is [hard][apachevuln]. It can be difficult to setup a web
server but it becomes infinitely more difficult when adding on an abstraction
layer like Tor, worrying about the safety or your users, and incorporating a
number of private and Government users who wish to cause you harm or unmask
you.

You can also attack the [internet backbone][tempora]. This gives you a birds
eye view of internet behavior and greatly simplifys finding the hidden services
hosted as .onion sites.

## Content

## Answers

1. Tor is a peer-to-peer platform that appears to regularly tout a strong
   connection to cyptocurrency and dark markets.

2. An example of a [Javcascript exploit is found here][cveexploit] with more
   [information][cvenist] provided by the NIST.

3. Tor functions by allowing users to anonymously share files, browse, chat,
   and more through the use of the Tor protocol.

4. Tor uses onion routing while Tor uses garlic routing. Tor is more focused on
   accessing servers outside the Tor network while Tor attempts to minimize
   connections to the clear net.

## Conclusion

## Final Recommendations

1. Register a PGP key.

2. Use Linux.

3. Contribute to a privacy enhancing project. I recommend Freenet. Pick one.

4. Develop relationships and build your own 'Darknet'. Network in the real world.

5. Contribute to Open Source Projects. 

[scaleways]: https://www.scaleway.com/ 'Web Hosting'
[gittor]: https://gitweb.torproject.org/tor.git 'The Tor Project GIT' 
[githubtor]: https://github.com/TheTorProject 'The Tor GitHub'
[installtor]: https://www.torproject.org/docs/debian.html.en 'The Tor Download'
[accomplicelaw]: http://criminal.findlaw.com/criminal-law-basics/what-is-complicity-or-accomplice-liability.html 'Criminal Law'
[tortarget]: https://www.theregister.co.uk/2014/09/19/fbi_overseas_hacking_powers/ 'Tor users are targets'
[accomplicelaw2]: https://lawshelf.com/courseware/entry/defenses-to-accomplice-liability 'Accomplice Law'
[torfinancials]: https://www.torproject.org/about/financials.html.en 'Financial Reports'
[militaryapplicationstor]: https://www.torproject.org/about/torusers.html.en#military 'Military Tor Applications'
[apachevuln]: https://thehackernews.com/2016/02/apache-tor-service-unmask.html 'Server setup is hard'
[fostacongress]: https://www.congress.gov/bill/115th-congress/house-bill/1865 'FOSTA'
[cloudcongress]: https://www.congress.gov/bill/115th-congress/senate-bill/2383 'CLOUD'
[mozcve]: https://www.cvedetails.com/vulnerability-list/vendor_id-452/product_id-3264/cvssscoremin-7/cvssscoremax-7.99/Mozilla-Firefox.html ' Firefox vulns'
[tempora]: http://archive.is/ueCuH 'Attack the back bone'
