---
title: How transistor models are developed
tags:
  - device
project: substack
date_published: 
status: 🚧
final title:
---
Transistor models are fundamental for integrated circuit design. These models emulate the physical behavior of a transistor in a circuit simulator. By using combinations of transistors and their underlying models with other components such as diodes and passive components, the circuit is designed to perform a specific function and meet desired specifications. 

In this article, we will look at how transistor models are developed, and how they operate in a simulator. Specifically you will learn about:
- thing1
- thing2
- thing3

Let's dive in.

--
## Compact Models

The industry term for the representation of a transistor in a simulator is called a Compact Model. The term 'compact' stems from the requirement that the model needs to be simple enough to be computationally efficient while still being accurate. It is essentially a 'black box' model of transistor operation where equations are used to represent the behavior of the device at its terminals. It tells us little of what actually happens inside the transistor even if the model is designed to mimic real world physics, as long as its terminal behavior is correct.

What actually happens inside a transistor depends on the process steps used to build it. It is costly to iterate on process steps required to build an optimal transistor by manufacturing them on silicon. Instead, Technology Computer-Aided Design (TCAD) tools (https://semiengineering.com/what-is-tcad-and-why-it-is-essential-for-the-semiconductor-industry/) provide a way to simulate the behavior of a transistor for a given sequence of processing steps. TCAD tools serve three functions:
1. Process: Mimic fabrication steps to build a transistor
2. Device: Simulate electrical current flow through a given transistor construction
3. Interconnect: Simulate metal connections in a transistor

With these TCAD tools, it is possible to obtain an estimate of currents at the transistor's terminals when a certain sequence of semiconductor processing steps are performed. Using these tools, semiconductor device engineers define the transistor construction so that it meets expected performance. Often, the results from TCAD simulation serves as a starting point for the design of a preliminary compact model.

Compact models are usually written in Verilog-A or C, and are comprised of closed form equations that analytically describe the physics of a transistor as a function of terminal voltages or currents, device size, temperature and variability. These equations are implemented by an industry standard simulator such as Cadence Spectre, to solve the node voltages and currents across every device in the circuit. 

The numerical behavior of these equations is important for achieving convergence during circuit simulation. They need to be both continuous and differentiable to lower computation time. The iterative process of solving for node voltages and currents often results in abnormal intermediate values for which the model equations should be well behaved to converge on a final solution.

The process of fitting a model to an actual transistor involves finding the values of constants in the analytical equations within the compact model. These constants, called model parameters, are usually defined in a text file called the model card and are derived from measurements of individual transistors. Each model has a suggested parameter extraction strategy to methodically extract the model parameters for a given transistor.

Put *picture of drain current equation*

## Types of Transistor Models

One of the most popular device models for MOS transistors is the Berkeley Short-Channel IGFET{fn} Model (BSIM) developed by a team of researchers at the University of California, Berkeley. The first version introduced in the late 1980s [1] was a rather rudimentary version with only 17 model parameters. 

Since then, the complexity of the model has significantly increased as silicon MOS technology has progressed into more advanced technology nodes. MOS transistors stray away from classical modes of operation as the gate length shrinks, thus requiring more sophisticated models to capture these effects properly. The result is that a compact model requires more parameters that needs to be fit to accurately represent the transistor. For example, *put BSIM4 example *

BSIM alone comes in a variety of other flavors depending on the nature of the transistor. BSIM-IMG (Independent Multi-Gate) is useful for fully-depleted MOSFETs which usually have a thin silicon film with a doping low enough to deplete fully during transistor operation. The conducting channel for such a transistor can be independently controlled on both the top and bottom, requiring independent control of gates.

the BSIM-CMG (Common Multi-Gate) model commonly used for FinFET applications has over **400** (<--) model parameters that require fitting to capture transistor operation accurately.

For silicon-on-insulator devices, BSIMSOI



https://home.iitk.ac.in/~chauhan/ESSDERC2012_YSChauhan.pdf

Put *picture of evolution of BSIM*


