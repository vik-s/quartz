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

The industry term for the representation of a transistor in a simulator is called a Compact Model. The term 'compact' stems from the requirement that the model needs to be simple enough to be computationally efficient while still being accurate. It is essentially a 'black box' model of transistor operation where equations are used to represent the behavior of the device at its terminals.

What actually happens inside a transistor depends on the process steps used to build it. It is costly to iterate on process steps required to build an optimal transistor by manufacturing them on silicon. Instead, Technology Computer-Aided Design (TCAD) tools (https://semiengineering.com/what-is-tcad-and-why-it-is-essential-for-the-semiconductor-industry/) provide a way to simulate the behavior of a transistor for a given sequence of processing steps. TCAD tools serve three functions:
1. Process: Mimic fabrication steps to build a transistor
2. Device: Simulate electrical current flow through a given transistor construction
3. Interconnect: Simulate metal connections in a transistor

With these TCAD tools, it is possible to obtain an estimate of currents at the transistor's terminals when a certain sequence of semiconductor processing steps are performed. Using these tools, semiconductor device engineers define the transistor construction so that it meets expected performance. Often, the results from TCAD simulation serve as a starting point for the design of a preliminary compact model.

Compact models are usually written in Verilog-A or C, and are comprised of closed form equations that analytically describe the physics of a transistor as a function of terminal voltages or currents, device size, temperature and variability. These equations are implemented by an industry standard simulator such as Cadence Design Systems' Spectre, to solve the node voltages and currents across every device in the circuit. 

The numerical behavior of these equations is important for achieving convergence during circuit simulation. They need to be both continuous and differentiable to lower computation time. The iterative process of solving for node voltages and currents often results in abnormal intermediate values for which the model equations should be well behaved to converge on a final solution.

The process of fitting a model to an actual transistor involves finding the values of constants in the analytical equations within the compact model. These constants, called model parameters, are usually defined in a text file called the model card and are derived from measurements of individual transistors. Each model has a suggested parameter extraction strategy to methodically extract the model parameters for a given transistor.

Put *picture of drain current equation*

## MOSFET Models

### The BSIM Family
One of the most popular device models for MOS transistors is the Berkeley Short-Channel IGFET{fn} Model (BSIM) developed by a team of researchers at the University of California, Berkeley. The first version introduced in the late 1980s [1] was a rather rudimentary version with only 17 model parameters. 

Since then, the complexity of the model has significantly increased as silicon MOS technology has progressed into more advanced technology nodes. MOS transistors stray away from classical modes of operation as the gate length shrinks, thus requiring more sophisticated models to capture non-ideal effects properly. This results in a compact model that requires more model parameters to accurately model modern transistors.  For example, recent versions of the BSIM4 model have over 500 parameters that need to be determined to develop a fully scalable device model.

The BSIM family of models have other flavors depending on the nature of the transistor. 
- BSIM-IMG (Independent Multi-Gate) is useful for fully-depleted MOSFETs which require independent control of top and back-gates of a fully depleted ultra-thin silicon channel.
- BSIM-CMG (Common Multi-Gate) model commonly used for FinFET applications.
- BSIM-SOI is based on BSIM4 but modified for Silicon-on-Insulator applications.
- BSIM-BULK is a modern version of BSIM6 specifically targeting bulk silicon.

Early BSIM family of models like BSIM4 are threshold voltage based models of a transistor, and are generally simpler in terms of computational complexity. But RF and analog designers found a subtle asymmetry around Vds=0 with these models, that was resulting in incorrect nonlinear results when running harmonic balance simulations.

The reason was that these models failed to pass what is called the Gummel Symmetry Test (GST), which is today the standard test for MOSFET model symmetry. Since the source-drain terminals of the MOSFET are interchangeable by construction, the model should be symmetric about Vds=0. The GST tests that this is so by differentially biasing the source-drain terminals with a common DC offset, and ensuring that the drain (or source) current and its derivatives are symmetric about Vds=0.

In 2013, BSIM6 was created using a charge-based approach that retains the original features of BSIM4 while passing GST [4] and was adopted as the industry standard for RF and analog applications of bulk silicon MOSFET.

Put *picture of GST*
### Surface Potential Models
Another alternative to threshold voltage-based models are surface-potential based models, which calculate the surface potential at the Si-SiO2 interface. They are computationally more intensive because surface potential does not have a closed form expression, and needs to be iteratively solved. Surface-potential models are capable of better accuracy in predicting many transistor phenomena because they do not make the simplifying assumptions like in threshold voltage-based models.

Two noteworthy surface potential models for MOS devices are the [Hiroshima-University STARC IGFET Model (HiSIM)](https://www.hisim.hiroshima-u.ac.jp/index.php?id=87) and Phillips Surface Potential (PSP) Model [2], both of which pass GST. The SOI version of the PSP model called PSPSOI [5] is particularly interesting for RF switch design applications where the lack of symmetry in BSIMSOI (which is derived from BSIM4) gives incorrect simulations of harmonic generation from the switch.

https://home.iitk.ac.in/~chauhan/ESSDERC2012_YSChauhan.pdf

Put *picture of evolution of BSIM*
## Bipolar Device Models

### HiCUM Model

The Hi Current Model (HiCUM) according to the University of Technology, Dresden website (https://www.iee.et.tu-dresden.de/iee/eb/hic_new/hic_intro.html) who maintain the model is described as:
> A physics-based geometry-scalable compact model for homo- and heterojunction bipolar transistors. It targets the design of circuits using Si, SiGe or III-V based processes and is particularly accurate at high-frequencies and high-current densities.

They are applicable to homojunction silicon-based BiCMOS (Bipolar+CMOS) devices as well as heterojunction III-V based bipolar devices such as gallium arsenide, indium phosphide and gallium nitride bipolar devices. The HiCUM model is available in the two 'flavors' - the L2 and L0 variations. 

The L2-level model  includes a sophisticated approach to modeling a variety of physical effects and is the more comprehensive version of the model. The L0 model is a simpler version of the HiCUM model which can be used when the extra accuracy provided by L2 is not required for the applications, or for feasibility studies.

### MEXTRAM
This is a bipolar device model which is a rather immodest abbreviation for [Most EXquisite TRAnsistor Model (MEXTRAM)](https://www.eng.auburn.edu/~niuguof/mextram/), and is currently supported by the University of Auburn. Mextram originated from NXP semiconductors in 1985, but the first release Mextram 503 was released to the public in 1994. The first digit 5 refers to the fifth generation of bipolar device models, with the first four being Ebers-Moll versions 1-3, and Gummel Poon model. The most recent Mextram release is version 505.

While the HiCUM model has been reported to do very well at high injection currents, Mextram is a viable choice for Si/SiGe bipolar devices for most RF and power applications.
### VBIC
The Vertical Bipolar Intercompany (VBIC) Model for Bipolar transistors was developed as a replacement for the standard Gummel Pool Model (SGPM), and has been widely used in industry primarily for its good accuracy in most regions of operation except high current regions. Compared to Mextram and HiCUM, the VBIC model is easier to extract and has been extensively used in modeling of GaAs devices.
### AHBT

The Agilent (now Keysight) HBT model is a Keysight Technologies specific device model aimed at improved accuracy in predicting the performance of heterojunction devices. It has been used quite extensively for 

## HEMT Device Models
### Curtice-3

### EEHEMT

### Angelov-GaN

### ASM- HEMT

## Measurement-Based Device Models

### Root Model 

### DynaFET





[1] 

[2] G. Gildenblat _et al._, “PSP: An Advanced Surface-Potential-Based MOSFET Model for Circuit Simulation,” _IEEE Trans. Electron Devices_, vol. 53, no. 9, pp. 1979–1993, Sep. 2006, doi: [10.1109/TED.2005.881006](https://doi.org/10.1109/TED.2005.881006).

[3] C. C. Mcandrew, “Validation of MOSFET model Source–Drain Symmetry,” _IEEE Trans. Electron Devices_, vol. 53, no. 9, pp. 2202–2206, Sep. 2006, doi: [10.1109/TED.2006.881005](https://doi.org/10.1109/TED.2006.881005).

[4] Y. S. Chauhan _et al._, “BSIM6: Analog and RF Compact Model for Bulk MOSFET,” _IEEE Trans. Electron Devices_, vol. 61, no. 2, pp. 234–244, Feb. 2014, doi: [10.1109/TED.2013.2283084](https://doi.org/10.1109/TED.2013.2283084).

[5] W. Wu _et al._, “PSP-SOI: A Surface Potential Based Compact Model of Partially Depleted SOI MOSFETs,” in _2007 IEEE Custom Integrated Circuits Conference_, San Jose, CA, USA: IEEE, 2007, pp. 41–48. doi: [10.1109/CICC.2007.4405678](https://doi.org/10.1109/CICC.2007.4405678).