---
title: Origami-inspired RF
tags:
  - misc_letters
project: substack
date_published: 
status: 
final title:
---
It's been a whole month that we have been going hard on RF power amplifier classes. Not sure if you've had enough yet, but my ability to write about power amplifiers is running a bit saturated (pun intended.) If you enjoyed the series, or want more articles, reply to this email and let me know.

If you missed the series on basic power amplifier classes, here are the articles you can check out.
- links

To freshen things up a bit, I decided to look up latest research from the 2024 International Microwave Symposium, the premier conference in the field of RF and Microwave engineering. What I found was an idea so interesting that I felt compelled to write about it. 

As it turns out, there is a new class of RF circuits that draw inspiration from Origami, the Japanese (add a footnote that it actually got popular in Japan but nobody really knows who started it) art of paper folding. Just like you can make different shapes out of paper, you can physically reconfigure circuits to operate differently.

[Hani Al Jamal](https://www.linkedin.com/in/hani-aljamal/), a PhD student, and a team of researchers led by Prof. Manos Tentzeris at Georgia Tech, authored a paper titled [Beyond Planar: An Additively Manufactured, Origami-Inspired Shape-Changing, and RFIC-Based Phased Array for Near-Limitless Radiation Pattern Reconfigurability in 5G/mm-Wave Applications](https://ieeexplore.ieee.org/abstract/document/10531260), which won the [Best Paper Award](https://ece.gatech.edu/news/2024/06/al-jamal-wins-best-paper-award-2024-ieee-international-microwave-symposium) at the 2024 International Microwave Symposium.

This paper describes **a phased array antenna from which you can synthesize any radiation pattern**. It uses both electronic and physical modifications to achieve this. In this post, we will get into the details of exactly how this works.

Special thanks to Hani for providing additional information, pictures and review a draft of this post.

Here is a brief outline of the content:
- thing1
- thing2
- thing3

**Read time**: X mins

~~
### The Need for Adaptive RF Circuits
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

1. **360° Azimuth Coverage**: In its pyramidal orientation, turn on only one phased array and steer the beam to its maximum value, at which point turn on the phased array on the next face. This ensures a continuous handoff between different phased array on the faces, and provides 360° azimuth beam steering.
2. **Bending along an axis**: Fold the array along any one axis, and as the fold angle decreases, the radiation pattern reconfigures from a four-beam pattern to a two-beam pattern as shown in the figure.
3. **Arbitrary shaped beams**: Fold the array across either axes by an arbitrary angle, turn on anywhere between a single phased array to all four phased arrays, provide digital weights to the phased array to control both amplitude and phase to antenna elements (even do [gain tapering](https://www.viksnewsletter.com/i/140865578/gain-tapering) to control grating lobes), and then you can virtually synthesize any radiation pattern you want.

### Foldable Hinge Interconnects














~~

If you find any other interesting articles on this topic, reply to this email and let me know, I will cover them in a future article.

Also, if you enjoy paper review articles like these, reply to this email and let me know and I can do more of them.


I may have to look up and write about this.

Origami tessellations, notably the miura-ori [1] and the “eggbox” [2], have found applications in frequency-selective surfaces (FSS), showcasing spatial frequency reconfigurability.

### From Hani Al Jamal

**Novelty of work:**

The proposed work therein presents several novelties. First, the combination of mechanical and electrical reconfigurability enables continuous $360^{\circ}$ beamsteering through 2 degrees-of-freedom (2-DOF) resulting in virtually infinite radiation pattern reconfigurability capabilities. Second, the multi-faceted 3-dimensional nature of the phased array leads to highly reconfigurable multi-beam directional or quasi-isotropic patterns. Third, the proposed origami-inspired phased array is fully-contained with on-structure beamforming RFICs and a flexible feeding network that utilizes the first additively manufactured foldable hinge interconnect (arch interconnect) exhibiting near-constant insertion loss across folding angles and cycles. The result of this is a lightweight prototype with a small formfactor. Fourthly, a modular tile-based approach is employed; realizing the proposed eggbox origami phased array through scalable unit-cells. This not only allows for scalability, but also reduces costs in case of failure, as unit-cells can be individually replaced. In addition, a modular tile-based approach allows for the selective activation of specific unit-cells of eggbox faces based on desired patterns, TX/RX modes, and/or power consumption requirements. Finally, the use of additive manufacturing techniques leads to reduced waste, faster fabrication, and lower costs.

**Applications:** 

The eggbox phased array offers versatile application scenarios across various domains. Firstly, it enables multi-mode in-band full-duplex applications by selectively or simultaneously activating different faces or unit cells as transmitters (TX) or receivers (RX). This capability allows the array to function as an active transmit-receive relay system, where a signal is received from one side and transmitted in another direction, enhancing communication efficiency and reliability. Secondly, its multifunctionality is exemplified by its multi-beam capability, which is invaluable for autonomous vehicles. Different beams can be allocated for specific tasks such as communication, obstacle detection, and navigation, or in military applications where beams are used for jamming, radar, and communication, ensuring comprehensive situational awareness and operational effectiveness. Thirdly, the eggbox phased array can be deployed in search and rescue operations, particularly when mounted on an aircraft. Its geometric configuration addresses the tradeoff between gain and angular coverage; when unfolded, it provides wide angular coverage for rapid search operations, and can then be folded to offer narrow beams with high gain for precise localization. Lastly, its ability to be easily folded and deployed is crucial for space-constrained environments, such as space applications, where compactness and efficient deployment are essential. This adaptability presents the eggbox phased array as versatile and impactful with broad applicability.

  

**Kindly make sure to cite the paper:**

H. A. Jamal, C. Hu, N. Wille, K. Zeng and M. M. Tentzeris, "Beyond Planar: An Additively Manufactured, Origami-Inspired Shape-Changing, and RFIC-Based Phased Array for Near-Limitless Radiation Pattern Reconfigurability in 5G/mm-Wave Applications," in _IEEE Microwave and Wireless Technology Letters_, vol. 34, no. 6, pp. 841-844, June 2024, doi: 10.1109/LMWT.2024.3396026.

