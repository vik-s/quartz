---
title: AI for RF and Analog Design
tags:
  - systems
project: substack
date_published: 
status: 🚧
final title:
---
Historically, RF and analog circuit design has been an entirely manual process. It still is, compared to how much automation is possible in the digital world. A lot of the experience to do analog engineering comes from simply *doing* the engineering over and over. With time, we develop a "feel" for things and know what worked and what didn't from past experience. This intuition is the currency with which we build our engineering careers. We take pride in our intuition being irreplaceable. But is it?

The age of AI is upon us. The internet is rife with people and businesses trying to harness the power of AI to usher us into a new technological era. To what extent does AI possess the power of our intuition? What is it capable of?

What is generally referred to as AI these days are mostly large language models (LLMs). The ability to process language input and produce human-like language output, and have the technology available to the masses is most definitely a revolution of our times. While LLMs do have vast applications, it is not immediately apparent how this applies to electrical engineering work.

Aside from the race to implement silicon for large language models, the excitement for engineering work comes from the generative nature of AI. The prospect of simply "asking" the AI to design an electronic circuit and have it generate a fully working design far more optimized than any human is capable of, is undeniably attractive. The ability of image generation using tools like DALLE, Midjourney and Stable Diffusion, and video generation using Sora, encourages us to imagine that we can generate chip layouts the same way. With sufficient hardware resources, years of human effort would be replaced by hours of machine resources. That's the utopian dream anyway.

Some futurists in the industry believe this is genuinely going to happen down the line.  At that point, the need for hardware engineers will evolve to become something that involves interacting with the AI instead of actually doing the engineering work. We are nowhere near that capability. For now.

For engineering work, optimization algorithms, machine learning techniques and neural networks have been the bread and butter for minimizing the number of human design iterations. The advent of LLMs has stirred up a new flurry of activity and interest in these areas under the moniker of AI. Corporate departments grow their budgetary resources using the term AI, publications about AI have more readership, and EDA companies eagerly introduce AI capabilities within their tools. Everyone is looking for a piece of the AI pie.

In the rest of this article, we will look at ways engineers have tried to minimize human intervention in RF/analog design. My preference lies in identifying the underlying algorithm, since AI in electrical engineering at this point has become a catch-all term. We will focus instead on how capable machines have been in generating faster or better performing RF/analog designs than their human counterparts would.

## Use in layout generation

While digital layout today is done using place and route, analog/RF layout is done manually by layout engineers making it a time consuming process which involves highly skilled engineers. The complexity of layout involved is much higher to ensure layout symmetry, minimize losses and dispersion, and account for coupling effects and parasitics. 

In the past, there have been several attempts to automate analog layout generation, but none of them have really caught on in the design industry. There are three major reasons why automated analog layout is relevant today:
1. Modern technologies like FinFET have highly restrictive design rules, which reduces the overall design space to be explored for layout generation.
2. There need for analog content is increasing and design iterations need to be minimized.
3. Advent of machine learning techniques provides new opportunities for solving the automated analog layout problem.

