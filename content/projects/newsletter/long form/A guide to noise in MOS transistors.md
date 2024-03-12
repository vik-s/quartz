---
title: Understanding Noise Figure and its Measurement Methods
tags:
  - device
project: substack
date_published: 2024-03-10
status: 🟢
final title: A guide to noise in MOS Transistors
---
Noise is the great limiter. Without it, we would be communicating with aliens, have infinite computing power and create Skynet. Unfortunately for us mere mortals, we have to overcome the effects of noise in our world. In this article, we look at the basics.

You will learn:
- The fundamentals of random noise
- Noise in a resistor
- Noise sources in a mosfet
	- Thermal noise
	- Gate noise
	- Flicker noise
	- Induced noise
	- Shot noise
	- Popcorn noise
---

## Understanding Random Noise

Let's get down to the brass tacks, and consider current flow in a wire when a battery is connected to it. At room temperature, you will have some average current flow depending on the wire resistance and a whole lot of fluctuations of current at every point of the wire due to random motion of electrons.

You cannot predict the instantaneous current at any point in time because it is completely random. This "noise" from the random motion of electrons can only be represented by its "average power", which you get by squaring the noise and averaging over time. But as RF engineers, we much prefer a frequency domain view of things.

Fluctuations can happen fast or slow since it is completely random. This means that the noise power spectrum can have a wide range of frequencies. To find the power at any frequency, we run the time domain signal through a filter bank as shown in the figure below. Each filter has a different center frequency and an ideal 1-Hz bandwidth. At the output of each filter, we measure the average power. The result is called the "Power Spectral Density (PSD)" of the noise signal. The unit of measurement is V^2/Hz.

When measuring only positive frequencies, the PSD is called "one-sided". Often the math gets simpler if both negative (footnote) and positive frequencies are included, and the PSD is then "two-sided". The one-sided PSD is scaled down by a factor of two to make it two-sided, so that area under the spectrum or total noise energy is constant.

Fig1

## Noise in Resistors

