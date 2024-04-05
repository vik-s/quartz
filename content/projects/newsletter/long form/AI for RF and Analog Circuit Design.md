---
title: AI for RF and Analog Circuit Design
tags:
  - systems
project: substack
date_published: 
status: 🚧
final title:
---
RF and analog circuit design is an entirely manual process. The process of engineering relies on developing a "feel" for things by doing it over and over, by learning what works and what does not. This intuition is the currency with which we build our engineering careers. We take pride in our intuition being irreplaceable. But is it?

The age of AI is upon us. The internet is rife with people and businesses trying to harness the power of AI to usher us into a new technological era. But to what extent does AI possess the power of our intuition?

AI these days mostly refers to large language models (LLMs); the ability to process language input and produce human-like language output is most definitely a revolution of our times. While LLMs do have vast applications, it is not immediately apparent how this applies to electrical engineering work. Here's one scenario.

## Automatic Design Generation

Aside from the race to implement silicon for LLMs, the excitement for engineering work comes from the generative nature of AI. **The prospect of simply "asking" the AI to design an electronic circuit and have it generate a fully working design that is more optimized than any human is capable of, is undeniably attractive.** The ability to generate images using tools like DALL-E, Midjourney and Stable Diffusion, and video using Sora, leads us to imagine that we can generate chip layouts the same way. With sufficient resources, years of error prone human effort would be replaced by hours of reproducible machine design. That's the utopian dream anyway.

For engineering work, optimization algorithms, machine learning techniques and neural networks have been the bread and butter for intelligent, automated design. The advent of LLMs has stirred up a new flurry of interest in these areas under the moniker of AI. The recent AI gold rush leads corporations to devote more resources to it, publications on AI to have more readership and EDA companies to claim their tools are assisted by AI. Everyone is looking for a piece of the AI pie.

In the midst of the AI chaos we find ourselves in, what specific machine-centric approaches are available to analog, mixed-signal and RF engineers? What problem are they looking to solve?
## The Problem of Analog Design

While digital layout today is done using place and route, analog/RF layout is done manually by layout engineers making it a time consuming process which involves highly skilled engineers. The complexity of layout involved is much higher to ensure layout symmetry, minimize losses and dispersion, and account for coupling effects and parasitics. 

The fact that layout parasitics greatly affect the design implies that the schematic component values need redesign once they are taken into account. This iterative loop of schematic design, parasitic extraction and performance evaluation constitutes a large, time-consuming portion of the design process.

Past attempts to automate analog layout generation have not always stuck in industry. EDA giants like Cadence Design Systems and Synopsis have provided tools for automated layout generation from schematics. The results, however, do not always appeal to the "aesthetic" of the experienced circuit designer. It is the underlying belief (and probably rightly so), that aesthetic designs are robust to layout effects which are not often modeled precisely.

 There are several reasons why automated analog layout has greater relevance today than ever before:
1. Modern technologies like FinFET have highly restrictive design rules, which: 
	1. makes it hard to generate designs manually
	2. reduces the overall design space to be explored for layout generation.
2. There need for analog content is increasing, experienced designers are in short supply, and design cycle times are shrinking while specifications are getting more challenging.
3. Portability of designs between technology nodes is essential for a variety of technology and business reasons. We need ways to quickly translating designs.
4. The advent of machine learning techniques and AI provides new opportunities for solving the automated analog layout problem.

In essence, we need tools that translate a design specification into schematics and layouts that are DRC and LVS clean, with minimal human intervention. We will look at a few such frameworks that are in existence today.
## ## Berkeley Analog Generator (BAG)

Berkeley Analog Generator is a 

[Berkeley Analog Generator](https://bag3-readthedocs.readthedocs.io/en/latest/index.html)
https://github.com/ucb-art/bag/tree/961c40e113b53fb0762e2b30c931176869b716fd

## MAGICAL and ALIGN



The latest approach to doing this is called [ALIGN](https://arxiv.org/pdf/2008.10682.pdf) (Analog Layout, Intelligently Generated from Netlists). This is an [open-source](https://github.com/ALIGN-analoglayout/ALIGN-public) automatic layout generation flow for analog circuits which translates an input SPICE netlist to an output GDSII layout, specific to a given technology. 

ALIGN attempts to build IC layouts much like a human would. This involves identifying  layout hierarchies, generating layouts of the building blocks and then assembling them at each level of the layout hierarchy. For example, the lowest level of hierarchy would be an individual transistor. They are used to generate primitives such as current mirrors and differential pairs, which are then assembled into modules such as transconductance amplifiers. Using these modules, the system such as an RF transceiver is built.

Another [open source project](https://github.com/magical-eda/MAGICAL) that attempts automatic analog layout generation is [MAGICAL](https://github.com/magical-eda/MAGICAL), which is described as "a human-intelligence inspired, fully- automated analog IC layout system" that is funded by the [DARPA IDEA](https://www.darpa.mil/program/intelligent-design-of-electronic-assets) program.

The overall flow is the same as ALIGN. Take an input netlist and generate an optimized layout. Interestingly, MAGICAL places emphasis in making sure that differential transistors are matched by identifying transistor sources that are connected to each other to form a virtual ground. The overall routing and placement is done based on a variety of optimization algorithms.

Publications using both these tools show that they are capable of producing designs that match in performance to a circuit designed by a human. This area of electronic tool development is certainly worth pursuing especially if it helps reduce design cycle times.

## AutoCkt

To translate a circuit specification into a working design layout, the circuit design phase needs to be automated as well, and not just layout generation from an optimized netlist. This is a much more complex problem that simply parametrizing a circuit netlist and throwing an optimizer at it. If you've ever tried this, you know it does not work. 

There are several reasons for this:
1. Pure optimization methods that randomly sample an initial space do not converge on many occasions.
2. If design specification changes, the optimization needs to restart from scratch.
3. Most approaches do not consider layout parasitics, which when included, can completely change the optimal design for analog circuits.

[AutoCkt](https://arxiv.org/pdf/2001.01808.pdf)

## Today and the Future


Recently, a startup company called [Astrus](https://www.future-of-computing.com/astrus-shaping-the-future-of-analog-chip-design-with-artificial-intelligence/) is looking at commercializing analog layout generation out of Toronta, Canada. Co-founded by Brad Moon and Zeyi Wang, they recently announced a $2.4M pre-seed funding round. Moon says that analog layout generation presents a very-specific, high value problem to the 60,000 or so analog designers globally. With increasing chip demand and shortage of highly skilled analog engineers, Astrus has a multi-billion dollar opportunity on their hands.



This video from [Jon Y](https://www.asianometry.com/) from the [Asianometry YouTube channel](https://www.youtube.com/@Asianometry) explains why analog circuits are so hard to do, and how AI is positioning itself to help. 

PyCells https://arxiv.org/pdf/1607.00859.pdf

