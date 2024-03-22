---
title: How to get design simulation right
tags: 
project: substack
date_published: 
status: 🚧
final title:
---
In the last article, we looked at the process of RFIC design from specification to tapeout. The chip design process does not end there. It has only begun. In this article, we will fill in the dots about the design process and look at some post processing steps.

In this article, we will look at the simulation and modeling aspect of any RF design in a bit more detail. The concepts here are not limited to integrated circuits. Instead, they apply to all of RF design. Unlike digital design, RF/analog design is still at the transistor level.

More specifically, you will learn:
- thing1
- thing2
- thing3

Let's dive in!

---

When we spoke of the design process last time, we quickly skipped over the details of the actual design phase and over one important question. How do we trust that our simulations correlate with the real world? The answer lies in the accurate modeling of the chip using EDA tools. All of RF simulation and modeling relies on a few key concepts, and if done right, is capable of predicting the performance of a chip design in the real world.
- Passive modeling
- Active modeling
- Combining the above- also called co-simulation.
- Thermal / Electrothermal / Electromechanical

Let's look at each one.

## Passive Modeling

In the RF world, anything passive refers to components not involving amplifying devices of any sort. Examples include inductors, capacitors, transmission lines, wirebonds, antennas, and filters. They primarily consist of arbitrary configurations of metals and dielectrics in three dimensional space.

For the most part, the response of these 3D structures to a radio frequency input is predicted with the help of electromagnetic (EM) simulators. These tools are highly capable of producing accurate predictions by numerically solving Maxwell's equations but require the following to be properly defined:
1. **Material properties of metals and dielectrics**: Permittivity, loss tangent, resistivity, surface roughness and permeability information determine how electromagnetic fields will interact with structures that use these materials.
2. **Boundary conditions**: Defines the state of the electromagnetic field at the boundaries of the simulation space, and defines appropriate signal excitations along the 3D structure being simulated.

Fortunately, the material properties of commonly used materials are well known, and is available as a database in most EM simulators. The definition of boundary conditions is in the control of the engineer and should be implemented with care.

Before inherently trusting the results of an EM simulators, design teams prefer to undertake a one-time activity to *calibrate* the EM simulator. In this context, calibration means that you verify that the material values, discretization setting and boundary conditions used to accurately predict hardware measurements in the laboratory. In addition, all EM simulators have a setting that allows you to control the extent to which the problem is discretized via a mesh. Finding the correct extent for both good accuracy and reasonable simulation time is important.

The exact verification process can vary depending on what RF product is being designed, and what the EM simulator is being calibrated for. In the context of RFIC design, here are some common ways to calibrate an EM simulator.

1. **Transmission lines**: Coplanar waveguides are easy to implement on-wafer and measure using probes. From measured s-parameters, extract RLGC parameters, and compare with RLGC parameters extracted from the simulation of the line.
2. **Inductors**: Spiral inductors of different shapes and values are helpful to validate the material parameters used for simulation. The primary intent is to get simulated inductance, quality factor and self-resonance frequency to line up with measurement.
3. **Capacitors**: Simulating on-wafer metal-insulator-metal (MIM) or metal-oxide-metal (MOM) capacitors (plate or interdigitated) are helpful in extracting dielectric constants on wafer. The capacitance and Q-factor of the capacitor from simulation is expected to align with measurements.
4. **Resonators**: Resonators are helpful since they combine inductors and capacitors. The resonant frequency is usually set high enough so that small parasitics from routing start to matter. If EM simulations can capture the right resonant frequency, you are including all the parasitics properly and the simulation can be trusted.

With enough rigor, any EM simulator can be verified to a high degree of certainty regarding the accuracy of its results. When amplifying devices get involved, things get complicated.
## Active Modeling

### What do these models look like?

The electrical model of an amplifying device such as a MOSFET or Bipolar transistor is quite a lot more complicated than the small signal model of a MOSFET often shown in textbooks. The simple model does not account for all the physics of a transistor, will not scale properly with device sizing or support advanced nonlinear simulations.

"Real" device models consist of extensive equations written in Verilog-A or C that are implemented as a model framework. The equations are based on the analytical equations for currents and charge storage, and are designed to exhibit a lot of the physics the actual transistor does. Charge transport in modern devices are however so complicated that there are usually substantial number of "fitting factors" used to account for various effects.

