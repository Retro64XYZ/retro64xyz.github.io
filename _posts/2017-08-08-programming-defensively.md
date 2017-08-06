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

[The metasploit for eternalblue][EternalBlueMetasploit] is a very good example
of how one could take advantage of a buffer overflow state.

> There is a buffer overflow memmove operation in Srv!SrvOs2FeaToNt. The size
> is calculated in Srv!SrvOs2FeaListSizeToNt, with mathematical error where a
> DWORD is subtracted into a WORD. The kernel pool is groomed so that overflow
> is well laid-out to overwrite an SMBv1 buffer. Actual RIP hijack is later
> completed in srvnet!SrvNetWskReceiveComplete.

What is [memmove](http://www.cplusplus.com/reference/cstring/memmove/)?

> Copies the values of num bytes from the location pointed by source to the
> memory block pointed by destination. Copying takes place as if an
> intermediate buffer were used, allowing the destination and source to
> overlap.
>
> The underlying type of the objects pointed by both the source and destination
> pointers are irrelevant for this function; The result is a binary copy of the
> data.
>
> The function does not check for any terminating null character in source - it
> always copies exactly num bytes.
>
> To avoid overflows, the size of the arrays pointed by both the destination
> and source parameters, shall be at least num bytes.

A DWORD is 32 bit. A WORD is 16 bit. This is where our overflow happens.

#### What is a pointer?

A pointer is used to assign the memory address value of a variable to a
variable. You could potentially access the memory address in C using the `&`
symbol.

```
int main() {
	int var1;
	printf("The address of var1 is: %x\n", &var1);
	return 0;
}
```

The above code could return something like -

The address of var1 is: bff5a200

#### The Buffer

A buffer overflow happens when software tries to continue writing past the
start or end of the buffer. A buffer overflow or buffer underflow happens in
either the stack or the heap. When a problem in the buffer occurs the software
can crash, compromise or release information, or function as a foothold into
escalating the attack with either privilege escalation or remote code
execution.

#### Very Important Concepts About The Buffer

* The stack and the heap both reside in the RAM/Disk of the computer running
  the code.

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

```
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

### Weak Crypto

Implementing cryptographic tools is hard. It is very easy to make a serious
mistake when trying to implement encryption algorithims and secure data. Even
the bad guys have learned that cryptography is hard. Varians of cryptolocker
have been released into the wild using weak crypto and have been proven easy to
defeat. Some variants of these attacks have been defeated and data recovered
without any payment made.

### Social Engineering

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

### Failure To Expect Attacks

Many companies simply do not expect to come under attack. There is a severe
lack of education in the cyber security field and many individuals do not
understand that there is a level of security that can be gained with education
and due dilligence. There is a disservice in the security mantra of 'not if but
when'. Users should not be made to feel hopeless but instead empowered.

## Software Development For Penetration Testers

There are numerous applications used for penetration testing and security
related work. I have curated a small list from different sources here.

1. [German Python List][PythonPenTestTools]
2. [The PenTesters Framework][PenTestersFramework]
3. [Awesome List Of Github Things][AwesomeListOfThings]
4. [Awesome Pen Testing Tools][AwesomePenTest]

## Jobs That Need Software Developers

Many cyber security related positions or jobs require the possession of some
kind of security clearance. As is common in many aspects of cyber security,
security theatre is more important than the skill sets or capabilities of those
involved. Reality Winner, the NSA Contractor who leaked information from the
government to the news was a possessor of a clearance who was also a 'self
proclaimed resistor and Bernie Sanders supporter'.

Many HR offices do not know that the jobs they are trying to fill can use a
software security person or programmer on their team. The idea that a
programmer can help in many different functions is foreign to many of these
individuals. There seems to be a serious disconnect in how computing is treated
in this day and age.

## Developing Developer Skills

<div class='video-container'>
<iframe width="560" height="315" src="https://www.youtube.com/embed/KMU0tzLwhbE"
	frameborder="0" allowfullscreen></iframe>
</div>

There are an inordinate amount of resources today that are available to
aspiring coders. A small list of websites that can help you learn will be
included here.

1. [Learn-C](http://www.learn-c.org/)
2. [Udemy](https://www.udemy.com/c-programming-for-beginners/)
3. [Toptal](https://www.toptal.com/c/the-ultimate-list-of-resources-to-learn-c-and-c-plus-plus)
4. [Tutorial Point](https://www.tutorialspoint.com/cprogramming/)
5. [Lynda](https://www.lynda.com/) -- Free with a library card in Chandler
6. [Vim Adventures](https://vim-adventures.com/)
7. [Rails For Zombies](http://railsforzombies.org/)
8. [Checkio](https://checkio.org/)
9. [Code Combat](https://codecombat.com/)

## You Can Still End Up In Trouble

Do you remember [Marcus Hutchins][Hutchins1]? The security researcher who
'stopped' WannaCry? He was recently arrested at DefCon 2017 and charged for
creating a credit card stealing application called [Kronos][Hutchins2]. He is
being accused of the creation and distribution of tools being used to steal
bank account information, accessing and damaging computers he is not authorized
to use, and wiretapping. 

Marcus became famous after he 'stopped' Wannacry from his parents home. He
registered a website and the Wannacry application fell dormant. Here is a
conspiracy theory. Marcus may have had more knowledge about Wannacry than
previously thought, registered the website due to concern about the number of
hospitals hit, and someone turned him over to authorities for his work with
Kronos.

Kronos was sold on the AlphaBay and Hansa dark web markets. AlphaBay and Hansa
were both government run honey pots appropriated as part of a massive take
down. [The sites were part of a massive law enforcement
operation][AlphaTakeDown] and only a short while after the arrests begin,
Hutchins is swooped upon. It is an interesting thought exercise.

## Answers

1. Coders develop the tools we use every day.

2. OWASP is an organization that provides unbiased information about internet
   and computer applications.

3. The testing phase is a good time to locate issues in the code.

4. A buffer overflow happens when software tries to continue writing past the
   start or end of the buffer.

5. DRY stands for DON'T REPEAT YOURSELF

## Conclusion

Software development skills are invaluable for security researchers, network
engineers, and more. The number of jobs that do not include or necessitate
software engineering are going to continue to shrink over the coming years. The
capability to function with at least one traditional programming language and
one scripting language will be the bare minimum necessary to succeed in
computer related fields.

Understanding how software works, who is writing that software, and how that
software is used is important to any one concerned about security. Closed off
source code and walled off systems must be removed from the landscape. Even
with software becoming increasingly open source, we must also do actual code
reviews and frequently check for issues. Few people, if any, have checked every
line of code in the Linux Kernel. We must gain the skills necessary to begin
checking for vulnerabilities.

## Final Recommendations

1. Use Linux! 

2. Learn a programming language and a scripting language. Skills cross!

3. Register a Github and contribute to projects.

4. Pay attention to what software you are using. Choose Open Source. 

## Glossary

1. Memory Leak - Previously allocated memory is not deallocated by the programmer. 
2. Pointer - A pointer is an object which points to another value stored in
   memory by the memory address assigned.
3. Crypto - Shorthand for Cryptography. The study and implementation of secure
   communication.
4. Buffer - The temporary placeholder in memory where data is dumped.
5. Stack - The data structured used to store data in a particular order. Last In First Out.

[PythonPenTestTools]: https://github.com/dloss/python-pentest-tools 'Curated Github List'
[PenTestersFramework]: https://github.com/trustedsec/ptf 'An installation script for pentesting tools'
[AwesomeListOfThings]: https://github.com/sindresorhus/awesome#security 'Curated list of Github Stuff'
[AwesomePenTest]: https://github.com/enaqx/awesome-pentest 'Curated Pentest Tools'
[Hutchins1]: http://archive.is/wFXKE 'Marcus Hutchins Arrested'
[Hutchins2]: http://archive.is/btC65 'Marcus Hutchins Charges'
[AlphaTakeDown]: http://archive.is/YezFG 'AlphaBay and Hansa taken down'
[EternalBlueMetasploit]: https://github.com/rapid7/metasploit-framework/blob/master/modules/exploits/windows/smb/ms17_010_eternalblue.rb
