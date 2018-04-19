---
layout: post
title: "Introduction To Tor"
date: 2018-04-19T04:52:43-07:00
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

## FOSTA - Fight Online Sex Trafficking Act

The [FOSTA bill][fostacongress] was passed by the House of Representatives.
This kills the Craigs List. Any website found to be promoting prostitution or
sex trafficking can now be held responsible for the content within. This will be
selectively enforced to target start ups and small businesses.

Some news outlets have claimed that FOSTA will disproportionately harm innocent
LGBT peoples. These arguments are not new and have existed in relation to
computers for a long time. Please view the Computer Chronicles episode on 
[BBS and Modems][chronbbs] for an interesting discussion between the hosts, a
BBS sysop, and an assistant district attorney.

The question is posed - should admins be held responsible for the discussions
held on their boards? Is a BBS like a newspaper with first ammendment rights or
is it like a utilitie that is subject to regulation? The exact questions we are
asking today were previously posited then. What has changed between then and
now?

## The CLOUD Act Rains On Our Parade

The [CLOUD act][cloudcongress] is currently in the budget and is being snuck into use
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

Microsoft is in [court][courtcloud] already due to the passing of this bill. I
want to know what was on the server the government is after.

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

Tor works as an internet networking protocol with the intent of anonymizing any
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

[In fairness][elinkscve] I will also provide the 7 current vulnerabilities in
Elinks.

## How To Install

1. [Review the code][gittor] on their GIT platform! You don't have an
   excuse. You need to stop and look at the tool, how it is made, and who is
   making it. Check their [Github][githubtor] as well.

2. [Get the installer][installtor] and get it onto your computer. The process
   will look like the following.

	```
	$ apt install tor 
	```

3. Open the Tor Browser

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
laws concerning [accomplice liability][accomplicelaw]. You should also read more
about [accomplice law][accomplicelaw2].

Tor is used to commit crimes. The open net is used to commit crimes. Cars,
planes, trains, and even banjos have been used by criminals or became
instruments in crimes. We don't try to ban them, spy on people for owning them,
or worry that our neighbors may be serial 'pumpernicklers'. In 1988 a murder
was committed in Britain in which a man was beaten to death with bread. But
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

1. Set security to high.

2. Disable Javascript - No White lists

3. Keep Tor running some where with 24/7 uptime or as close to as possible

## Who Made Tor

Tor was originally developed as a method for the United States Government to
provide bi-directional communications over the internet where the source and
destination are hidden from view. The Department Of Defense, Naval
Intelligence, and DARPA deployed Tor in order to protect their assets and to
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
from their tax statements. You can see who is paying what, where donations come
from, and how much money is being spent on different aspects of the project.
Some believe that Tor is funded by the US [government][torgov]. I would be
inclined to believe it, but don't consider it a bad thing. The BBG, the
American Propaganda Company, provided approximately
[$6.1 million dollars][torfund] to Tor between 2007 and 2015.

I could not locate the financials for the RiseUp group.

## What does Tor do

Tor allows users to enhance their privacy and gives some level of identity
protection. It is not a perfect tool that can be trusted to make a users
completely anonymous, hidden, or invisible. No currently known tools can
provide absolute protection. The Tor system relies on a custom Firefox fork,
local software or proxy, and an internet connection.

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
eye view of internet behavior and greatly simplifies finding the hidden
services hosted as .onion sites. We have discussed this before but it needs to
be repeated.

Javascript provides many vulnerabilities. As per usual.

## Significant Incidents In Tor History

Tor is in a particularly difficult position and has suffered several 
[scandals][torchat]. One situation occurred in which an individual who presented
themselves as a State Department Employee achieved employment within the Tor
project. They then later revealed they were a member of an American
intelligence agency and had joined up with Tor in order to 'do some good' while
using false credentials. They later claimed that the Government had no
knowledge of their clandestine 'personal operation' to improve Tor. One Tor
member was so concerned by this deception and their own situation that
they believed their family would be killed.

mrphs or [Nima Fatemi][mrphs] is(was) an Iranian who functioned as a
contributor to the Tor project. Shortly after this chat occurred he moved to the
United States and began deploying Tor exit nodes inside
[libraries][librarytor]. The Tor nodes were [brought down][libdown] and then
allowed to [run again][libup] after public support came through.

Tor is regularly used for hosting child pornography. Playpen was run by the FBI
and Childs Play was run by the Australian Police Department. Governments are
unmasking onion sites, taking them over, and impersonating these sites. I do
not know of any efforts to unmask the method used for capturing these sites or
understanding the methodology used for defeating Tor.

## Content

Tor content includes all open net sites that do not explicitly block Tor use
as well as many .onion based sites. The most well known and notorious criminal
related sites rely on Tor due to the manner in which it provides a similar
style of platform as the open net for conducting web based business.

Most users employ Tor for surfing clear net sites with enhanced 'security'.
However, over 1 million users are currently logging into Facebook using Tor. My
assumption is that many of these users live in non permissive environments that
do not allow connection to Facebook.

## Answers

1. Tor is a peer-to-peer platform that employs the use of a specific browser to
   function. 

2. Users of Tor include Doctors, Educators, Privacy Advocates, Drug Addicts,
   Seditionists, and Criminals. 

3. Tor functions by allowing users to anonymously share files, browse, chat,
   and more through the use of the Tor protocol.

4. Tor uses onion routing while I2P uses garlic routing. Tor is more focused on
   accessing servers outside the Tor network while I2P and Freenet attempt to
   minimize connections to the clear net.

## Conclusion

This concludes our three part deep dive into privacy enhancing tools. I stand
by my statement that I believe Freenet to be the best of the three that were
reviewed. Tor provides an interesting tool set designed to provide some very
specific protections but due to the nature in which it is configured, the
reliance on the Tor Browser, and the historical as well as current issues we
have found, I do not recommend this toolset.

I wish deeply that we could build an internet that was designed to be secure
from the start. The current assortment of tools for 'securing' us or providing
us with 'privacy' are bandages that hide a festering wound. The internet was
not made to be secure or private and we have moved far beyond the point of
being able to resolve the issues with the current deployment of tools. It will
be some time before we find a resolution for our problem and I personally
believe that we will not find a resolution for the issue.

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
[courtcloud]: http://archive.is/yka6B 'Supreme Court Case Drop For Microsoft'
[hushmail]: http://archive.is/P3qio 'Hushmail broke for law enforcement'
[torgov]: http://archive.is/ppIwD 'Tor project funding controversie'
[torfund]: http://archive.is/9pVBt 'Tor Broadcasting Links'
[elinkscve]: https://www.cvedetails.com/vulnerability-list/vendor_id-1592/Elinks.html 'Vulnerabilities in Elinks'
[torchat]: /../assets/tor-chat-06292016.txt 'A mole in Tor'
[mrphs]: https://twitter.com/mrphs 'Nima Fatemi'
[librarytor]: http://archive.is/iAPLV 'Tor in Libraries'
[libdown]: https://techcrunch.com/2015/09/14/homeland-security-shuts-down-librarys-tor-node-citing-situational-awareness/ 'Library Relay Closed'
[libup]: http://archive.is/oghA5 'Library Relay Reopened'
[chronbbs]: https://www.youtube.com/watch?v=Pb7te_HZyiA&t=14m21s 'BBS And Free Speech'
