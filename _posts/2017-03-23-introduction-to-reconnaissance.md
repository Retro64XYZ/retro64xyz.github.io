---
layout: post
title: "Introduction To Cyber Reconnaissance"
date: 2017-01-22T15:52:43-07:00
author: IWriteThings
summary: >
  Introduction to Cyber Reconnaissance is a two-hour course focused on
  providing learners with a gentle introduction to the tools and techniques used
  to probe and locate targets for attack.
categories: computers
thumbnail: fa-desktop
tags:
 - hacking
 - soft skills
 - education
 - series
 - phoenix linux users group
---

## Performance Objective

At the conclusion of the course the student will be able to:

1. Identify six out of six reasons why someone may want to be a hacker.
2. Identify and describe the four parts of the hacking timeline.
3. Identify and describe the three teams involved in hacking and their role.
4. Identify and describe tools used in the probing aspect of the hacking timeline.

## Why Hack?

1. Fame
  * The pursuit of recognition.

       [Kevin Mitnick][6] is an example of a fame driven hacker. He has been in
       numerous news articles, movies, magazines, and blog posts. He also sells
       books.

2. Fortune
  * Monetary reward for services rendered. 
  * [Bug Bounty Programs](https://bugcrowd.com/).
  * Criminal Rewards.

	   [Kevin Poulsen][2] was an example of a hacker driven by the drive of
	   monetary gain. He is most famous for rigging a contest for a Porsche.
	   His thirst for a larger payout eventually led to him being found guilty
	   of mail, wire, and computer fraud as well as money laundering and other
	   financial crimes.

3. The pursuit of knowledge
  * Some people like to learn how things work and are natural tinkerers.

	   [Richard Stallman][3] is an icon of traditional hacker culture. He is a
	   proponent of freedom and has written numerous essays on software
	   freedom. He is now a political activist.

4. Political statement
  * Hacktivism has recently reached the news as a method to rebel against issues
    real or imagined.

	    [Gary McKinnon][1] is an example of a political hacker. He believed
	    the United States Government was hiding evidence of UFO contact with
	    the planet. He hacked into US military and NASA networks in order to
	    investigate this.

5. Criminal Enterprise
  * Furthering the aims of a criminal enterprise by committing crimes like
    identity theft, credit card theft, or unauthorized access of a computer.

	   [Astra][4] was a hacker who stole and sold data that was in relation to
	   weapons. It is believed that he stole information about weapons stored
	   in French Dassault Group computers and then resold that data to
	   numerous countries. His real identity was never released but he has
	   been caught. He was accused of costing Dassault over $360 million in
	   damages.

6. Fun and laughs
  * Some people just want to see the world burn.

	   [LulzSec][5]

## Hack Timeline
1. Reconnaissance
  * Who is the target?
  * What is the target?
  * When is the best time to execute scans or attacks?
  * Where is the target?
  * How should you attack?

2. Scan and Probe
	* Tools
	* Techniques
	* Documentation

3. Infiltration
	* Vulnerabilities
	* Bugs
	* Remote Code Execution (RCE)
	* Soft Skills

4. Exfiltration and Attack Continuity
	* Slow and Silent
	* Smash and Grab

## Teams

1. Red
  * The offense. Team members here are looking for exploits, vulnerabilities,
    and ways into a system or network. They usually follow the rules of
    engagement as set forth by the White team.

2. Blue
  * The defense. Team members here are on the lookout for the Read team and
    their antics. They are usually well versed in how the application and
    network is built and functions. They follow the ROE on defensive actions.

3. White
  *  Management and direction. Normally sets the ROE and how the operation will
     be conducted. These are the management members who monitor the event and
     also filter the results.

## Scan Tools

### nmap

nmap or Network Mapper is an open source tool for network exploration and
security auditing.

Perform an OS Detection Enabled Scan

``` bash
$sudo nmap -O target.host.com
```

Scan a range of IP addresses

``` bash
$sudo nmap -O 10.0.0.0-24
```

Scan a range using notation

``` bash
$sudo nmap -O 10.0.0.0/24
```

Aggressive Finger Print Scan With Versioning

``` bash
$sudo nmap -sV target.host.com
```

What is available locally?

``` bash
$sudo nmap -sP 192.168.0.0/24
```

### masscan

masscan is an Internet-scale port scanner, useful for large scale surveys of
the Internet, or of internal networks.

Scan the entire internet for all ports while using an exclude file

``` bash
$masscan 0.0.0.0/0 -p0-65535 –excludefile exclude.conf
```

Scan the entire internet for dns servers using an exclude file

``` bash
$masscan 0.0.0.0/0 --excludefile no-dod.txt -pU:53 --banners --output-filename dns.xml
```

### traceroute

traceroute  tracks  the route packets taken from an IP network on their way to
a given host. It utilizes the IP protocol's time to live (TTL) field and
attempts to elicit an ICMP TIME_EXCEEDED response from each gate‐ way along the
path to the host.

``` bash
$traceroute target.host.com
```

### wireshark

Wireshark is a GUI network protocol analyzer.  It lets you interactively browse
packet data from a live network or from a previously saved capture file.
Wireshark's native capture file format is pcap format, which is also the format
used by tcpdump and various other tools.

Add the user to the wireshark group

``` bash
$sudo adduser -a aaron wireshark
```

Enable the Name Resolution

```
Edit -> Preferences -> Name Resolution -> Enable Network Name Resolution
```

#### Example Filters

Filter by port 80 traffic

```
tcp.port eq 80
```

Filter by conversation

```
ip.src==192.168.0.0/24 and ip.dst==192.168.0.0/24
```

View all tcp recets

```
tcp.flags.reset==1
```

Only view http and dns

```
http and dns
```

Mask traffic

```
!(arp or icmp or dns)
```

View the man file for the filters

``` bash
$man wireshark-filter
```

### tshark

TShark is a network protocol analyzer.  It lets you capture packet data from a
live network, or read packets from a previously saved capture file, either
printing a decoded form of those packets to the standard output or writing the
packets to a file.  TShark's native capture file format is pcap format, which
is also the format used by tcpdump and various other tools.

Add the user to the wireshark group

``` bash
$sudo adduser -a MY_USER wireshark
```

Get the device number for our network card

``` bash
$tshark -D
```

Dump the traffic on the card to the terminal

``` bash
$tshark -i #THEDEVICE
```

Dump to file

``` bash
$tshark -i #THEDEVICE -w #_device_dump.pcap
```

### whois

whois searches for an object in a RFC 3912 database.

``` bash
$whois example.com
```

## Web Applications

Web Applications and search engines can be used for gathering target data
during the reconnaissance and probing stage. Individuals would be on the
lookout for weak links in the security such as individuals dealing with
financial troubles, divorce, or job issues. A restructuring of the company
could mean employees will be laid off and they may be more likely to actively
assist in an attack or allow an attack to occur due to apathy.


* [Google Dorking](https://en.wikipedia.org/wiki/Google_hacking)
* [IP Logger](https://iplogger.org)
* Social Media
* Court Data
* Public Records

## Vulnerabilities

Poorly cared for infrastructure could also be of use to the hacker. They may
discover systems that have not been kept up to date and could find
vulnerabilities available for their use in unpatched software.

* [Vulnerabilities](https://cve.mitre.org/index.html)

## Conclusion

Education, leadership, and attention to detail are the core principals
that will allow an individual or company to recover from an attack.
There is no assurance that a vulnerability will not be found in your
company. Your preparation and understanding of security will allow you
to recover with the least amount of damage done when a hacker arrives
on your doorstep looking to pilfer or make a name for themselves off of
your embarrassment.

All parties involved should be educated about the dangers posed by social
media, poor practices, or ignorance of standards. Continuous education is
important but that education must be relevant and interesting for individuals
to be willing to learn from it. Make learning worthwhile with incentives for
passing tests. A company I know of provided a day of paid vacation to an
inquisitive secretary who refused to allow a social engineering test to
proceed. Make success worthwhile.

Lead by example. When the top brass have open social media accounts, release
improper information over the wrong channels, or do not demonstrate good
choices, it reduces every ones effectiveness. Listen and ask questions. You
must be willing to allow others to bring issues forward without fear of
retribution or they will hide problems until it is too late. Don't foster a
culture of fear when people locate issues that need to be rectified.

The final principal is attention to detail. Thoroughness and accuracy in every
task should be cultivated within the culture. Backups should be made but also
tested. Regular reviews for improperly managed company data should be made.
Make lists and plans that can be followed to ensure that a job can be performed
correctly. It is in the fine details that the enemy looks for their avenue of
attack.

## Final Recommendations

1. Develop a physical security plan.
2. Develop a data security plan.
3. Document business processes and review them for vulnerabilities.
4. Foster a security-positive culture.

[1]: https://en.wikipedia.org/wiki/Gary_McKinnon "Gary McKinnon - Wikipedia Link"

[2]: https://en.wikipedia.org/wiki/Kevin_Poulsen "Kevin Poulsen - Wikipedia Link"

[3]: https://stallman.org "Richard Stallman - Website"

[4]: https://www.scmagazine.com/hacker-arrested-in-greece-for-stealing-selling-weapons-data/article/554157 "Astra - Greek Hacker"

[5]: https://en.wikipedia.org/wiki/LulzSec "LulzSec - Wikipedia Link"

[6]: https://mitnicksecurity.com "Kevin Mitnick - Web Site"