These models are usually provided by the foundry who employ a team of device modeling engineers to extract these models. The role of the device modeling engineer is to find the values of the coefficients of the equations so that the model predicts the current and charge dependence on voltage, temperature and frequency. Usually extensive device level measurements are required for fitting of device models.

The BSIM family of models are the industry standard for MOSFETs and have over 300 parameters that must be chosen to accurately predict various operating regions and effects that occur in a transistor. The HiCUM model for BJTs have over 200 parameters.

### How are these models validated?

They often are not, or only validated to a limited extent. Design teams often place inherent trust that the model is correct because it takes a lot of transistor-level measurements to verify that this is sufficiently accurate. Some companies may have enough means to fund a small team of device modeling experts who will place transistors on test vehicles, measure them and validate them against the foundry model. They will also adjust the model internally if needs be.

In my opinion, the real way to validate the accuracy of a model is to build reference designs like an amplifier on a test vehicle, and check if the model predicts the DC, s-parameter and nonlinear performance of the reference amplifier. The reference amplifier can be designed for low current mobile applications or high current infrastructure applications, or anything in between.

I have personally done a lot of this, and the accuracy with which device models can predict these "real" circuits is often of great interest to an RFIC designer. This quantitatively identifies shortcomings of a device model, especially on aspects like nonlinearity which are hard to tell from purely device-level measurements alone.

The key takeaway here is to never inherently trust what the device model simulations tell you. Foundry models are usually quite good, but it really depends on the foundry, the technology node and how much accuracy you require from it.  **Comprehensive validation of device models is important before they are used in multi-million dollar projects.**
## Co-simulation

Using a reference amplifier design for device model validation is a good idea for another reason: it allows us to validate active and passive modeling simultaneously. Amplifiers often have inductors, transmission lines and capacitors, and interfacing an active device with a passive model is called co-simulation.

Co-simulation is required because EM simulators cannot deal with transistor-level physics. Active and passive models need to be combined in a circuit simulator to capture parasitics required for accurate prediction of circuit performance. In general, parasitics need to be captured at three levels.
### Transistor Level

The transistor model for any active device consists of two parts:
1. **Intrinsic**: This represents the core behavior of the device. This is essentially what we just discussed in the active modeling section, where equations control the how the device behaves in simulation.
2. **Extrinsic**: This is the part of the model that defines all the parasitic elements associated with the transistor that are external to the core behavior of the device. One example is the parasitic capacitance between the source and drain due to coupling between metal connections to these terminals.

The extrinsic part of the model is usually provided only up to a certain metal level. In the source-drain capacitance example, it might only be included up to the first metal level.

In practical chip layout, it is necessary to use other metal levels to make connections on the chip. The associated parasitics need to be included in simulation. An EM simulator is a possible solution, but the complexity and narrow dimensions involved make it a resource intensive task. Also, the extreme accuracy that EM simulators are capable of is just overkill for device parasitic extraction.

Instead, most EDA tools offer a parasitic extraction tool that can be used to get extrinsic parasitics. These parasitic extraction tools are not field solvers. They use a pattern matching algorithm to extract the capacitance based on a pre-trained dataset. Parasitic extraction is the industry standard when accounting for routing parasitics in the transistor. But it is important to understand where the device model ends and the parasitic model begins to avoid under or over counting parasitics.
### Circuit Level

This step of parasitic modeling is an absolutely essential. Whether you are designing an RF circuit off-chip or on-chip, you need to account for every connection and passive component in the presence of everything else. Here is a list of usual suspects that need careful attention.
- Inductors are especially notorious for generating a significant electromagnetic field that affects anything in its vicinity. 
- Metal seal rings are used to enclose your circuit design before manufacture, and can provide a coupling path to various parts of the chip.
- Large bypass capacitors on-chip when placed next to inductors appear as ground planes moved too close to the inductor.
- If density fill cannot be avoided, they must somehow be accounted for.

The real challenge is when you have to interface active devices to the circuit level EM model. How you define ports for the transistor terminals has a major impact on the simulation accuracy. Ports cannot always be "calibrated out" and often themselves have an impact on the circuit. The goal of co-simulation is to minimize the impact by implementing the shortest possible return path for current by choosing ports properly. Additionally, you should also be careful to ensure that the EM model has enough low frequency data to ensure DC convergence of the circuit.

### Package / Board Level


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