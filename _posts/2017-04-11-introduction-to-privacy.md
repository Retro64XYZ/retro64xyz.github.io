---
layout: post
title: "Introduction To Privacy"
date: 2017-04-11T15:52:43-07:00
author: IWriteThings
summary: >
  Introduction To Privacy is a two hour course that provides a rough outline of
  the tools and techniques that can be used to assist an individual in
  enhancing their privacy and becoming more aware of the liberties they are
  trading in return for convenience.
categories: computers
thumbnail: fa-desktop
tags:
 - tor
 - proxy
 - vpn
 - series
 - phoenix linux users group
---

## Performance Objective

At the conclusion of the course the student will be able to:

1. Identify the amount of entropy required to identify an individual online.
2. Identify the three major Psychographic segments targeted by advertisers.
3. Identify one type of marketing that uses tracking.
4. Understand what a proxy is.
5. Understand what a VPN is.
6. Understand what Tor does.

<div class="video-container">
<iframe width="560" height="315" src="https://www.youtube.com/embed/d5Z8_rX_EWA"
	frameborder="0" allowfullscreen></iframe>{: itemprop="associatedMedia" itemscope itemtype="http://schema.org/VideoObject"}
</div>

## Privacy

Privacy is defined as the condition of being free from observation or
disturbance. The right to privacy is not guaranteed by the Constitution of the
United States. Although the right to privacy is implicitly granted in the First
Amendment, Third, Fourth, and Fifth. Your right to privacy has been a
justification for many civil liberties cases. In addition, most of the States
recognize four torts based on your right to privacy. This includes intrusion
upon private affairs, public disclosure of private facts, false revelations or
publicity about a person, and assuming the name or likeness of a person to
deceive or for gain. 

## Entropy

