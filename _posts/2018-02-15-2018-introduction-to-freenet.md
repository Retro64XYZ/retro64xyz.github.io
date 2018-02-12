---
layout: post
title: "Introduction To Freenet"
date: 2018-02-11T15:52:43-07:00
author: RetroMe
summary: >
  Introduction To Freenet is a two-hour course designed to provide an
  introduction to Freenet, uses for anonymous browsing tools, and why privacy
  matters. It will focus on the practical uses for Freenet, how others may
  attempt to unmask you, and why tools like Freenet are applicable to the
  public.
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

[The Freenet Project.](https://freenetproject.org/index.html)

Censorship-resistant communication. Freenet claims to be a peer-to-peer
platform to enable and promote communication and publishing without the fear of
interference.  Freenet provides the ability to browse websites, post to forums,
and publish files while enjoying strong privacy protections. It is a platform
for publishing that does not and cannot silence the user.

Privacy is important. Privacy is a counter weight to the amount of force that
others can exert on us without our consent. When a person is well informed
about us we are less likely to be able to voice unpopular opinions, posit
questions, or to take action that could be construed as outside the norm. A
lack of privacy prevents people from being able to think for themselves for
fear of being punished or ostracized by the group.

Freenet is one tool that can be employed to enhance your privacy, give you a
platform to publish on, and to contribute to global discourse. It is not a tool
for surfing the clear net. You should not use Freenet if you main goal is to
post on Facebook, surf Youtube, or use tools like GMAIL. Freenet is for
individuals interested in contribution and discussion.

## How does Freenet Work

[Kent State University][peernetreview] has a very good explanation of Gnutella,
Bittorrent, and Freenet protocols.

## How To Install

1. [Review the code][githubfreenet] on the GitHub platform! You don't have an
   excuse. You need to stop and look at the tool, how it is made, and who is
   making it.

2. [Acquire hosting][scaleways] on an external platform. You have a lot of
   options.  I prefer scaleway as a platform because they are off shore. Pick
   your favorite country, pick a provider, and get a VPS. A $3.00 'starter
   cloud' is a sufficient package for hosting a Freenet install.

   Host Country List -

   * Panama
   * Hong Kong
   * Seychelles
   * Slovakia
   * Hungary
   * Russia
   * Syria
   * Turkey

3. [Get the installer][installfreenet] and get it onto your VPS. The process
   will look like the following.

	```
	$ wget 'https://github.com/freenet/fred/releases/download/build01479/new_installer_offline_1479.jar' -O new_installer_offline.jar;
	$ java -jar new_installer_offline.jar;
	```

4. We will want to run the software locally. This can be done with a tunnel.
   Run this command on your local machine.

	```
	$ ssh -L 8888:127.0.0.1:8888 YOURSERVERIPHERE
	```

5. We then open a browser on our local machine and surf over to
   http://localhost:8888

6. You will then want to surf over to Status->Internet Connection and get your
   ports. You can then open those ports in your firewall.

## How To Setup

Setting up Freenet can feel daunting. New users are bombarded with questions
during the setup process and will often feel confused on what is the best way
to protect themselves while using this tool. Depending on how popular you are,
you may need to make decisions on how you will use Freenet in order to best
defend yourself. The ultimate goal is to run the system under 'Maximum'
security levels while only connecting to individuals that you are familiar
with. In practice this will often be difficult or impossible to implement
without the ability to build trust and community with other users.

### High Confidence

Set your security level to 'Normal' and use 'High' protection for your
Downloads, Uploads, and Freenet browsing cache. You can be discovered to be
running Freenet with some reliability but you are also contributing to the
growth and health of the network at large. Set a good password when prompted.
Do not post data that can be correlated to a person. Be wary of your
mannerisms, screen name use, or uploading files with meta data that could be
used to pinpoint you as a user.

### Low Confidence

This situation warrants more ground work. Similar to how we may wish to trade
information during signing parties, you will need to seek out like minded
individuals, trade connection data, and use 'High' or 'Maximum' protection
settings. You will want to network with trusted members and not connect to
individuals you do not know. As the warnings on the page states, adding people
as friends you don't know will not improve security. You should also use 'High'
protection for downloads and employ a strong password.

## Censorship

The [Daily Stormer][dstormerverge] moved to a Tor hidden service. They lost
their protection provided by [Cloudflare][cloudflare] and were forced off of
the clear net.

The move of the Daily Stormer brought on [calls to censor Tor][torcensor] and
issues were raised about whether 'free speech' should be allowed if someone
doesn't agree with what is being said.

You should [read the statement from the Tor Project][torstatement] that they
made available on their blog.

Freenet takes a very strong stance against censorship and has a binary attitude
in that they believe that all speech should be allowed but any speech can be
challenged. This is the correct stance to take.

## Attack Vectors

Freenet suffers from a handful of vulnerabilities that could reduce the quality
of the network, halt access, or poison results. It is also vulnerable to
certain physical issues as well. Information on vulnerabilities is available on
the [Freenet Wiki][securitysummary] and is a worthwhile read for any
researchers.

### Physical 

[Shut it all down][sop303] and turn off the internet.

Freenet, Tor, Gnutella, and any other tool that exists on the internet is
vulnerable to the ultimate attack. You can shut down the internet and
individuals will no longer be able to communicate without alternatives. It is a
brutal and fast method that could be employed by a Government just as easily as
by hackers. Even a [mistake][scavengecut] could remove an entire country from
the internet for a period of time. 

[The communications act][killswitch] gives the President unlimited power to
shutdown the internet. The United States began developing a method to shut down
communications within the US shortly after the Arab Spring as the power wielded
by activists on Facebook and Twitter desmonstrated the danger of allowing
unfettered access to these tools during an uprising.

### Digital

#### Denial Of Service Attack

You can attempt to fill the network with junk data. Each system can and does
only provide a small amount of space for others to use when moving data around
the network. You could upload junk data and begin the process of making many
requests for that data. A user with sufficient resources may be able to force
peers to download and fill their drives with this junk data. This would drive
down the speed and performance of the network and may force an exodus of users.

#### Monitoring

Users who employ anonymous networks will often produce traffic with specific
signatures. 'Odd' behavior can be searched for by ISPs or others with access to
the traffic being generated. If you are running the Freenet software on a
server outside of your physical control it will most likely be possible for
that company to figure out exactly what you are doing. A quick peek at HTOP
reveals a running process with the word 'freenet' inside. It would not be
impossible for a company to search for processes running with the word
'freenet' in their name. The resources require to break the anonymity of
Freenet are immense and not easily wielded by less than State level actors as
far as we know at this time.

#### Denial Of Service Attack II

Block all seed nodes and attempt to make life miserable for any users
attempting to use Freenet in the open. If users must rely on seed nodes, it
becomes much more difficult for them to connect to the network successfully. It
also becomes an avenue of attack when those seed nodes are poisoned by bad
actors. They may be able to bootstrap new users with hostile public keys. This
could lead to them being able 'surround' the node and therefore be able to
guess what data is stored on the box or manipulate that box to download certain
data. This threat is very low.

## Privacy Threats

The website [Darkode][darkode] was used by criminals to lower the barrier to
entry for cyber criminals. It was once used by people like Brian Krebs of
[Krebs on Security][krebsite] for gathering information in near real time.
Darkode relied heavily on Tor and paranoia for their survival but it was shut
down.

[Playpen][ppop] was run by the FBI.

[Childs Play][auscp] was run by Australian Law Enforcement.

[The Black Ice Project(PDF)][blackice]{:target="_blank"} made the claim that
Freenet users could be compromised using a convuluted method to reveal the
systems used to store specific data. The Freenet project has refuted the claims
made and the [source code][blackicefalse] shows that their method is flawed or
a fabrication.

>Well, this is alarming.  Their entire grounds for probable cause are based on
>an outright lie. Freenet's probabilistic decrement does not work at all in the
>fashion described in that paper (which is largely copy and paste from other
>documents, including Wikipedia). Five minutes of studying the source code would
>have led them to discover this.  Four years of investigating and all that
>they've come up with is "hey, we're stumped so lets just lie to the courts
>about this and hope that no one catches on".

While there is undoubtably illegal content on Freenet, it is much rarer. The
lack of server side processing, databases, and the ability to use the tools
available to turn a profit are all major turn offs for those individuals
attempting to conduct illicit business. You are more likely to find ramblings,
rantings, and complaints on Freenet. You are also better protected against
vulnerabilities and browser exploits because the Freenet hosting tools will
attempt to strip javascript, flash, and other attack vectors from sites before
you ever load the page.

## Content

Is there content on Freenet? Yes! I found some very good radio dramas,
interesting rants, and simple blogs. While there isn't a ton of content, it is
your responsibility to build more. We cannot allow privacy tools to be
synonymous with criminal enterprise and should endeavor to enhance the security
of the network by both providing space as well as injecting content. Something
as simple as a site designed to regularly upload memes, funny pictures, or even
jokes could be incredibly helpful in legitimizing the use and growth of these
tools.

Search engines, indexes, and announcement pages are all available for Freenet.

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
   and hosts content in a decentralized way in order to reduce the
   effectiveness of traditional DDOS attacks.

## Conclusion

Privacy, Anonymity, and Authorship Assurance are still important concepts that
we need to focus on. There are many threats that have developed with the sole
intention of reducing our freedom, limiting conversation, and disrupting our
right to autonomy. There are corporate, government, and private interests who
are each working to end our right to anonymity as well as chill discourse.
Information has become valuable to that point that many companies now subsist
on the gathering of this data as well as dissemination of it.

It is your duty to contribute to the defense of the internet and the right to
privacy. Each of us must take a stand by employing the tools that allow us to
participate in civic discourse without fear of a heavy handed response. You
deserve the right to hold an unpopular opinion, to ask questions, and to learn.
No single group should hold a monopoly over discussion.

You can help build the future of communication by being an advocate for
freespeech, anonymous networks, and open and civil discourse. We should not
allow our differences to become a muzzle. We must contribute to the health and
welfare of the internet in order to reduce the chance that we will one day
discover ourselves unable to use it. Don't allow the internet to become 'The
Facebook Machine'. Develop your skills so you can ensure a future for the
internet.

## Final Recommendations

1. Register a PGP key.

2. Use Linux.

3. Contribute to a privacy enhancing project. I recommend Freenet. Pick one.

4. Develop relationships and build your own 'Darknet'. Network in the real world.

5. Contribute to Open Source Projects. 


## Continued Reading

[Understanding Freenet(PDF).][cornellfreenet]{:target="_blank"}

[P2P Attacks(PDF).][p2pattacks]{:target="_blank"}

[githubfreenet]: https://github.com/freenet/fred 'The Freenet Repo'
[scaleways]: https://www.scaleway.com/ 'A cloud computing platform'
[installfreenet]: https://github.com/freenet/fred/releases/download/build01479/new_installer_offline_1479.jar 'Installer'
[darkode]: http://archive.is/XAlfN 'Darkode used Tor'
[krebsite]: https://krebsonsecurity.com/ 'Brian Krebs Website'
[ssecurity]: https://secure.ssa.gov/RIL/SiView.do 'Social Security Admin'
[sskrebs]: http://archive.is/z13HZ 'Brian Krebs Social Security Warning'
[dstormerverge]: http://archive.is/wR2Vh 'Daily Stormer Blocked'
[peernetreview]: http://archive.is/T32C2 'Tutorial on Gnutella, Bittorrent, and Freenet'
[torcensor]: http://archive.is/zeQ6Y 'Allow Tor relays to censor content'
[sop303]: http://archive.is/v8WY6 'SOP 303 kills the internet'
[killswitch]: http://archive.is/L8JD4 'Internet Kill Switch'
[torstatement]: http://archive.is/MSj2y 'Tor project responds to demands to censor'
[scavengecut]: http://archive.is/WyRwS 'Old woman turns off Georgian internet'
[securitysummary]: https://github.com/freenet/wiki/wiki/Security-summary 'View the WIKI for the security summary for freenet'
[cloudflare]: http://archive.is/hdKv4 'Cloudflare dumps Daily Stormer'
[ppop]: http://archive.is/KIkzQ 'Playpen Bust'
[auscp]: http://archive.is/6Et01 'Austalian Police Run Child Porn Ring'
[blackice]: /../assets/pdf/blackice_project.pdf 'The Black Ice Project'
[cornellfreenet]: /../assets/pdf/freenet_breakdown_cornell.pdf 'Cornell Freenet'
[blackicefalse]: https://github.com/freenet/fred/blob/build01475/src/freenet/node/PeerNode.java#L1603 'Blackice cannot work'
[p2pattacks]: /../assets/pdf/2005DCGreview.pdf 'P2P Attacks'
