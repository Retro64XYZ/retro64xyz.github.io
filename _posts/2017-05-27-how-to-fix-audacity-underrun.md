---
layout: post
title: "How do I fix the ALSA underrun error 7963 in Audacity?"
date: 2017-05-26T15:52:43-07:00
author: RetroMe
summary: >
  A short how-to on fixing an error found in Audacity. If you see an underrun
  error in Audacity that is causing distortion and sped up replay, this may fix
  your issue.
categories: computers
thumbnail: fa-microchip
tags:
 - how-to
 - Ubuntu
 - pulseaudio
 - audacity
---

I was seeing an underrun error when attempting to use the latest version of
Audacity on my Ubuntu box. It would cause the sound to become fast and
distorted during playback. Audacity was completely unusable.

## The error

```
ALSA lib pcm.c:7963:(snd_pcm_recover) underrun occurred
```

If you see these errors, there is a fast way to fix it.

## The fix

``` bash
$ sudo vim /etc/pulse/daemon.conf
```

```
default-fragments = 5
default-fragment-size-msec = 25
```

Open the pulse daemon configuration file, stay in normal mode, and then type -

```
/default-fragments
```

This causes VIM to search. You will find two lines that have been commented out
using `;`. Uncomment the two lines above and edit their values to be 5 and 25
respectively. Then write and quit. `:wq` 

``` bash
$ pulseaudio -k
```

You will then need to kill and restart pulseaudio. You may have to wait for a
while for your USB microphones to reconnect. Once you do this, it should solve
your issue.

## The Explanation ( What did I do? )

The [Arch Linux Wiki][ArchLinuxWikiURL] defines the default fragments like so -

> Audio samples are split into multiple fragments of default-fragment-size-msec
> each. The larger the buffer is, the less likely audio will skip when the
> system is overloaded. On the downside this will increase the overall latency.
> Increase this value if you have issues.

When we edit the configuration and increase the size of the fragments, we are
less likely to run into an underrun. At the size we have chosen, we are
unlikely to suffer from a tremendous latency issue. Your hardware may require
fine tuning of the numbers chosen.

[ArchLinuxWikiURL]: https://wiki.archlinux.org/index.php/PulseAudio#Setting_the_default_fragment_number_and_buffer_size_in_PulseAudio 'A great database of information for Linux'
