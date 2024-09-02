---
title: Origami-inspired RF
tags:
  - antennas
project: substack
date_published: 2024-09-01
status: 🚧
final title: How origami-inspired phased arrays are reshaping the future of antennas
---
It's been a whole month that we have been going hard on RF power amplifier classes. Not sure if you've had enough yet, but my ability to write about power amplifiers is running a bit saturated (pun intended.) If you enjoyed the series, or want more articles, reply to this email and let me know.

If you missed the series on basic power amplifier classes, here are the articles you can check out.
- links

To freshen things up a bit, I decided to look up latest research from the 2024 International Microwave Symposium, the premier conference in the field of RF and Microwave engineering. What I found was an idea so interesting that I felt compelled to write about it. 

As it turns out, there is a new class of RF circuits that draw inspiration from Origami, the Japanese (add a footnote that it actually got popular in Japan but nobody really knows who started it) art of paper folding. Just like you can make different shapes out of paper, you can physically reconfigure circuits to operate differently.

[Hani Al Jamal](https://www.linkedin.com/in/hani-aljamal/), a PhD student, and a team of researchers led by Prof. Manos Tentzeris at Georgia Tech, authored a paper titled [Beyond Planar: An Additively Manufactured, Origami-Inspired Shape-Changing, and RFIC-Based Phased Array for Near-Limitless Radiation Pattern Reconfigurability in 5G/mm-Wave Applications](https://ieeexplore.ieee.org/abstract/document/10531260), which won the [Best Paper Award](https://ece.gatech.edu/news/2024/06/al-jamal-wins-best-paper-award-2024-ieee-international-microwave-symposium) at the 2024 International Microwave Symposium.

This paper describes **a phased array antenna from which you can synthesize any radiation pattern**. It uses both electronic and physical modifications to achieve this. In this post, we will get into the details of exactly how this works.

Special thanks to Hani for providing additional information, pictures and for reviewing a draft of this post.

Here is a brief outline of the content:
- Need for Adaptive RF Circuits
- Eggbox Phased Array
- Interconnect Systems
- Practical Applications

**Read time**: X mins

~~
### Need for Adaptive RF Circuits

Fixed RF systems are not optimal when it comes to changing RF environments. It is better if RF blocks are context-aware and adapt to provide the best overall system performance. Back in the old days, reconfigurability meant that components like antennas were mounted on big servos and moved around to point to where the signal is coming from. In fact, radio astronomers still mount [large parabolic dishes](https://www.viksnewsletter.com/i/140865578/gigantic-antenna-arrays) [on train tracks](https://public.nrao.edu/telescopes/VLA/) and move them around to form [different configurations](https://public.nrao.edu/vla-configurations/) in order to detect faint signals from the universe. This is often too slow for modern applications.

Soon, engineers found that they could achieve the same results by steering antennas using [phased arrays](https://www.viksnewsletter.com/p/basics-of-phased-array-antennas-and?r=222kot&utm_campaign=post&utm_medium=web). Instead of moving the antennas around, they could do the same thing by controlling the phase shift between different antennas. The constructive and destructive interference between different antennas in the array helped steer the radiated beam without physically moving it. Since the whole thing is electronic, the time taken to steer antennas is really fast, in the order of microseconds.

If you are new to the concepts of antenna and phased arrays, check out earlier posts about it.
- links

What if we could somehow mix physical modification with electronic beam steering? This is a great application for foldable phased arrays, where one could make origami-like physical transformations slowly, but then use electronic beam steering for rapid directional changes. Can we literally form any antenna pattern we want, and then steer the beam?
### Eggbox Phased Array

The inspiration for the phased array antenna comes from the design of an [eggbox built out of paper](https://youtu.be/e8WHFI3z2yA?si=9UGZVxs-CLCy6-lD). It is basically a grid of upside down pyramids with an open base, into which you can place eggs. The research paper explains how just one of these open-base pyramids can be used as a building block for larger reconfigurable arrays. When looking at just one of them, the unit cell looks more like an [origami fortune teller](https://youtu.be/SAhiIlTxUYA?si=0NLP_PYrRJ39wo5p) that my kids make all the time.

*put pictures of eggbox or fortune-teller*

To make this eggbox-unit/fortune-teller radiate, a 4-element phased array antenna is implemented on all four faces, and a Qorvo AWMF-0108 28 GHz beamformer RFIC is used to steer the beam at 11.25° increments.

Just like an origami design, this unit cell can be folded across either axis, or laid out completely flat, which means that it is physically possible to alter the direction of radiation. Since the phased array antenna on each face is itself capable of further steering the beam, you get an antenna that can be used to generate nearly any radiation pattern you want through a combination of physical folding and electronic beam steering.

Here are some ways to shape the radiated beam from this antenna.

1. **360° Azimuth Coverage**: In its pyramidal orientation, turn on only one phased array and steer the beam to its maximum value, and then switch to the phased array on the next face. This ensures a continuous handoff between different phased arrays on the faces, and provides 360° azimuth beam steering.
2. **Bending along an axis**: Fold the array along any one axis, and as the fold angle decreases, the radiation pattern reconfigures from a four-beam pattern to a two-beam pattern as shown in the figure.
3. **Arbitrary shaped beams**: Fold the array across either axes by an arbitrary angle, turn on anywhere between a single phased array to all four phased arrays, provide digital weights to the phased array to control both amplitude and phase to antenna elements (even do [gain tapering](https://www.viksnewsletter.com/i/140865578/gain-tapering) to control grating lobes), and then you can virtually synthesize any radiation pattern you want.

### Interconnect Systems

Whenever you see a foldable circuit running at 28 GHz, the immediate concern is the RF performance of the interconnect, and its stability over repeated folding. The authors designed a clever solution that uses an "arch hinge interconnect" and is created using 3D printing technology with flexible80A, a flexible photopolymer resin. The interconnect itself is a 50Ω transmission line inkjet printed onto a Rogers RO3003 substrate and combined with the 3D printed support structures.

The result is a stable hinge design that does maintains low loss over the 180° range of folding, and shows no degradation up to 300 folds.

*put picture of hinge interconnect system*

Another concern when designing interconnects for the eggbox unit cell is that the feed-point can only be present on one of the faces of the 3D structure. This means that the interconnect system does not feed all four phased arrays on the structure equally. (footnote: which is important for proper beamforming. you want phase shifts to be controlled only by the beamformer IC and not have static shifts from things like interconnect systems.) To fix this, there are extra sections of interconnects to compensate for this difference of overall electrical length.

*put picture of beta_l compensation networks*

### Practical Applications

The beauty of this design is that the eggbox unit cell can simply be cascaded to form a larger array that can be spatially reconfigured along either axes. The modular design approach has more advantages:
1. If any single unit cell fails, it can easily be replaced.
2. Selective faces of the eggbox array can be activated to synthesize different radiation patterns based on power consumption requirements and transmit/receive operating modes.
3. The additive 3D printing approach produces lesser waste.

Let's look at some ways this phased array can be effectively used:

- **Full Duplex Operation**: Say we want to use the same antenna array for transmit and receive simultaneously. With the modular system, it is possible to simply activate all phased arrays on any given face for transmit, and a different face for receive. The ability to control beams electronically also allows the transmit/receive beams to track targets if needed.
- **Multi-beam Operation**: By using different folding angles, we already saw how we could synthesize two or four beams from the array. In autonomous vehicles, for example, each beam can be assigned to a different function such as communication, navigation and obstacle avoidance.
- **Adjustable Beamwidths**: Since folding angle controls the width of the beam, unfolding the array to form wide beam widths is helpful in aircraft search operations, and then by folding up the array, a narrow beam helps in targeted rescue operations.
- **Space Constrained Systems**: Especially with the rise in popularity of small form-factor, low-cost satellites such as CubeSats, the ability to fold up an antenna array during launch, and then deploy while in orbit is valuable. Reshaping the antenna array and steering beams in space will be useful to form satellite mesh networks to increase connectively across the globe.

This implementation of an origami-inspired antenna uses only two degrees of freedom, but it paves the way for improvements that have utilize even more degrees of freedom for reconfigurability.

The future of wireless communications will rely heavily on the ability to modify radiation beams at-will whether it is for 5G, 6G, automotive radar, space, or military applications.

If you enjoy paper review articles like these, reply to this email and let me know and I can do more of them. If you find any interesting articles that involve a clever idea or unique implementation, reply to this email and let me know. I will cover them in a future newsletter post.

### References

H. A. Jamal, C. Hu, N. Wille, K. Zeng and M. M. Tentzeris, "Beyond Planar: An Additively Manufactured, Origami-Inspired Shape-Changing, and RFIC-Based Phased Array for Near-Limitless Radiation Pattern Reconfigurability in 5G/mm-Wave Applications," in _IEEE Microwave and Wireless Technology Letters_, vol. 34, no. 6, pp. 841-844, June 2024, doi: 10.1109/LMWT.2024.3396026.

