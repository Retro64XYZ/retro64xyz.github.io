---
layout: post
title: "Introduction To Defensive Programming"
date: 2017-07-10T15:52:43-07:00
author: RetroMe
summary: >
  Introduction To Defensive Programming is a two hour course focused on
  developing the skills necessary to understand best practices for software
  development. This is not an introduction to programming class but is instead
  focused on helping the student better understand software related security
  and how the programmer is the first line of defense. Even non programmers can
  benefit from this course without issue. 
categories: computers
thumbnail: fa-desktop
tags:
 - software
 - programming
 - developers
 - best practices
 - phoenix linux users group
---

## Performance Objective

At the conclusion of the course the student will be able to:

1. Identify why coding is the backbone of security.

2. Identify an organization that provides unbiased information about internet
   and computer applications.

3. What phase of software development lends itself to finding vulnerabilities
   in the code?

4. What is a buffer overflow?

5. What does DRY stand for?

## Introduction

Software development and security are intertwined concepts. Your hardware is
useless without software to run on it. It is extremely important that security
experts have detailed understanding of their hardware and software as well as
the different types of vulnerabilities that could affect their ecosystem. 

## Vulnerable Software

Code should be correct first and fast second. While profiling code for
performance and having fun writing fancy or impressive scripts designed to wow
your peers may be an exercise for an evening, it should always take a backseat
to the need for functional and reliable code. There are many vulnerabilities
that you can introduce into your code and it is better to be verbose and plain
than to be fancy and interesting. Writing clever code will not protect you from
determined hackers.

### Buffer Overflow

A buffer overflow happens when software tries to continue writing past the
start or end of the buffer. A buffer overflow or buffer underflow happens in
either the stack or the heap. When a problem in the buffer occurs the software
can crash, compromise or release information, or function as a foothold into
escalating the attack with either privilege escalation or remote code
execution.

#### Very Important Concepts About The Buffer

* The stack and the heap both reside in the RAM of the computer running the
  code.

* The stack is a Last In First Out data storage space that is built to handle
  a single call to a function, block, method, or the equivalent object.

```
void stackFunction() {
	Counter d;
} // Object 'd' is destroyed when the function finishes.
```

* The heap is the general purpose storage where data remains as long as the
  application is running. You MUST delete data in an explicit manner if you
  create it on the heap or you will create a memory leak.

```C
void heapFunction() {
	Counter *d = new Counter();
	delete d;
} // Object d must be destroyed by hand or it will create a memory leak.
```

* The stack is a fixed size while the heap can grow. The stack can overflow in
  what is called a stack overflow if there is not enough room on the stack to
  handle memory being assigned to it.

* Some languages provide 'garbage collection' and will free/delete memory from
  the heap as items fall out of scope.

### Unvalidated Inputs

* Your application will most likely need to receive input at some point during
  the lifetime of the program. This input could be provided by a user in the
  form of a text input field, an uploaded file, piped, or data sent over a
  network or made available by a REST call. You cannot trust this data.

* Common terms used are input validation or sanity checking.

* An attacker could attempt to crash the program by providing improper or
  poorly formatted data to the program in an attempt to cause issues with the
  software. This could be as simple as using emoji characters to crash a
  database like in WordPress, passing SQL query code in order to force an SQL
  injection, or even uploading executable code in the form of a file and then
  running that code on a web server.

### Race Conditions

Race conditions occur when multithreaded applications attempt to access a
shared resource without any kind of protection or locking. Consider the
following code.

```C
for ( int i = 0; i < 10000000; i++ ) {
   x = x + 1;
}
```

If you have two threads attempting to access the below code, you can quickly
enter a race condition. The problem occurs as the threads involved can be at
any point in the process at any time. It is even possible for x to be changed
in the between time of reading x and writing x.

1. T1 reads x = 7
2. T1 adds 1 to x, x = 8
3. T2 reads x = 7
4. T1 writes 8 to x
5. T2 adds 1 to x, x = 8
6. T2 writes 8 to x

This is a compounding problem that will only get worse as more threads are
introduced. 

### Access-Control Failure

I believe I can safely assume that any one reading this document will be
familiar with the act of access control. If you have ever logged into a website
or registered an account with a company, you will have participated in the
access control life cyle. The vast majority of discussion of security
vulnerabilities is in terms of privilege and the exploits necessary to gain
more privileges. The individuals attack your software, systems, or accounts are
usually looking for some way to gain permissions to perform Create, Read,
Update, or Delete actions for nefarious purposes. 

### Weak Crypto / Weak Authorization Methods / Poor Planning

#### Crypto

Implementing cryptographic tools is hard. It is very easy to make a serious
mistake when trying to implement encryption algorithims and secure data. Even
the bad guys have learned that cryptography is hard. Varians of cryptolocker
have been released into the wild using weak crypto and have been proven easy to
defeat. Some variants of these attacks have been defeated and data recovered
without any payment made.

#### Social Engineering

Educating the users while providing a simple to use interface that explains to
the user are the combination to needed to help users protect themselves and
others. Users should be educated about the value of the data and how it should
be treated with clear instructions on how the data should be interacted with.
Users should know better than to divulge information over the phone or through
email. Valuable data should be shared using agreed upon and secure methods.

Consider a system in which no social security number is to ever be repeated
over the phone or through email. Transport of that data should be made through
a system that distributes the data in a secure manner to a secure channel. Can
it still be exfiltrated? Yes. But the difficult level is now much higher.

Users should also be warned during use of the software. They may be informed
about the dangers with tool tips or text made available to explain that at all
times they should be cognizant of hackers or bad actors.

#### Failure To Expect Attacks

Many companies simply do not expect to come under attack. There is a severe
lack of education in the cyber security field and many individuals do not
understand that there is a level of security that can be gained with education
and due dilligence. There is a disservice in the security mantra of 'not if but
when'. Users should not be made to feel hopeless but instead empowered.

## Software Development For Penetration Testers

## Jobs That Need Software Developers

## Developing Developer Skills

<div class='video-container'>
<iframe width="560" height="315" src="https://www.youtube.com/embed/KMU0tzLwhbE"
	frameborder="0" allowfullscreen></iframe>
</div>

## Answers

1. Coders develop the tools we use every day.

2. OWASP is an organization that provides unbiased information about internet
   and computer applications.

3. The testing phase is a good time to locate issues in the code.

4. A buffer overflow happens when software tries to continue writing past the
   start or end of the buffer.

5. DRY stands for DON'T REPEAT YOURSELF

## Conclusion

The Dark Net is a valuable tool to fight censorship, assemble, and to spread

## Final Recommendations

1. Use Linux! 

## Glossary

1. Memory Leak - Previously allocated memory is not deallocated by the programmer. 

[Hansa-Testing-Kit]: http://hansamkt2rr6nfg3.onion/listing/95135/ 'Hansa Market - Testing Kit'
