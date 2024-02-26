---
title: Terminology Every RF Engineer should know
tags:
  - fundamentals
project: substack
date_published: 
status: 🚧
final title:
---
This articles explains a list of terminology or key metrics you will use in the design of most RF systems. Knowing their definitions is key to system design, or even understanding the data sheets of various RF components. This list is by no means exhaustive. It is often the most used in microwave engineering, but there are a lot of terms you will come across.

### Gain

As opposed to voltage gain that you often see defined in operational amplifiers, in microwave engineering, we commonly deal with power gain. It is simply defined as

> the ratio of the power at the output to the power at the input

It is commonly expressed in decibels or dB. There are various definition of power gain depending on what you consider the input and output in a system, especially when talking about amplifiers. Check out this whole article I have on that topic.

When gain is above 0 dB (or 1), there is signal amplification which is often the case when working with active devices such as amplifiers and mixers. If gain is below 0 dB (or between 0 and 1), there is insertion loss which is characteristic of passive devices like filters or attenuators. 

In the two port network, Gain is commonly obtained from S-parameters by measuring S21, assuming port 1 to be the input port. S12 is often referred to as reverse gain, or isolation. For a passive, reciprocal network (with no amplification and does not differentiate which is input or output port), S21=S12. In the case of active devices, S21 != S12 and we want to minimize S12 as much as possible to increase the gain and stabilize the amplifier.

### Compression Point

Components that use active devices for amplification or mixing are inherently nonlinear. A linear amplifier will faithfully increase the level of the input signal without modifying the resulting waveform.

In reality, this is rarely the case. Transistors have voltage-dependent capacitors due to the semiconductor junctions within them, and they cause distortions of the output signal depending on the level of the input signal.

Let's think of this in the frequency domain. If you inject an amplifier with a pure signal at only one frequency, you would expect a higher output power at the same frequency and nothing else. This is almost true at a lower input signal level, and we refer to this value as linear gain.

However, distortions in the active device start to increase the level of harmonics at the output. As you raise the level of the input signal, more and more power is transferred from the fundamental tone to the harmonics. The output power level at the fundamental frequency starts to drop, giving lower gain. 

> The power level at the input or output at which the gain of the active device reaches 1 dB below linear gain is called compression point.

The choice of 1 dB is fairly arbitrary. Engineers use 0.1 dB or even 4 dB on occasion.

### Linearity

These are metrics that quantify how linear a component is in the RF system.

### Noise Figure


- Noise Factor/Figure
- Phase Noise
- Linearity
	- Intercept points
	- Adjacent Channel Leakage Ratio
	- AM-AM and AM-PM
- Amplifier Efficiency
	- Power added efficiency
	- Drain efficiency
- Matching
	- For gain, max power, noise etc
- Stability
- Calibration
- De-embedding