The PSD of noise in a resistor R is given by 4kTR, where k=1.38 x 10-23 J/K (boltzmann's constant) and T is absolute temperature in Kelvin. It is often called "white noise" because like white light, it contains all the frequencies with equal power levels.

If we were to calculate the area under the white noise to find total noise energy, we get an impossible result. Infinite energy from finite ambient temperature. Well, turns out that noise is not that white after all, and the PSD starts to fall off at frequencies over a terahertz.

To avoid this confusion, it is easier to calculate noise energy in a 1-Hz bandwidth. This means that 4kTR is the noise power in a resistor when a 1 Hz bandpass filter is applied at any frequency below a terahertz. To make it even easier for electrical engineers, we can take a square root of the average noise power and represent it as a root-mean-square (RMS) noise voltage expressed in V/sqrt(Hz). 

Sqrt(Hz) is a strange unit, but we live with it because the numerator is in volts, and lends itself to circuit analysis nicely. Given any circuit with a noisy resistor R, you can immediately replace it by a noiseless resistor with a noise voltage or noise current. The Thevenin and Norton representations shown below prove quite useful in circuit analysis. If noise voltage is expressed in V/sqrt(Hz), noise current is A/sqrt(Hz).

An immediate application of these concepts is in the received noise of an antenna which is often characterized by its radiation resistance. In the calculation of noise in a system, the antenna produces a noise voltage of sqrt(4kTR_rad) V/sqrt(Hz).

Fig2
## Noise in MOSFETs

This gets complicated really fast and the section below assumes you have a basic understanding of transistor operation. Let's identify the various noise sources and qualitatively understand why they occur and their relative importance.

Noise in a MOSFET arises from a variety of sources, but the majority of it comes from its intrinsic thermal noise especially at RF frequency. With good design practices, the contribution of the other sources can be minimized. 

#### Channel Thermal Noise
Channel thermal noise in a MOSFET is approximated with a noise current between source and drain whose PSD is 4kT\gamma.gm, or as a noise voltage at the input gate whose PSD is 4kT\gamma/gm. 

gm is the "transconductance" of the transistor, which is a measure of how much current it generates for a given input voltage. \\gamma is the "white noise gamma factor" or "excess noise coefficient" with a value of 2/3 for transistors whose gate length is sufficiently large (>1 micron). As the gate length of the transistor shrinks below 1 micron, the value of \gamma goes up to even 2 due to noise contributions from parasitic resistances in the small transistor and other effects such as velocity saturation and channel length modulation. The value of \gamma is usually determined by measurements for each particular technology node.

(define terms velocity saturation and channel length modulation)

The figure below shows the channel thermal noise as a function of frequency, gate-source voltage, and drain-source voltage, for different gate lengths. Several observations about channel current noise can be made:
- It is higher for small transistor gate lengths due to increased parasitic resistances
- It remains relatively flat with frequency showing that it is "white" in nature
- It increases with gate-source voltage because it is directly proportional to the transconductance (which increases with gate source voltage).
- It is relatively insensitive to drain-source voltage because the pinch-off region after the device is in saturation does not contribute to noise. Any slight increases with Vds are due to channel length modulation.

If the drain voltage is increased far above the rated operating voltage of the MOSFET, avalanche effects kick in and the current noise increases drastically. We do not operate transistors in this region normally, but its worth a mention.

Fig3

#### Flicker noise
https://web.mit.edu/klund/www/papers/UNP_noise.pdf

Flicker or 1/f noise affects MOSFETs at low frequencies and its origins have been debated over the years. Strangely, this 1/f power law occurs across nature from coastline topography, neuronal spike patterns to animal vocalizations (https://www.nature.com/articles/s41598-023-28444-z). In the context of electronics, there are two competing models to explain this effect, both of which have supporting evidence:

1. McWhorter Model -  which claims that flicker noise is due to trapping and de-trapping of electrons at the interface of silicon and oxide in a transistor as it moves through the channel. The traps are a result of atomic bonds at the interface that are left "dangling" so that they can trap an electron when possible.
2. Hooge Model - which claims that flicker noise is due to conductivity fluctuations arising from variations of mobility in the bulk of the material.

There are attempts to merge the two theories too. Without getting deep into the origins of this noise, it is enough to understand that the PSD of flicker voltage noise is given by: $$\overline{V_n^2} =  \frac{K}{WLCox} . \frac{1}{f}$$where K is a process dependent constant, W and L are transistor dimensions and Cox is the oxide capacitance.

It is important to know that the 1/f PSD of flicker noise  reaches the same level as thermal noise at a point called the "1/f noise corner frequency". Ideally we want this corner frequency to be as low as possible, but modern MOS devices can have this corner in 10-100 MHz range.
#### Gate Noise

The gate of a MOSFET is often a significant contributor to noise, and its effect is more important as the gate length is scaled down. The polysilicon gate in short channel transistors have more resistance that contributes to thermal noise whose voltage PSD can be approximated by $$\overline{V_n^2} = 4kTR_{g,eff}$$Due to the distributed resistance across the gate, the effective resistance is about 1/3 the value you get from counting the number of resistor squares on the gate. If the gate is contacted on both ends, the effective resistance can be as low as 1/12. Other methods to reduce gate resistance is to use transistors with multiple fingers and siliciding the polysilicon gate to minimize its resistance.

#### Induced Gate Noise

This one is interesting. Remember that the space between the gate and channel of transistor is separated by a thin oxide layer. This makes the channel and the gate capacitively coupled, and if the frequency of operation is sufficiently high, there is a low impedance coupling path between the channel and the gate.

This means that any thermal noise in the channel "induces" a noise at the gate through the capacitive coupling path and its PSD can be expressed as: $$\overline{I_n^2}=4kTR_{g,eff}.(\omega^2C_{gg}^2) $$where Cgg is the effective gate capacitance. Induced gate current noise has a squared relationship to the frequency. When using thin oxide, short channel transistors with high gate resistance and capacitance at high frequency, induced gate noise can be a significant contributor to overall noise.

Similarly, the 1/f noise from the transistor will also be induced at the gate, with the frequency-squared dependence making it effectively proportional to frequency. Luckily, these mechanisms are at odds with each other. 1/f noise is low at high frequency, and the capacitive coupling is low at low frequency. As a result, induced flicker noise is not a major contributor.

#### Shot Noise

As the channel length of transistors shrink, there is an additional source of noise to worry about. The leaky gate oxide causes the carriers in the channel to "tunnel" through the oxide resulting in a gate leakage current. This quantum-mechanical effect will result in a shot noise contribution to the overall gate current noise and is related to the gate leakage current as: $$\overline{I_n^2}=2qI_G$$
Fortunately, the impact of shot noise is dominated by gate resistance noise and induced gate noise at RF frequencies of a few GHz. At frequencies below the GHz range, shot noise may become a significant source of noise. If you tied the source and drain of a MOSFET together to make a capacitor, the shot noise of gate current will be a dominant noise source in that case.

Now that there is gate leakage through the oxide dielectric, the resulting DC gate leakage current generates its own thermal noise and 1/f noise contributions to the gate current. The origins of 1/f noise in gate tunneling current is really not well understood. Its best to let sleeping dogs lie for the sake of this article.

## Noise in Circuits

- Calculation with Re(zout)
- Input referred noise
- Noise figure

## References

- https://web.mit.edu/klund/www/papers/UNP_noise.pdf
- https://www.nikhef.nl/~jds/vlsi/noise/sansen.pdf
- https://www.epfl.ch/labs/iclab/wp-content/uploads/2019/02/5_EKV_UMW04_Christian_Enz.pdf
- https://briefs.techconnect.org/wp-content/volumes/Nanotech2004v2/pdf/B2-23.pdf
- https://briefs.techconnect.org/wp-content/volumes/Nanotech2014v2/pdf/992.pdf
- M. J. Deen, C. . -H. Chen, S. Asgaran, G. A. Rezvani, J. Tao and Y. Kiyota, "High-Frequency Noise of Modern MOSFETs: Compact Modeling and Measurement Issues," in IEEE Transactions on Electron Devices, vol. 53, no. 9, pp. 2062-2081, Sept. 2006, doi: 10.1109/TED.2006.880370.

[[Excalidraw/Noise_in_MOS_transistors.excalidraw|Noise_in_MOS_transistors.excalidraw]]