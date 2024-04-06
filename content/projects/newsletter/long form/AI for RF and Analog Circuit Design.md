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

AI these days mostly refers to large language models (LLMs); the ability to process language input and produce human-like language output is most definitely a revolution of our times. While LLMs do have vast applications, it is not immediately apparent how this applies to electrical engineering work. We will look at one useful scenario next.
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
3. Portability of designs between technology nodes is essential for a variety of technology and business reasons. We need ways to quickly translate designs.
4. The advent of machine learning techniques and AI provides new opportunities for solving the automated analog layout problem.

In essence, we need tools to translate a design specification into schematics and layouts that meet specifications and are manufacturable, with minimal human intervention. We will look at a few such frameworks that are in existence today.
## Berkeley Analog Generator (BAG)

[Berkeley Analog Generator](https://bag3-readthedocs.readthedocs.io/en/latest/index.html) (BAG) is a [python-based framework](https://github.com/ucb-art/bag/tree/961c40e113b53fb0762e2b30c931176869b716fd) for analog and mixed-signal circuit generation. It is much more than a simple optimization tool. With just the circuit template netlist and target specifications as input, the idea is to iteratively perform parasitic-aware simulations to converge on a working schematic and layout. 

A detailed design flow looks something like this:

1. **Schematic Template**: A designer creates a circuit schematic appropriate for the design. BAG will create designs by copying and modifying this template.
2. **Parameterize**: The designer chooses the parameters in the design such as transistor dimensions as variables that need to be determined.
3. **Generators**: The designer writes a schematic generator using the BAG python API. The schematic generator will convert the template into circuit instances with various parameter combinations on the fly. The designer also writes a layout generator using two process-independent layout engines provided by BAG, called Xbase and Laygo. This produces DRC/LVS clean layouts, and parasitic extractions.
4. **Design script**: The designer writes a script to design the circuit. It involves the following steps:
	1. Obtain a good guess starting point for the design parameters. 
	2. Specify measurement parameters of the circuit (like gain and bandwidth).
	3. Evaluate the results of the schematic and layout generators. BAG will automatically setup testbenches, perform simulations and calculate circuit performance with extracted netlists. 
	4. Compare circuit specification with the simulation result, and generate new set of parameters for the generators. 
	5. Automatically iterate till the desired result is reached.

Using this method, researchers have generated the full design of a time-interleaved successive approximation analog-to-digital converter (SAR ADC) and a SerDes transceiver front-end in TSMC 16nm process, which they then proceeded to easily replicate to other process nodes from both TSMC and GlobalFoundries. Read (this paper) if you're interested in more details.
## AutoCkt

[AutoCkt](https://arxiv.org/pdf/2001.01808.pdf) takes BAG to the next level. The problem with BAG was that it needed an initial design point, and then iteratively found its way to an optimum solution. This presents two challenges:
1. Optimization methods that randomly sample an initial space do not always converge.
2. If design specification changes, the optimization needs to restart from scratch.

Instead what we want is to approach the problem like a human designer would. By intuitively understanding the design space available, we would like an algorithm to learn the trade-offs between different target specifications across the design space. 

AutoCkt does this with a reinforcement learning (RL) agent that uses a trial and error process like a human would. If there are multiple parameters to be optimized in the design, the combination of all these parameters constitutes the design space. Each set of parameters gives a simulated result, which is compared to the required specification.

The reinforcement learning process involves the following steps:
1. **Trajectory Generation**: It starts with an initial parameter set in the middle of the design space and keeps iterating till the simulated result meets the specification. The generation of one trajectory is said to be complete.
2. **RL Agent Training**: Select several randomly selected target specifications (say 50). Generate trajectories for each of these specifications. Depending on how close the final result comes to the specification, give each trajectory a score. The training ends when all 50 specifications are met based on a threshold trajectory score.

Now, if you provide a new specification not contained in the training, the RL agent knows the best trajectory closest to the specification you provided. If the trajectory is known, then you have a really good starting point for the design. As a result, you will need to iterate much lesser to get to the correct design parameter set.

Remember that by using BAG for the entire training process, you are already including the schematic and layout along with its associated parasitic extractions. As a result, the final parameter set from the RL agent will provide a value very close to the final result.

The authors of the original paper show that AutoCkt requires 10 times fewer iterations than the current best approach that uses a combination of genetic algorithms and machine learning. They show that they can generate 40 LVS passing designs for a two state OTA with negative gm load in under 3 days with a single core CPU. 

That's awesome.

##  ALIGN and MAGICAL

So far, we have simply discussed layout generation without any concern for how it is implemented. No real designer would ever like to have a "flat" layout without a hierarchy of building blocks. Its not the way things are done in the human world.

The programmatic answer to this is [ALIGN](https://arxiv.org/pdf/2008.10682.pdf) (Analog Layout, Intelligently Generated from Netlists). This is an [open-source](https://github.com/ALIGN-analoglayout/ALIGN-public) automatic layout generation flow for analog circuits which translates an input SPICE netlist to an output GDSII layout, specific to a given technology, but with an added feature.

ALIGN attempts to build IC layouts much like a human would. This involves identifying  layout hierarchies, generating layouts of the building blocks and then assembling them at each level of the layout hierarchy. For example, the lowest level of hierarchy would be an individual transistor. They are used to generate primitives such as current mirrors and differential pairs, which are then assembled into modules such as transconductance amplifiers. Using these modules, the system such as an RF transceiver is built.

Another [open source project](https://github.com/magical-eda/MAGICAL) that attempts automatic analog layout generation is [MAGICAL](https://par.nsf.gov/servlets/purl/10192511), which is described as "a human-intelligence inspired, fully- automated analog IC layout system" that is funded by the [DARPA IDEA](https://www.darpa.mil/program/intelligent-design-of-electronic-assets) program.

The overall flow is the same as ALIGN. Take an input netlist and generate an optimized layout. It also places emphasis on generating layouts hierarchically. The main differences comes from the considerations of circuit symmetry requirements that MAGICAL recognizes.

For example, MAGICAL places emphasis in making sure that differential transistors are matched by identifying transistor sources that are connected to each other to form a virtual ground, based on a process called "seed pattern detection." It also places appropriately matched passive elements. As a final step, the layout is post-processed to identify additional sources of symmetry that might have been missed in the first attempt, such as bias circuit symmetry by looking for common gate or diode connected transistors.

Publications using both these tools show that they are capable of producing designs that match in performance to a circuit designed by a human.

## In Closing

Recently, a startup company called [Astrus](https://www.future-of-computing.com/astrus-shaping-the-future-of-analog-chip-design-with-artificial-intelligence/) is looking at commercializing analog layout generation out of Toronta, Canada. Co-founded by Brad Moon and Zeyi Wang, they recently announced a $2.4M pre-seed funding round. Moon says that analog layout generation presents a very-specific, high value problem to the 60,000 or so analog designers globally. With increasing chip demand and shortage of highly skilled analog engineers, Astrus has a multi-billion dollar opportunity on their hands.

As exciting as these advancements are, machine-based designs will never completely displace analog, RF and mixed-signal design engineers. What will change is the way we will operate as designers. Instead of manually placing circuit components and drawing wires on a schematic tool, machine intelligence will help us automate away the boring parts so that we can focus on great circuit ideas instead.

If all this whole article was too much detail, just check out this video from [Jon Y](https://www.asianometry.com/) from the [Asianometry YouTube channel](https://www.youtube.com/@Asianometry) that explains why analog circuits are so hard to do, and how AI is positioning itself to help. 


PyCells https://arxiv.org/pdf/1607.00859.pdf
Learn to Design Circuits https://arxiv.org/abs/1812.02734

[[Excalidraw/AnalogDesignLoop.excalidraw|AnalogDesignLoop.excalidraw]]


B. Xu _et al._, “MAGICAL: Toward Fully Automated Analog IC Layout Leveraging Human and Machine Intelligence: Invited Paper,” in _2019 IEEE/ACM International Conference on Computer-Aided Design (ICCAD)_, Westminster, CO, USA: IEEE, Nov. 2019, pp. 1–8. doi: [10.1109/ICCAD45719.2019.8942060](https://doi.org/10.1109/ICCAD45719.2019.8942060).

E. Chang _et al._, “BAG2: A process-portable framework for generator-based AMS circuit design,” in _2018 IEEE Custom Integrated Circuits Conference (CICC)_, San Diego, CA: IEEE, Apr. 2018, pp. 1–8. doi: [10.1109/CICC.2018.8357061](https://doi.org/10.1109/CICC.2018.8357061).

K. Settaluri, A. Haj-Ali, Q. Huang, K. Hakhamaneshi, and B. Nikolic, “AutoCkt: Deep Reinforcement Learning of Analog Circuit Designs.” arXiv, Jan. 20, 2020. Accessed: Apr. 05, 2024. [Online]. Available: [http://arxiv.org/abs/2001.01808](http://arxiv.org/abs/2001.01808)

T. Dhar _et al._, “ALIGN: A System for Automating Analog Layout.” arXiv, Aug. 24, 2020. Accessed: Apr. 06, 2024. [Online]. Available: [http://arxiv.org/abs/2008.10682](http://arxiv.org/abs/2008.10682)