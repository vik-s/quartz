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

The industry term for the representation of a transistor in a simulator is called a Compact Model. The term 'compact' stems from the requirement that the model needs to be small enough to be computationally efficient while still being accurate. It is essentially a 'black box' model of transistor operation where equations are used to represent the behavior of the device at its terminals. It tells us little of what actually happens inside the transistor even if the model is designed to mimic real world physics, as long as its terminal behavior is correct.

What actually happens inside a transistor depends on the process steps used to build it. It is costly to iterate process steps required to build an optimal transistor by manufacturing them on silicon. Instead, Technology Computer-Aided Design (TCAD) tools (https://semiengineering.com/what-is-tcad-and-why-it-is-essential-for-the-semiconductor-industry/) provide a way to simulate the behavior of a transistor for a given sequence of processing steps. TCAD tools serve three functions:
1. Process: Mimic fabrication steps to build a transistor
2. Device: Simulate electrical current flow through a given transistor construction
3. Interconnect: Simulate physical connections in a transistor

With these TCAD tools, it is possible to obtain an approximate estimate of currents at the transistors terminals when a certain sequence of semiconductor processing steps are performed. Using these tools, device engineers often design the transistor construction so that it meets expected performance. Often, the results from TCAD simulation serves as a starting point for the design of a preliminary compact model.

Compact models are usually written in Verilog-A or C, and are comprised of closed form equations that analytically describe the physics of a transistor as a function of terminal voltages or currents, device size, temperature and variability. These equations are implemented by an industry standard simulator such as Cadence's Spectre, to solve the node voltages and currents across every device in the circuit. 

The numeric behavior of these equations is important for achieving convergence during circuit simulation. The iterative process of solving for node voltages and currents often results in abnormal intermediate values for which the model equations should be well behaved to converge on a final solution.

## Who makes these models?

One of the most popular device models for MOS transistors is the Berkeley Short-Channel IGFET Model (BSIM) developed by a team of researchers at the University of California, Berkeley.