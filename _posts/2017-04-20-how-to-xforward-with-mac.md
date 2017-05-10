---
layout: post
title: "How do I use Docker and XForwarding with OSX?"
date: 2017-04-19T15:52:43-07:00
author: IWriteThings
summary: >
  A short introduction to using X-forwarding with Docker in a Macintosh OSX Machine.
categories: computers
thumbnail: fa-microchip
tags:
 - how-to
 - xforwarding
 - macintosh
 - apple
 - osx
 - ssh
---

Running a Docker container and using XForwarding to acces the contents is not
straight forward in Mac OSX. Users will often attempt to use the command and
discover that the box reports no error but does not spawn their desired
software. The below instructions can be used to assist a user in forwarding the
contents of their box on OSX.

You have two options so please read the entire page first and choose what works
best for you before continuing.

## Option 1

* Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads) and the VM Extension Pack.
* Install [Docker](https://www.docker.com/docker-mac)
* Install [XQuartz](https://www.xquartz.org/)
* Install brew

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

* `brew install socat`

## Option 2 (Recommended)

You can also use brew to install docker, xquartz, virtualbox, and all other tools.

* Install brew

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

* `brew cask install virtualbox`
* `brew install docker`
* `brew install Caskroom/cask/xquartz`
* `brew install socat`

You must still manually download and install the VM extension pack for Vbox.

## Setup XQuartz

In a terminal type -

`open -a XQuartz`

1. Go to the preferences and then security tab. Select Allow connections from network clients.

2. Open a terminal and type - ( substitute `en0` for the device with your local IP address )

`ip=$(ifconfig en0 | grep inet | awk '$1=="inet" {print $2}')`

3. Using the same terminal type

`echo $ip`

Verify the IP is correct then do.

`sudo xhost + $ip`

## Setup socat

1. Open a terminal and type

`socat TCP-LISTEN:6000,reuseaddr,fork UNIX-CLIENT:\"$DISPLAY\"`

This command blocks the terminal. So you will need a new terminal window.
Append a `&` to the command if you want to make it nonblocking.

You can then use the fg command to foreground the command and kill it with ctrl-c if necessary.

## Run the torbrowser

1. Open a terminal and type

`docker build github.com/paulczar/docker-torbrowser`

then do

```
docker run -i -t --rm -e DISPLAY=10.1.24.141:0 -v /tmp/.X11-unix:/tmp/.X11-unix:ro paulczar/torbrowser
```

Replace the IP address with your local IP. It was the IP assigned to the variable $ip.

## References

[Alexellis Blog](http://blog.alexellis.io/linux-desktop-on-mac/)

[paulczar Github](https://github.com/paulczar/docker-torbrowser)

[Docker For Mac](https://fredrikaverpil.github.io/2016/07/31/docker-for-mac-and-gui-applications/)
