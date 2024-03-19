---
title: How to get design simulation right
tags: 
project: substack
date_published: 
status: 🚧
final title:
---
In the last article, we looked at the process of RFIC design from specification to tapeout. The critical phase involved the actual circuit design process. But how do we have confidence that our simulations are (a) correct (b) even remotely correlate with lab measurements.

In this article, we will look at the simulation and modeling aspect of any RF design in a bit more detail. The concepts here are not limited to integrated circuits. Instead, they apply to all of RF design. Unlike digital design, RF/analog design is still at the transistor level.

More specifically, you will learn:
- thing1
- thing2
- thing3

Let's dive in!

---

All of RF simulation and modeling relies on three key pillars.
- Passive modeling
- Active modeling
- Combining the above- also called co-simulation.
- Thermal / Electrothermal / Electromechanical

We need to be sure that each of these three aspects are done properly, correlate with the real world and is applicable over the design space required for successful design of a product. Let's look at each one.

## Passive Modeling
- Relies on the accurate definition of physical properties of materials used in the construction of the passive RF component.
- Dielectric constant, resistivity, loss tangent, surface roughness, permeability.
- Using these in an EM simulation gives the correct answer. How do we know that these values are correct?
- Calibrating an EM simulator
	- CPW measurements to extract RLGC parameters, substrate resistivity
	- Inductors to check their Q factor accuracy
	- The EM settings chosen also play an important role.
	- Test vehicles with passive structures are manufactured, and EM simulation is run to verify that it is accurate. If not adjustments are made.
	- Boundary conditions that are used, and how far away from the circuit

## Active Modeling
- Traditional device modeling requires the proper fitting of a device model to measured data.
- Depending on the device, there are different models that can be applied. Can I put a table of these?
- The model consists of a bunch of equations written in verilogA or C-code, the co-efficients of the equations are the model parameters that need to be fitted.
- The model for the device is provided by the foundry typically.
- Designer should always be sus about its accuracy because it is general purpose, and intended to fit every application. It may not be most accurate around your region of operation.
- When predictions of distortion are required, derivatives also need fitting, and it is unlikely that the model fits this out of the box.
- Often, companies have teams of people who optimize models based on internal circuit know how for highly accurate RF design.

## Co-simulation

- Active model needs to be combined with passive model because there are always routing parasitics. 
- EM is the most accurate approach to getting passive model performance.
- Its not always most practical. Sometimes we need to use parasitic extraction when it is needed for a large number of transistor devices.
- Choosing the right interface between active and passive device is critical to avoid missing anything or double counting it.
- Active device cannot be EM simulated, so we will need ports for it so that acrtive device model can be plugged in later.
## Package/EVB Co-simulation

- If designers stop simulating at the periphery of the chip, that would be a big mistake. The impact of the package on the IC needs to be considered.
- There is a lot of ambiguity as to what constitutes a good ground reerence for ports on the chip/
- The EVB needs to be simulated in EM too, to ensure that all the transitions are captured. This gets critical the higher the frequency of operratiom/
- 


## Device Models, Parasitic Extraction and Electromagnetics
- Device models - a primer. What they are. What they're not. How much to believe them.
- What is parasitic extraction and why do we need it.
- How do device models interact with parasitic extraction
- Why EM is required? Where do you get the process stackup?
- What is the best EM tool? 
- Correlating EM tool accuracy



## Packaging, Board Evaluation and Testing
- Impact of packaging on the IC design
- Introduction of new ground planes and coupling paths
- Impedance control and good ground plane access on the EVB
- Testing a chip for all its specs - across voltages, temperatures and multiple samples.
- Generating the data sheet in collaboration with marketing.
- Providing samples to customers

## Iterations
- Few ICs work straight out of the gate. 
- Always correlate your measurements with simulation. this takes extra work but its worth it.
- There will be some spec not being met, or something the customer doesnt like
- Do a tapeout revision-- if you can use the spares to reconfigure the circuit, you can only do a metal mask spin. otherwise you have to do an all-layer change -- more $

## Productization
- what is involved here.