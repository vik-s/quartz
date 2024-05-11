---
title: How transistor models are developed
tags:
  - device
project: substack
date_published: 
status: 🚧
final title: 
Subtext: Looking under the hood of your schematics...
---
Transistor models are fundamental for circuit design.  But every model has its strengths and weaknesses. Having an understanding of what model is being used, and what other options are available provides an additional dimension of trust (or distrust) in the simulation results. Having a healthy level of skepticism regarding the simulated circuit metrics differentiates the designer new to the art of circuit design, from a veteran who has done it for decades. 

In this article, we will look at compact models used for MOS and bipolar junction transistors. Specifically we will cover:
- The BSIM family of models
- Usefulness of surface potential models
- Bipolar models such as HiCUM, Mextram, VBIC and AHBT
- Practical insights and choosing the right model

Read time: X mins

--
## What are Compact Models?

The industry term for a transistor's representation in a simulator is Compact Model. The term 'compact' comes from the requirement that the model be basic enough to be computationally efficient while remaining accurate. It is essentially a 'black box' model of transistor operation, with equations representing the device's behavior at its terminals.

What happens inside a transistor is determined by the manufacturing process steps. It is costly to iterate on the process steps required to create an optimum transistor by manufacturing it on silicon. Instead, [technology computer-aided design (TCAD)](https://semiengineering.com/what-is-tcad-and-why-it-is-essential-for-the-semiconductor-industry/) tools allow you to mimic the behavior of a transistor for a specific sequence of processing steps.

TCAD tools serve three functions:
1. Process: Mimic fabrication steps to build a transistor
2. Device: Simulate electrical current flow through a given transistor construction
3. Interconnect: Simulate metal connections in a transistor

With these TCAD tools, it is possible to estimate current at the transistor's terminals when a sequence of semiconductor processing steps are implemented. Semiconductor device engineers fine-tune the processing steps till the transistor meets expected performance. The results from TCAD simulation then serves as a starting point for the design of a preliminary compact model.

Compact models are typically written in Verilog-A or C and are made up of equations that analytically describes the physics of a transistor in terms of terminal voltages or currents, device size, temperature, and variability. An industry standard simulator, such as Cadence Design Systems' Spectre, uses these equations to solve the node voltages and currents across each device in the circuit.

The numerical behavior of these equations is important for achieving convergence during circuit simulation. To save calculation time, they must be continuous as well as differentiable. The iterative process of solving for node voltages and currents often results in abnormal intermediate values for which the model equations should be well behaved to converge on a final solution.

The process of fitting a model to an actual transistor entails determining the values of constants in the analytical equations of the compact model. These constants, known as model parameters, are often described in a text file called the model card and obtained from measurements of individual transistors. Each model includes a recommended parameter extraction procedure for carefully extracting the model parameters for a particular transistor.

Put *picture of drain current equation*

## MOSFET Models

Because MOSFETs are widely used in electronic circuit design, the use of device models based on application is quite well defined. For example, when silicon-on-insulator technology is employed, there are just a few device model alternatives (e.g., BSIM-SOI, PSP-SOI, HiSIM-SOI). When conventional planar bulk silicon transistors are utilized, BSIM-BULK is an excellent choice, and so on.

Models are generally categorized on that basis of threshold-voltage, surface-potential or inversion-charge. In the section below, we will compare these approaches and what constitutes state-of-the-art for MOSFET models today.
### The BSIM Family
One of the most popular device models for MOS transistors is the Berkeley Short-Channel IGFET{fn} Model (BSIM) developed by a team of researchers at the University of California, Berkeley. The first version introduced in the late 1980s [1] was a rather rudimentary version with only 17 model parameters. 

Since then, the model's complexity has grown dramatically as silicon MOS technology has improved to more advanced technology nodes. MOS transistors deviate from classical modes of operation when the gate length decreases, necessitating increasingly advanced models to represent non-ideal phenomena properly. This yields a compact model that requires more model parameters to adequately represent modern day transistors. For example, latest versions of the BSIM4 model require approximately 500 parameters to construct a fully scalable device model.

The BSIM family of models have other flavors depending on the nature of the transistor. 
- BSIM-IMG (Independent Multi-Gate) is useful for fully-depleted MOSFETs which require independent control of top and back-gates of a fully depleted ultra-thin silicon channel.
- BSIM-CMG (Common Multi-Gate) model commonly used for FinFET applications.
- BSIM-SOI is based on BSIM4 but modified for Silicon-on-Insulator applications.
- BSIM-BULK is a modern version of BSIM6 specifically targeting analog and RF design on bulk silicon.

Early BSIM family of models like BSIM4 are threshold voltage based models of a transistor, and are generally simpler in terms of computational complexity. But RF and analog designers found a subtle asymmetry around Vds=0 with these models, that was resulting in incorrect nonlinear results when running harmonic balance simulations.

The reason was that these models failed to pass what is called the Gummel Symmetry Test (GST), which is today the standard test for MOSFET model symmetry. Since the source-drain terminals of the MOSFET are interchangeable by construction, the model should be symmetric about Vds=0. The GST tests that this is so by differentially biasing the source-drain terminals with a common DC offset, and ensuring that the drain (or source) current and its derivatives are symmetric about Vds=0.

In 2013, BSIM6 was created using a inversion charge-based approach that retains the original features of BSIM4 while passing GST [4] and was adopted as the industry standard for RF and analog applications of bulk silicon MOSFET. Interestingly, the inversion charge based approach came from a collaboration between the BSIM and the the [EKV (Enz-Krummenacher-Vittoz) model](https://archiveweb.epfl.ch/iclab.epfl.ch/ekv/) group to create a world-class open-source MOSFET model for the design community. 

The EKV model was developed primarily for low-power CMOS applications in which MOS devices were operating in weak-inversion or even subthreshold mode. It's surprising simple with only 14 model parameters. However, the inversion-charge-based strategy they utilized, together with referring all transistor voltages to the body rather than the source, allowed the EKV model to pass the GST. The addition of these characteristics to the widely used BSIM4 model resulted in the creation of BSIM5, which was later modified to become BSIM6 and then dubbed BSIM-BULK.

Put *picture of GST*
### Surface Potential Models
Another alternative to threshold voltage-based models are surface-potential based models, which calculate the surface potential at the Si-SiO2 interface. They are computationally more intensive because surface potential does not have a closed form expression, and needs to be iteratively solved. Surface-potential models are capable of better accuracy in predicting many transistor phenomena because they do not make the simplifying assumptions like in threshold voltage-based models.

Two noteworthy surface potential models for MOS devices are the [Hiroshima-University STARC IGFET Model (HiSIM)](https://www.hisim.hiroshima-u.ac.jp/index.php?id=87) and Phillips Surface Potential (PSP) Model [2], both of which pass GST. The SOI version of the PSP model called PSPSOI [5] is particularly interesting for RF switch design applications where the lack of symmetry in BSIMSOI (which is derived from BSIM4) gives incorrect simulations of harmonic generation from the switch. Similarly HiSIM has an SOI equivalent model as well.

https://home.iitk.ac.in/~chauhan/ESSDERC2012_YSChauhan.pdf

Put *picture of evolution of BSIM*
## Bipolar Device Models

Bipolar device models are arguably a bit of the wild west. When it comes to choosing a model for homojunction devices such as silicon bipolar devices or heterojunction devices such as silicon-germanium or gallium arsenide bipolar devices, there are several options available. 

Depending on who you ask, you will find that modeling engineers have strong opinions which model is superior. Other times, you will be locked into a certain model due to legacy reasons if only due to the fact that this model has 'worked before.' 

To add to the difficulty of choosing a model, even simply evaluating a model is a time consuming process. Model fitting is time consuming, and evaluation needs to be performed on a variety of circuits and simulation types, from DC to large signal. The model also needs to be evaluated against measurements that are free from packaging effects so that the device model may be evaluated fairly. Such data is not easy to obtain.

All of the compact models listed below are widely used in a variety of bipolar devices. 
### HiCUM Model
The Hi Current Model (HiCUM) according to the University of Technology, Dresden website (https://www.iee.et.tu-dresden.de/iee/eb/hic_new/hic_intro.html) is described as:
> A physics-based geometry-scalable compact model for homo- and heterojunction bipolar transistors. It targets the design of circuits using Si, SiGe or III-V based processes and is particularly accurate at high-frequencies and high-current densities.

The HiCUM model is available in the two 'flavors' - the L2 and L0 variations. The L2-level model  includes a sophisticated approach to modeling a variety of physical effects and is the more comprehensive version of the model. The L0 model is a simpler version of the HiCUM model which can be used when the extra accuracy provided by L2 is not required for the applications, or for feasibility studies.

HiCUM has been used for the modeling of 55nm SiGe HBTs from STMicroelectronics up to the Sub-THz range [6]. HiCUM has also shown good applicability for scalable  GaAs HBT modeling [7].
### MEXTRAM
This is a bipolar device model which is a rather immodest abbreviation for [Most EXquisite TRAnsistor Model (MEXTRAM)](https://www.eng.auburn.edu/~niuguof/mextram/), and is currently supported by the University of Auburn. Mextram originated from NXP semiconductors in 1985, but the first release Mextram 503 was released to the public in 1994. The first digit 5 refers to the fifth generation of bipolar device models, with the first four being Ebers-Moll versions 1-3, and the Standard Gummel Poon model. 

While the HiCUM model has been reported to do very well at high injection currents, Mextram is a viable choice for most Si/SiGe bipolar devices targeting RF and power applications. It is a comprehensive model that captures most advanced physical effects occuring in modern bipolar devices and is widely used in industry.
### VBIC
The Vertical Bipolar Intercompany (VBIC) Model for Bipolar transistors was developed as a replacement for the standard Gummel Pool Model, and has been widely used in industry primarily for its good accuracy in most regions of operation except high current regions. Compared to Mextram and HiCUM, the VBIC model is easier to extract and has been extensively used in modeling of GaAs devices. The choices of VBIC over MEXTRAM or HiCUM mostly depends on the application for which the device is used, which physical effects dominate transistor action and what impact they have on the circuit operation.
### AHBT
The Agilent (now Keysight) HBT (AHBT) model is a proprietary HBT model developed by Keysight Technologies. In my opinion, there is no specific reason to use AHBT over others and the decision to use it might often be rooted in the product design flow of the company, which may be reliant on Keysight's Advanced Design System. Keysight also provides a turnkey model extraction package for AHBT which assists in rapid model extraction. The model is accurate enough to capture most effects occurring in bipolar devices and is arguably as good as any of the others.
## Conclusion


## References

[1] B. J. Sheu, D. L. Scharfetter, P.-K. Ko, and M.-C. Jeng, “BSIM: Berkeley short-channel IGFET model for MOS transistors,” _IEEE J. Solid-State Circuits_, vol. 22, no. 4, pp. 558–566, Aug. 1987, doi: [10.1109/JSSC.1987.1052773](https://doi.org/10.1109/JSSC.1987.1052773).

[2] G. Gildenblat _et al._, “PSP: An Advanced Surface-Potential-Based MOSFET Model for Circuit Simulation,” _IEEE Trans. Electron Devices_, vol. 53, no. 9, pp. 1979–1993, Sep. 2006, doi: [10.1109/TED.2005.881006](https://doi.org/10.1109/TED.2005.881006).

[3] C. C. Mcandrew, “Validation of MOSFET model Source–Drain Symmetry,” _IEEE Trans. Electron Devices_, vol. 53, no. 9, pp. 2202–2206, Sep. 2006, doi: [10.1109/TED.2006.881005](https://doi.org/10.1109/TED.2006.881005).

[4] Y. S. Chauhan _et al._, “BSIM6: Analog and RF Compact Model for Bulk MOSFET,” _IEEE Trans. Electron Devices_, vol. 61, no. 2, pp. 234–244, Feb. 2014, doi: [10.1109/TED.2013.2283084](https://doi.org/10.1109/TED.2013.2283084).

[5] W. Wu _et al._, “PSP-SOI: A Surface Potential Based Compact Model of Partially Depleted SOI MOSFETs,” in _2007 IEEE Custom Integrated Circuits Conference_, San Jose, CA, USA: IEEE, 2007, pp. 41–48. doi: [10.1109/CICC.2007.4405678](https://doi.org/10.1109/CICC.2007.4405678).

[6] S. R. Panda, T. Zimmer, A. Chakravorty, N. Derrier, and S. Fregonese, “Exploring Compact Modeling of SiGe HBTs in Sub-THz Range With HICUM,” _IEEE Trans. Electron Devices_, vol. 71, no. 1, pp. 173–183, Jan. 2024, doi: [10.1109/TED.2023.3321017](https://doi.org/10.1109/TED.2023.3321017).

[7] T. Nardmann, P. Kolev, N. Tao, and M. Schröter, “Geometry scalable compact modeling of GaAs HBTs,” in _2022 IEEE BiCMOS and Compound Semiconductor Integrated Circuits and Technology Symposium (BCICTS)_, Phoenix, AZ, USA: IEEE, Oct. 2022, pp. 212–215. doi: [10.1109/BCICTS53451.2022.10051750](https://doi.org/10.1109/BCICTS53451.2022.10051750).