---
layout: post
title: "Introduction To Operational Security"
date: 2017-06-11T15:52:43-07:00
author: RetroMe
summary: >
  Introduction To Operational Security is a two hour course that provides an
  outline of how to manage privacy, data security, and data assurance. We will
  discuss the tools and techniques used by professionals to manage their online
  presence.
categories: computers
thumbnail: fa-desktop
tags:
 - PGP
 - GPG
 - Keybase
 - phoenix linux users group
---

## A Quick Interlude With Wannacry

Wannacry affected a lot of people. Almost every country on the planet was
affected with over 300,000 machines compromised. It took hours for developers
to create variants as soon as the original infection began to appear. The update 
that resolved this issue is [located here][msupdate].

A [breakdown](http://archive.is/Fph0M) of the attack is available from zerosum.
I will summarize the event as so.

1. Microsoft had an exploit available in their SMB protocol since WindowsXP days.

2. Find out if the computer is x86 or x64.

3. Locate the .exe DOS MZ header.

4. Begin the process of allocating memory.

5. Find the SMB driver.

6. Allocate memory and copy code for the function hook. It stores a function
   pointer and then calls it and overwrites a member table with the hook. This
   creates a backdoor.

7. It then uses invalid SMB calls to 'knock' when it needs access. You can send
   shellcode in a payload packet in increments of 4096 bytes. The backdoor
   allocates executable memory, decrypts shellcode, and then runs it.

## Performance Objective

At the conclusion of the course the student will be able to:

1. Identify what PGP is.
2. Identify the use of a PGP Public Key.
3. Identify the use of a PGP Private Key.
4. Understand what encryption is.
5. Understand when to sign communication.
6. Understand what threats prey on trust issues.

<div class="video-container">
<iframe width="560" height="315" src="https://www.youtube.com/embed/lBH3UC8Wi54"
	frameborder="0" allowfullscreen></iframe>{: itemprop="associatedMedia" itemscope itemtype="http://schema.org/VideoObject"}
</div>

## Introduction

Privacy is the buzz word of the day. There is a dire concern that every person
on the planet is being surveilled in perpetuum. Businesses, classrooms, and our
private lives are at constant risk of exposure to enemies both foreign and
domestic.  Members of the media have decried encryption, privacy, and personal
freedom in the hopes of encouraging members of the public to give up their
freedoms in exchange for an illusion of safety. What can we do to ensure our
personal safety in an age of always on connections, constant monitoring, and
the potential for a major cyber terrorism event looming over us like a
poisonous cloud?

## Privacy Threats

[Children are being targeted][CTRecordingURL] by advertisers for their
personally identifiable information. There are children toys being sold that
ask kids for information like who their family members are, what they like to
do, and where they live. They also provide their 'opinion' on how the child
should feel about specific brands and companies.

In addition to conducting intelligence gathering and analysis on the children
in question, companies like the one in the article referenced are employing
[voice and biometric screening tools][NuancePDF] (PDF used without permission
for educational purposes only) which double as counter terrorism and
investigation software to monitor the inputs of the child.

The toys used by the children lack basic security and allow a connection by
Bluetooth with no authentication or password necessary. The toys also provide
two way communication as well as function as a covert listening device. It is
possible to make a connection and record conversations or communicate at will.

[Adults are being targeted][WeepingAngelURL] by tools like Weeping Angel. The
NSA was recently attacked and many of their tools have been released onto the
internet. Of note was the Weeping Angel attack. This attack allows individuals
to compromise a specific model of smart television in order to use it as a
covert spying and listening device. These tools are now being used to attack
the public by bad actors. We will continue to see attacks like
[WannaCry][WannaCryURL] employing NSA tools and methods.

Everything is on fire.

### Loose Lips Sink Ships

Stop telling people every thing about yourself.

[Even the military][MilTweetPDF] has had to get in on the social media game.
They have updated their operational security products to now include Twitter
and Facebook. You can view more at the
[CDSE](http://www.cdse.edu/resources/posters-cybersecurity.html).

##### Incidents

1. [Israeli](http://archive.is/E0UZh){:target="_blank"}

2. [United States](http://archive.is/2PZoo){:target="_blank"}

3. [United States](http://archive.is/7tvmm){:target="_blank"}

4. [The Republic Of 4Chan][4chanAirStrike1]{:target="_blank"}(Potentially Offensive Material)

5. [The Republic Of 4Chan][4chanAirStrike2]{:target="_blank"}(Potentially Offensive Material)

### SSL

You should only communicate with sites secured by SSL. SSL provides encryption
for your connection and protects user names, passwords, and other digital
information that is being transferred between your computer and the internet.
It does not however provide proof of data assurance and cannot prove that the
data is truthful. It is only good for providing a layer of encryption over the
data.

[Fake SSL Certificates that are trusted][FakeSSLURL] have been deployed over
the internet for domains like Google as well as others. [Symantec][FakeSSLURL2]
issued over 30,000 certificates improperly. This mishandling of SSL lead to
companies like Google restricting their use on their Chrome browser.

SSL is proof of encryption. It is not proof of ownership nor is it an assurance
that the content is real or truthful. It is solely proof of encryption and
should be treated as such. Even people who are hostile to you and yours can use
encrypted communications.

#### Download Assurance

[Linux Mint was compromised][LinuxMintHackURL] and proved that it is entirely
possible for a determined attacker to completely take over a website, Linux
distribution, and even the tools used to assure the quality of the download.

Separation of failure is vital for situations where an individual could
compromise a single point of failure and then build a complete attack from that
weakness. It is a cascading failure that a compromised website gave the user
the ability to upload an ISO, edit the page to display a different signature,
and then distribute the infected software.

The Linux Mint community has since changed their security practices and now
provide a very thorough if not a bit complicated method to verify the integrity
of their distribution.

#### How to verify a file

The first thing we need to do is verify the gpg key used to sign the
authenticity of the sha256 at the key server. [Keys][KeyServerUbuntuURL] are
hosted by Ubuntu and can be verified with a little bit of work.

1. sha256sum

2. Download the sha256sum.txt file

3. Download the signature for the sha file.

4. Get the sha with sha256sum -b *.iso

5. `gpg --keyserver keyserver.ubuntu.com --recv-key "27DE B156 44C6 B3CF 3BD7  D291 300F 846B A25B AE09"`

6. or `gpg --keyserver keyserver.ubuntu.com --recv-key A25BAE09`

7. `gpg --list-key --with-fingerprint A25BAE09`

8. `gpg --verify sha256sum.txt.gpg sha256sum.txt` verify key used was A25BAE09

#### Key Servers

Other key servers exist in the world. A short list can be found below.

1. [PGP Key Server](https://keyserver.pgp.com/)
2. [MIT Key Server](https://pgp.mit.edu/)
3. [SKS Key Servers](https://sks-keyservers.net/)

### No one on the internet knows you are a dog

![No One Knows You Are A Dog][UnknownDogMeme]

Privacy means that we are free of being observed or disturbed unless we choose
to be. If you do not tell people information about yourself, it is very
difficult for people to discover things about you. Websites do exist that
provide detailed information about people through public record and eventually
this data will need to be better managed. I estimate that within the next five
years we will see laws put into place to curtail the availability of public
records over the internet or in some way curb these data warehouses that
publish private information online.

Even though we have the capability to be extremely anonymous on the internet,
sometimes we need the opposite of that behavior. It can be important for a user
to be easily identifiable and that is where proof can be required.

### Keybase

GPG / PGP as a service.

[Keybase][KeybaseURL] provides powerful cryptography for every one and not just
for hardcore programmers. You can use their website or their mobile
applications in order to prove your ownership of specific products or to sign
and encrypt communications. As of 05-21-2017, the Keybase website requires an
invitation for access. You can contact users like myself over Mastodon or other
social media for access to this project.

### GPG - Build Our Key

How to generate -

```
$ gpg --gen-key
```

How to generate the revocation certificate -

```
$ gpg --gen-revoke [ID_OF_KEY] > ~/.gnupg/revocation-[ID_OF_KEY].crt
```

How to send your key to a public server -

```
$ gpg --keyserver pool.sks-keyservers.net --send-key 'THE FULL KEY ID'
```

How to backup your keys -

```
$ tar -zcvf gnukeys.tar.gz .gnupg/
```

Then just save the created file somewhere secure.

### Threats

There are an innumerable number of threats that could be employed to steal from
both individual as well as business. Some of these threats include whale
phishing as well as fraud. We will discuss them both as well as some of the
incidents that have proven their effectiveness in the arsenal of the threat
actor.

#### Whale Phishing

A specific form of phishing that targets high-profile individuals is called
whaling. This scam is usually detailed, well planned, and executed for the sole
purpose of causing someone with power to divulge secrets or provide money.
This type of attack usually focuses on a call to action with urgency. An
example may look like the following.

> Retro64XYZ! The business is at risk because we forgot to pay our bill to
> NigerianSuperConducters LLC. I know we usually pay them bi-weekly but the
> bank forgot to clear one of our checks and now we owe a double payment. Can you
> please send a payment of $1,800,000 to NigerianSuperBank, account number 12345,
> routing number 54321? If we don't pay it, they will stop making the chips we
> need and the whole business will go bust. Hurry! Also, don't call me because I
> am obviously on vacation in Idaho where I go all the time because that is where
> my mom lives and you know that because it is information you could find on my
> Facebook. Pay quick!

This is a silly example but it covers many bases you may see in a real whaling
email. There is a sense of urgency due to the possibility of the business going
bust. Do YOU want to be responsible for destroying the business? Obviously not.
There is a quick explanation of the problem, a method of resolution, and an
excuse for why you should do this thing now and not worry about verifying the
information in the email. The template is simplistic but with a bit more detail
could easily convince someone. This holds doubly true if the individual has
ever had previous problems with the bank or distributor before. Not unheard of.

### Fraud

Another method of fraud is the ever popular 'invoice' scam. This one is usually
targeted at companies or institutions and designed to attack the petty cash
type accounts. The fraudster will create an invoice for a service or purchase
and then send this invoice out to a large number of companies. The cost
presented will normally be something affordable and within budget. A $250 fee
for software or technical services is a popular one. Although, larger targets
may require [higher invoice costs](http://archive.is/JwNn6).

Facebook and Google were swindled out of $100 million dollars. An individual
forged emails, invoices, and logos and then began the process of charging
companies like Facebook and Google for fraudulent transfers. He spent two years
earning over $100 million dollars from his efforts before the companies
realized what was happening. This type of attack, also known as a B2B or
Business To Business attack, is extremely common place and has been used
against a multitude of victims.

### GPG - Encrypt With Our Key

You may want to refer to the [Debian GPG Guide][DebianKeysURL] for further
information.

## Answers

1. PGP is an internet standard for encrypting and digitally signing communication.

2. A public key is used to encrypt data. It is safe to give this key away.

3. A private key is used to decrypt data. It is not safe to give this key away.

4. Encryption is the process of encoding data to prevent unauthorized access.

5. Sign digital communications any time you need to impart trust in the origin of the data.

6. Phishing, Whale Phishing, and Fraud are all attacks that require a degree of trust to be effective.

## Conclusion

Privacy, Anonymity, and Authorship Assurance are all important aspects and
deserve equal focus by both the security community as well as the public. It is
imperative that the next generation of security researchers be able to not just
move in secrecy but provide proof of self. We cannot become so engrossed in the
'secret squirrel' stuff that we forget the practical and useful.

Some of the largest companies in the world have been victims of fraud, B2B
attacks, and other threats. No one is immune from these incidents but training
and experience are excellent tools in better protecting your business or
operations from threats.

## A Challenge

How to check if two files are the same -

`diff file1 file2`

`sha256sum file1`

`sha256sum file2`

1. You will find a link to two images below. They appear to be the same. Using
   the skills you learned today, diff them with sha256sum. Are they different?

   * [First Image][challenge00]
   * [Second Image][challenge01]

2. Find the hidden difference between the files.

3. Reveal the hidden message.

* Hint

  1. VIM - Delimiter - SECRET

  2. base64 -d (-D on mac)

  `echo 'message minus SECRET' | base64 -d`

Use the secret to solve the puzzle.

## Final Recommendations

1. Register a PGP key. Use [Keybase][KeybaseURL] if you are uncomfortable
   managing it yourself.

2. Familiarize yourself with scams.

3. Create a plan for dealing with emergencies. Who to contact to verify incidents?

4. Encourage the use of cryptography and digital signing in business.

## Glossary

1. PGP - Pretty Good Privacy provides cryptograhic privacy and authentication.

2. GnuPG - Is a complete and free implementation of OpenPGP.

3. Gpg4win - Is a PGP tool implementation for Windows.

4. Key Server - A computer that receives and serves cryptograhic keys to users 
   and programs.

[KeybaseURL]: https://Keybase.io/ 'Crypto For Everyone - PGP As A Service'
[CTRecordingURL]: http://archive.is/2noGW 'Threats To Children And Their Privacy'
[NuancePDF]: /../assets/pdf/nc_025785.pdf 'Nuance Identifier Sales PDF'
[MilTweetPDF]: /../assets/pdf/mil_tweets.pdf 'New Military Op Sec Warning'
[WeepingAngelURL]: http://archive.is/fD1kX 'CIA Listening Device For Smart Television'
[WannaCryURL]: http://archive.is/2XPVU 'WannaCry using NSA tools'
[LinuxMintHackURL]: http://archive.is/NHsxy 'Linux Mint Attack'
[FakeSSLURL]: http://archive.is/rbKo4 'Fake Certificates'
[FakeSSLURL2]: http://archive.is/KVH8a '30000 More Fake Certificates'
[DebianKeysURL]: https://wiki.debian.org/Keysigning 'A good guide from Debian on GPG'
[UnknownDogMeme]: /../assets/images/memes/on-the-internet-nobody-knows-youre-a-dog-meme.jpg 'Image Of Dog Sitting At Computer'
[4ChanAirStrike2]: /../assets/images/inserts/4chanAirStrike2.jpg '4Chan Bombathon'
[4ChanAirStrike1]: /../assets/images/inserts/4chanAirStrike1.jpg '4Chan Bombathon'
[KeyServerUbuntuURL]: http://keyserver.ubuntu.com 'The Ubuntu Key Server'
[challenge00]: /../assets/images/challenges/pgp-check/sailor-moon-floppy-disk0.jpg 'No Hidden Message'
[challenge01]: /../assets/images/challenges/pgp-check/sailor-moon-floppy-disk1.jpg 'Has Hidden Message'
[msupdate]: http://archive.is/YnRPo 'Microsoft Update'
