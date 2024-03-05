---
title: Understanding Noise Figure and its Measurement Methods
tags:
  - metrology
project: substack
date_published: 
status: 🚧
final title:
---
Noise is the great limiter. Without it, we would be communicating with aliens, have infinite computing power and create Skynet. Unfortunately for us mere mortals, we have to overcome the effects of noise in our world. In this article, we look at the basics.

You will learn:
- thing1
- thing2
- thing3
---

## Understanding Random Noise

Let's get down to the brass tacks, and consider current flow in a wire when a battery is connected to it. At room temperature, you will have some average current flow depending on the wire resistance and a whole lot of fluctuations of current at every point of the wire, at all times. 

You cannot predict the instantaneous current at any point in time because it is completely random. This "noise" from the random motion of electrons can only be represented by its "average power", which you get by squaring the noise and averaging over time. But as RF engineers, we much prefer a frequency domain view of things.

Fluctuations can happen fast or slow since it is completely random. This means that the noise power spectrum can have a wide range of frequencies. To find the power at any frequency, we run the time domain signal through a filter bank as shown in the figure below. Each filter has a different center frequency and an ideal 1-Hz bandwidth. At the output of each filter, we measure the average power. The result is called the "Power Spectral Density (PSD)" of the noise signal. The unit of measurement is V^2/Hz.

When measuring only positive frequencies, the PSD is called "one-sided". Often the math gets simpler for calculations if both negative (footnote) and positive frequencies are included, and the PSD is then "two-sided". The one-sided PSD is scaled down by a factor of two to make it two-sided, so that area under the spectrum or total energy is constant.

Fig1

## Noise in Resistors

The PSD of noise in a resistor R is given by 4kTR, where k=1.38 x 10-23 J/K (boltzmann's constant) and T is absolute temperature in Kelvin. It is often called "white noise" because like white light, it contains all the frequencies with equal power levels.

If we were to calculate the area under the white noise to find total noise energy, we get an impossible result. Infinite energy from finite ambient temperature. Well, turns out that noise is not that white after all, and the PSD starts to fall off at frequencies over a terahertz.

To avoid this confusion, we will just talk about noise in a 1 Hz bandwidth. This means that 4kTR is the noise power in a resistor when a 1 Hz bandpass filter is applied at any frequency below a terahertz. To make it even easier for electrical engineers, we can take a square root of the average noise power and represent it as a root-mean-square (RMS) noise voltage expressed in V/sqrt(Hz). 

Sqrt(Hz) is a strange unit, but we live with it because the numerator is in volts, and lends itself to circuit analysis nicely. Given any circuit with a noisy resistor R, you can immediately replace it by a noiseless resistor with a noise voltage or noise current. The Thevenin and Norton representations shown below prove quite useful in circuit analysis.

An immediate application of these concepts is in the received noise of an antenna which is often characterized by its radiation resistance. In the calculation of noise in a system, the antenna produces a noise voltage of sqrt(4kTR_rad).

Fig2
## Noise in Transistors

MOSFETs:
- thermal noise in saturation region
- gate resistance noise
- gate induced noise current
- flicker noise

BJTs:
- thermal noise from physical B, C, E resistors
- Shot noise from carrier transport across Base / Emitter

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

