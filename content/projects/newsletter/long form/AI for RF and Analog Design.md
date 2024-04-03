---
title: AI for RF and Analog Design
tags:
  - systems
project: substack
date_published: 
status: 🚧
final title:
---
The age of AI is upon us. The internet is rife with people and businesses trying to harness the power of AI to usher us into a new technological era. But what does it mean for Analog/RF design?

This video from [Jon Y](https://www.asianometry.com/) from the [Asianometry YouTube channel](https://www.youtube.com/@Asianometry) explains why analog circuits are so hard to do, and how AI is positioning itself to help. 

While digital layout today is entirely automated, analog/RF layout is done manually by layout engineers. This is a time consuming and error prone process and the experience level of the engineer plays a major role in getting these layouts right. 

There have been several attempts to automate analog layout generation, but none have stuck in the industry. Many projects with clever abbreviations like [ALIGN](https://arxiv.org/pdf/2008.10682.pdf), [BLADES](https://ieeexplore.ieee.org/abstract/document/31523) and [MAGICAL](https://github.com/magical-eda/MAGICAL) have been reported, and there is even an AI startup called [Astrus](https://www.future-of-computing.com/astrus-shaping-the-future-of-analog-chip-design-with-artificial-intelligence/) looking to solve the problem of automated analog layout. 

It’s not just analog layout that is an issue. Choosing optimal component values for an analog circuit is equally complicated and time consuming. Often, the design process heavily relies on the experience of the designer, and the number of possible iterations by a human is always limited. **What if we can feed human intuition to a machine learning algorithm that can generate optimal designs?**

A 2020 paper from UC Berkeley describes a deep-learning based automated analog circuit designer called [AutoCkt](https://arxiv.org/pdf/2001.01808.pdf). The paper claims that the algorithm intuitively understands the design space much like a human designer would, and converges on a working solution 40X faster than a genetic algorithm optimization. It uses [Berkeley Analog Generator](https://bag3-readthedocs.readthedocs.io/en/latest/index.html), a tool that simulates a circuit with layout parasitics, to design forty two-stage operational transconductance amplifiers (OTAs) that meet specification and pass [LVS](https://www.viksnewsletter.com/p/a-beginners-guide-to-the-process?r=222kot&utm_campaign=post&utm_medium=web) using a single-core CPU in under three days. Not bad.

Another time consuming aspect of RF design involves the creation of optimum passive structures using electromagnetic simulation. We often look at matching circuits in a classical sense - a series inductor with a shunt capacitor, for example to convert the impedances from source to load. But what if these predetermined metal shapes or matching topologies are not the optimal answer? 

As Prof. Kaushik Sengupta says in [a paper](https://ieeexplore.ieee.org/abstract/document/10136184/references#references) (IEEE paywall) published in the Journal of Solid State Circuits,

> In the space of all possible manufacturable EM structures, there is no reason to believe that these (and therefore, the co-designed circuits) will be close to being “globally” optimal.

Prof. Sengupta and his team show that you can use deep convolutional neural networks to synthesize an arbitrary metal shape that provides the appropriate transformation of impedances. In [this paper](https://www.researchgate.net/profile/Zheng-Liu-108/publication/360427205_Deep_Learning-Enabled_Inverse_Design_of_30-94_GHz_P_sat3_dB_SiGe_PA_Supporting_Concurrent_Multiband_Operation_at_Multi-Gbs/links/62758ee6973bbb29cc67bce5/Deep-Learning-Enabled-Inverse-Design-of-30-94-GHz-P-sat-3-dB-SiGe-PA-Supporting-Concurrent-Multiband-Operation-at-Multi-Gb-s.pdf), an arbitrary metal shape serves as the output matching network for a millimeter-wave PA, and works as intended.

The ultimate RF/analog dream would be to utilize generative AI to completely synthesize a design from just specifications to a fully working, optimal design whose performance is unmatched by human iteratively running design simulations. Maybe we will get there at some point.

- Applications of ML and ANN in device modeling
- Learning to design circuits 
- Automating placement of circuits for floorplanning
- Automatic inductor model extraction with ANN
- Design of PA output matching network with inverse design

https://www.doe.carleton.ca/~qjz/announcement.html