The [Electronic Frontier Foundation](https://www.eff.org/) provides a
mathematical formula that allows an individual to measure how likely you are to
be able to use information to reveal their unique identity. The quantity of
likelihood is called entropy and it is measured in bits. There are approximately
8 billion people on the planet Earth, therefore we can deduce that we require
approximately 33 bits of entropy to successfully identify a person in the
noise. 

```
2^33 = 8589934592
```

If you know a persons ZIP code and their birthday, that may still not be enough
to positively identify a person. If they live in a sufficiently large city,
there could be plenty of men and women who share those numbers. Add gender and
you narrow the pool. If you begin to add in shopping habits and interests, we
quickly begin to narrow down the candidates.

Members of the law enforcement community are often forced to take incomplete
descriptions of peoples and link that information back to a suspect. You may
have seen informational releases or pleas to the public asking for help in
identifying a person. We often release what information we have in the hopes
that someone else can fill in the blanks. This same behavior is practiced by
advertisers and data brokers who trade in anonymous data.

## Browser Tracking

The EFF [Browser Fingerprint](https://panopticlick.eff.org/) provides many 
interesting tools that can be used to test your browser in order to see how
easy it is to identify. The panopticlick project is designed to demonstrate how
likely your browser can be finger printed and identified among all the other
browsers on the internet. 

## Docker

Docker can be used to
[containerize your browser](https://github.com/chrisdaish/docker-firefox) and
provide a level of anonymity if properly configured. Running your code inside
of Docker would also require that other users do so as well. Browser tracking
would easily reveal the use of Docker and you would harm your ability to be
anonymous if you are the only one using these tools. Therefore, it is important
that more people use these tools to reduce the likelihood that it will be
This would require a fundamental change in how the public noticed. 

### Security

1. Kernel namespacing.
2. Docker daemon security.
3. Configuration.
4. Hardened kernel / container security.

Namespaces provide the isolation between the processes in the container and the
processes in other containers or the host itself. The containers have their own
network stack and don't get privileged access to the sockets or interfaces of
any other container. You can assume the containers are on bridge interfaces and
should be treated like physical machines that have a common ethernet switch.

A docker container should not be able to exhaust memory, CPU, disk I/O, or
bring down the host system. This helps defend against some denial of service
attacks. If you are on a VPS, this is invaluable behavior because it prevents
issues for the other tenants when an application begins to act up.

The daemon itself does require root access and any user permitted to use Docker
or control the daemon should be well vetted. You can share folders with the
daemon and if you share the `/` directory of your host, you can alter the host
without any restriction. Do not share your root file system.

You should also understand that if you are running Docker to manage services,
you should move as many services into Docker as you can. This tool is more
effective when you leverage it for the majority of your needs.

## Advertising And Surveillance Capitalism

[Google Remarketing](https://support.google.com/adwords/answer/2453998?hl=en) 
is one form of advertising that requires as much information about their
audience as possible. Google and other companies have a vested interest in
knowing "you". You may have surfed over to a website about dogs and later
received targeted ads about dogs in your browser only moments later. This is
an example of Google Remarketing.

Three major Psychographic segments in advertising are Personality, Lifestyle,
and Interests. The marketing of your data is invaluable because it allows an
advertiser to know what you like, how you live, and what you are most likely
going to need to spend money on next. The majority of traffic that advertisers
are dealing with is generated by bots or other shady means. There is a belief
that remarketing provides a more "real" and relevant picture of a human being
and can contribute more to the bottom line of the company in question. 

## Social Credit

[Chinese companies in pilot program for social credit](http://www.bbc.com/news/world-asia-china-34592186).

Are you a good citizen? Do you support the appropriate political party,
practice good life habits, and refrain from behavior that could be indicative
of "wrong" thought? The Chinese government is working to implement a program of
social credit which will be controlled by the companies contracted with after
the initial testing is completed. The social media use, medical history, and
shopping habits will each contribute to the persons scores. Buy diapers? Then
you are probably a responsible parent and your score goes up. Have a person in
your home who is playing video games for more than an hour per day? They are
considered "idle" and the irresponsibility score of the house hold goes up,
lowering the house hold score. It pays not to be "idle".

Social credit is being used to measure whether people are compatible on dating
sites, whether they are allowed specific privileges, and even if they are
allowed to rent a place to stay. The concept has been transformed into a game.
Mobile phone applications provide games designed to encourage players to share
their scores in order to guess which friend has the best score. There will also
be a special list for 'VIP' users. If you plan to be a teacher, journalist,
medical doctor, or tour guide, you will be forced to have a much higher score
than a person of less importance or risk loss of employment.

This social credit will be used to keep track of taxes, traffic tickets,
criminal records, academic degrees and club membership, party membership, and
even if females have been instructed to take birth control. The entire life of
the Chinese citizen will soon be tracked and graded for acceptability and this
data will be used for all manner of decisions.

## Personal Privacy And Safety

[A Google employee stalked underage girls](http://gawker.com/5637234/gcreep-google-engineer-stalked-teens-spied-on-chats) as reported by Gawker. [A second individual](https://www.wired.com/2010/09/google-spy/) 
also behaved in a similar manner and was released. No information on this
persons alleged violations of company policy was revealed other than the fact
that they broke strict internal privacy policies.

Your location can be tracked and the [position of your phone can be guessed with a 24-hour leeway](http://www.cultofmac.com/235009/researchers-have-developed-an-algorithm-that-predicts-your-next-location-within-20-meters/).

You can also produce [digital noise](https://slifty.github.io/internet_noise/index.html)
as a form of protest against the individuals who are collecting your data.

## Virtual Private Networks

[OpenVPN](https://openvpn.net/) is the gold standard for secure private networks.

A VPN allows the user to encapsulate their traffic, create a virtual network,
and then pass that information on to the destination while theoretically
limiting the amount of data leaked to any one monitoring the connection between
the server and the client.

Free and lifetime membership VPN accounts should be avoided due to their use of
monitoring to subsidize the cost of the VPN itself. A monthly fee between $5.00
or up-to $10.00 per month is a reasonable price to pay for a secure connection
for basic privacy purposes.

You should assume that logging is made on any system that you are not the sole
controller of in terms of both the software as well as the hardware side. No paid
service should be considered absolutely secure.

## Tor

The [Tor Project](https://www.torproject.org/) provides several tools that can
be used to provide a level of anonymous surfing to the user. The internal Tor
network is considered relatively secure but there are also links to the outside
world known as exit nodes.

You must disable four items in the browser to have reasonable privacy.

1. Cookies
2. Javascript
3. Java
4. All plugins

### This Is Not Perfect

[Law Enforcement tracked down a bomb threat](http://www.theverge.com/2013/12/18/5224130/fbi-agents-tracked-harvard-bomb-threats-across-tor) after realizing the individual in question had used Tor.

## Proxies

A Proxy server can be used to transport the traffic of a single application,
offers no additional encryption beyond that offered by the protocol used, and
are only good for mundane tasks. You should also refrain from using free
proxies as they can be used to spy on the user with extreme ease. A user
connecting over SSL could potentially find their traffic unmasked by software
like "Squid" in conjunction with [SSL bump](http://wiki.squid-cache.org/Features/SslBump).
TLS stops Squid from being able to bump as designed. This limitation may not exist for other proxies.

## Docker Tor Browser

[Docker-Torbrowser](https://github.com/paulczar/docker-torbrowser)

``` bash
sudo docker run -i -t --rm -e DISPLAY=$DISPLAY \
-v /tmp/.X11-unix:/tmp/.X11-unix:ro paulczar/torbrowser
```

## Docker Tor Proxies

[Alpine Privoxy Tor](https://medium.com/@rdsubhas/docker-image-with-tor-privoxy-and-a-process-manager-under-15-mb-c9e344111b61)

[GitHub](https://github.com/rdsubhas/docker-tor-privoxy-alpine)

`docker run -d -p 8118:8118 -p 9050:9050 rdsubhas/tor-privoxy-alpine`

`curl --proxy http://localhost:8118 ifconfig.co`

## Answers

1. 33 Bits of Entropy are required to successfully identify a person.
2. Three major Psychographic segments in advertising are Personality, Lifestyle, and Interests.
3. Google Remarketing is a tracking advertiser.
4. A proxy is used for displaying a different IP or impersonating a country. It has low security.
5. A VPN is a higher security tool that provides a separate IP as well as adds encryption.
6. Tor is a protocol used for the explicit purpose of providing anonymity.

## Conclusion

The web is not designed to make a user anonymous. We have integrated many web
2.0 tools into our day to day life and it has greatly reduced the ability of
the average user to be anonymous. Individuals interested in regaining their
anonymity online will require more than a change of browser. The fundamental
behaviors that we take for granted when surfing and interacting with others
online must all be reconsidered and managed carefully. 

## Final Recommendations

1. Move services and applications as appropriate to Docker.
2. Consider [mail-in-a-box](https://mailinabox.email/) to help replace Google Applications.
3. Donate money or time and run a tor relay node or exit node depending on your knowledge and skill.
