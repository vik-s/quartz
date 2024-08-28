---
title: Origami-inspired RF
tags:
  - misc_letters
project: substack
date_published: 
status: 
final title:
---
It's been a whole month that we have been going hard on RF power amplifier classes. Not sure if you've had enough yet, but my ability to write about power amplifiers is running a bit saturated (pun intended.) 

Power amplifiers is such a large and fascinating topic, I'm sure we will keep revisiting it from time to time. I haven't even scratched the surface of architectures like Doherty, envelope tracking and outphasing, or addressed linearization techniques like digital pre-distortion in any level of detail. 

Reply to this email and let me know if you want me to continue writing about other power amplifier classes or other related topics. I'll can always pick it up again in a bit.

If you missed the series on basic power amplifier classes, here are the articles you can check out.
- links

To freshen things up a bit, I decided to look up what research won the Best Paper Award at the 2024 International Microwave Symposium. What I found led me down a very interesting path of recent innovations that we will discuss in this post.

There is a new class of RF circuits that draw inspiration from Origami, the Japanese (add a footnote that it actually got popular in Japan but nobody really knows who started it) art of paper folding. Just like you can make different shapes out of paper, you can reconfigure circuits to operate differently.

In this post, we will look at a few published examples of origami-inspired circuits and how they work.

Here are the pieces of research we will look at:
- A mm-wave phased array antenna with near limitless reconfigurability (best paper winner)
- A C-band reconfigurable dipole antenna for CubeSat applications.
- Wafer-level 3D RF inductors\
- thing1
- thing2
- thing3

Read time: X mins

~~

There are at least a few reasons why one would consider making paper swans out of RF circuits.

**Reconfigurability**
Fixed RF systems are not optimal when it comes to changing RF environments. It is better if RF blocks are context-aware and adapt to provide the best overall system performance. Back in the old days, reconfigurability meant that components like antennas were mounted on big servos and moved around to point to where the signal is coming from. In fact, radio astronomers still mount [large parabolic dishes](https://www.viksnewsletter.com/i/140865578/gigantic-antenna-arrays) [on train tracks](https://public.nrao.edu/telescopes/VLA/) and move them around to form [different configurations](https://public.nrao.edu/vla-configurations/) in order to detect the faintest signals from the universe. This is often too slow for modern applications.

Soon, engineers found that they could achieve the same results by steering antennas using [phased arrays](https://www.viksnewsletter.com/p/basics-of-phased-array-antennas-and?r=222kot&utm_campaign=post&utm_medium=web). Instead of moving the antennas around, they could do the same thing by controlling the phase shift between different antennas. The constructive and destructive interference between different antennas in the array helped steer the radiated beam without physically moving it. Since the whole thing is electronic, the time taken to steer antennas is really fast, in the order of microseconds.

What if we could somehow mix physical modification with electronic beam steering? This is a great application for foldable phased arrays, where one could make physical transformations slowly, but then use electronic beam steering for rapid beam steering. Can we literally form any antenna pattern we want, and then steer the beam? This is where origami-inspired phased arrays come in. 

In the paper, [Beyond Planar: An Additively Manufactured, Origami-Inspired Shape-Changing, and RFIC-Based Phased Array for Near-Limitless Radiation Pattern Reconfigurability in 5G/mm-Wave Applications](https://ieeexplore.ieee.org/abstract/document/10531260), Al 





If you find any other interesting articles on this topic, reply to this email and let me know, I will cover them in a future article.



~~

### Origami-inspired mm-Wave Reconfigurable Phased Array Antenna


I may have to look up and write about this.

Origami tessellations, notably the miura-ori [1] and the “eggbox” [2], have found applications in frequency-selective surfaces (FSS), showcasing spatial frequency reconfigurability.

