---
layout: post
title: "Introduction To Operational Security"
date: 2017-05-13T15:52:43-07:00
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

## Performance Objective

At the conclusion of the course the student will be able to:

1. Identify what PGP is.
2. Identify the use of a PGP Public Key.
3. Identify the use of a PGP Private Key.
4. Understand what encryption is.
5. Understand when to sign communication.
6. Understand what threats prey on trust issues.

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
[WanaCry][WanaCryURL] employing NSA tools and methods.

Everything is on fire.

### Loose Lips Sink Ships

Stop telling people every thing about yourself.

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
authenticity of the sha256 at the key server.[Keys][KeyServerUbuntuURL] are
hosted by Ubuntu and can be verified with a little bit of work.

1. sha256sum

#### Key Servers

1. https://keyserver.pgp.com/
2. https://pgp.mit.edu/
3. https://sks-keyservers.net/

### No one on the internet knows you are a dog

![No One Knows You Are A Dog][UnknownDogMeme]

### Keybase

[Keybase][KeybaseURL] provides powerful cryptography for every one and not just
for hardcore programmers. You can use their website or their mobile
applications in order to prove your ownership of specific products or to sign
and encrypt communications. As of 05-21-2017, the Keybase website requires an
invitation for access. You can contact users like myself over Mastodon or other
social media for access to this project.

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
move in secrecy but provide proof of self.

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

## Glossary

1. PGP - Pretty Good Privacy provides cryptograhic privacy and authentication.

2. GnuPG - Is a complete and free implementation of OpenPGP.

3. Gpg4win - Is a PGP tool implementation for Windows.

4. Key Server - A computer that receives and serves cryptograhic keys to users 
   and programs.

[KeybaseURL]: https://Keybase.io/ 'Crypto For Everyone - PGP As A Service'
[CTRecordingURL]: http://archive.is/2noGW 'Threats To Children And Their Privacy'
[NuancePDF]: /../assets/pdf/nc_025785.pdf 'Nuance Identifier Sales PDF'
[WeepingAngelURL]: http://archive.is/fD1kX 'CIA Listening Device For Smart Television'
[WanaCryURL]: http://archive.is/2XPVU 'WanaCry using NSA tools'
[LinuxMintHackURL]: http://archive.is/NHsxy 'Linux Mint Attack'
[FakeSSLURL]: http://archive.is/rbKo4 'Fake Certificates'
[FakeSSLURL2]: http://archive.is/KVH8a '30000 More Fake Certificates'
[UnknownDogMeme]: /../assets/images/memes/on-the-internet-nobody-knows-youre-a-dog-meme.jpg 'Image Of Dog Sitting At Computer'
[KeyServerUbuntuURL]: http://keyserver.ubuntu.com 'The Ubuntu Key Server'
[challenge00]: /../assets/images/challenges/pgp-check/sailor-moon-floppy-disk0.jpg 'No Hidden Message'
[challenge01]: /../assets/images/challenges/pgp-check/sailor-moon-floppy-disk1.jpg 'Has Hidden Message'