The latest approach to doing this is called [ALIGN](https://arxiv.org/pdf/2008.10682.pdf) (Analog Layout, Intelligently Generated from Netlists). This is an [open-source](https://github.com/ALIGN-analoglayout/ALIGN-public) automatic layout generation flow for analog circuits which translates an input SPICE netlist to an output GDSII layout, specific to a given technology. 

ALIGN attempts to build IC layouts much like a human would. This involves identifying  layout hierarchies, generating layouts of the building blocks and then assembling them at each level of the layout hierarchy. For example, the lowest level of hierarchy would be an individual transistor. They are used to generate primitives such as current mirrors and differential pairs, which are then assembled into modules such as transconductance amplifiers. Using these modules, the system such as an RF transceiver is built.

Another [open source project](https://github.com/magical-eda/MAGICAL) that attempts automatic analog layout generation is [MAGICAL](https://github.com/magical-eda/MAGICAL), which is described as "a human-intelligence inspired, fully- automated analog IC layout system" that is funded by the [DARPA IDEA](https://www.darpa.mil/program/intelligent-design-of-electronic-assets) program 

The overall flow is the same as ALIGN. Take an input netlist and generate an optimized layout. Interestingly, MAGICAL places emphasis in making sure that differential transistors are matched by identifying transistor sources that are connected to each other to form a virtual ground. The overall routing and placement is done based on a variety of optimization algorithms.

Recently, a startup company called [Astrus](https://www.future-of-computing.com/astrus-shaping-the-future-of-analog-chip-design-with-artificial-intelligence/) is looking at commercializing analog layout generation out of Toronta, Canada. Co-founded by Brad Moon and Zeyi Wang, they recently announced a $2.4M pre-seed funding round. Moon says that analog layout generation presents a very-specific, high value problem to the 60,000 or so analog designers globally. With increasing chip demand and shortage of highly skilled analog engineers, Astrus has a multi-billion dollar opportunity on their hands.

## Use in circuit design 

It’s not just analog layout that is an issue. Choosing optimal component values for an analog circuit is equally complicated and time consuming. Often, the design process heavily relies on the experience of the designer, and the number of possible iterations by a human is always limited. **What if we can feed human intuition to a machine learning algorithm that can generate optimal designs?**

A 2020 paper from UC Berkeley describes a deep-learning based automated analog circuit designer called [AutoCkt](https://arxiv.org/pdf/2001.01808.pdf). The paper claims that the algorithm intuitively understands the design space much like a human designer would, and converges on a working solution 40X faster than a genetic algorithm optimization. It uses [Berkeley Analog Generator](https://bag3-readthedocs.readthedocs.io/en/latest/index.html), a tool that simulates a circuit with layout parasitics, to design forty two-stage operational transconductance amplifiers (OTAs) that meet specification and pass [LVS](https://www.viksnewsletter.com/p/a-beginners-guide-to-the-process?r=222kot&utm_campaign=post&utm_medium=web) using a single-core CPU in under three days. Not bad.
- [BLADES](https://ieeexplore.ieee.org/abstract/document/31523):
## Use in Electromagnetics

Another time consuming aspect of RF design involves the creation of optimum passive structures using electromagnetic simulation. We often look at matching circuits in a classical sense - a series inductor with a shunt capacitor, for example to convert the impedances from source to load. But what if these predetermined metal shapes or matching topologies are not the optimal answer? 

As Prof. Kaushik Sengupta says in [a paper](https://ieeexplore.ieee.org/abstract/document/10136184/references#references) (IEEE paywall) published in the Journal of Solid State Circuits,

> In the space of all possible manufacturable EM structures, there is no reason to believe that these (and therefore, the co-designed circuits) will be close to being “globally” optimal.

Prof. Sengupta and his team show that you can use deep convolutional neural networks to synthesize an arbitrary metal shape that provides the appropriate transformation of impedances. In [this paper](https://www.researchgate.net/profile/Zheng-Liu-108/publication/360427205_Deep_Learning-Enabled_Inverse_Design_of_30-94_GHz_P_sat3_dB_SiGe_PA_Supporting_Concurrent_Multiband_Operation_at_Multi-Gbs/links/62758ee6973bbb29cc67bce5/Deep-Learning-Enabled-Inverse-Design-of-30-94-GHz-P-sat-3-dB-SiGe-PA-Supporting-Concurrent-Multiband-Operation-at-Multi-Gb-s.pdf), an arbitrary metal shape serves as the output matching network for a millimeter-wave PA, and works as intended.

The ultimate RF/analog dream would be to utilize generative AI to completely synthesize a design from just specifications to a fully working, optimal design whose performance is unmatched by human iteratively running design simulations. Maybe we will get there at some point.

## Use in device modeling

## Use in wireless communications


- Applications of ML and ANN in device modeling
- Learning to design circuits 
- Automating placement of circuits for floorplanning
- Automatic inductor model extraction with ANN
- Design of PA output matching network with inverse design

https://www.doe.carleton.ca/~qjz/announcement.html

This video from [Jon Y](https://www.asianometry.com/) from the [Asianometry YouTube channel](https://www.youtube.com/@Asianometry) explains why analog circuits are so hard to do, and how AI is positioning itself to help. 