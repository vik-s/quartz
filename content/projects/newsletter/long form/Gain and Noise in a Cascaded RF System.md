---
title: Gain and Noise in a Cascaded RF System
tags:
  - systems
project: substack
date_published: 
status: 🚧
final title:
---
Over the last few months, we have been collecting bits and pieces of concepts related to RF systems, and we will put a few of those learnings together in this article. 

For example, we discussed at length about the different kinds of gain in an RF amplifier, the sources of noise in MOS devices, and developing an intuitive feel for nonlinearity of a system. We also looked at the history and architecture of the RF superheterodyne system, and how to choose the right frequencies to prevent images.

In this article, we will talk about gain, noise and linearity metrics when RF components are cascaded to build a system.

Read time: X minutes

--

Any block in the RF transmit or receive chain such as an amplifier, filter or mixer has three metrics associated with it that are used in design optimization. They are:
- Gain (or attenuation/loss)
- Noise
- Linearity

When designing an RF system, they have a value depending on what is reasonably achievable via circuit design with a given technology. The overall system design often looks something like this.

Put *figure from Matlab RF budget analysis*

If we were to start optimizing such a system, it is important that we understand the three metrics and how they change when blocks are cascaded. Let's look at each one.
### Gain
We spoke about gain extensively in a previous article, so we won't go too deep here. Fundamentally, gain is expressed as
$$
G = 10 \log \frac{P_{out}}{P_{in}} = 20 \log \frac{V_{out}}{V_{in}}
$$
Gain is represented either in terms of power or voltage ratios. The conversion from power to voltage ratio assumes that impedances at input and output are the same, which is most often not the case in RF systems. So we will stick to power gain when possible. But remember when to use the factor of 10 or 20 when calculating decibels. This often becomes a simple source of error for RF engineers.

Both of these quantities are only ratios, and say nothing about how much actual voltage or power is present at the input or output. When talking about absolute terms, we use yet another decibel metric called dBm - decibels over milliwatt.
$$
P_{dBm} = 10 \log\frac{P_{sig}}{1 \text{mW}}
$$
This quantity tells you how much absolute power is present compared to a milliwatt. 30 dBm is 1 Watt of power. Sometimes dBW - decibels over watt is also used, in which case, 0 dBW = 30 dBm.

Consider two RF blocks that are cascaded as shown in the figure below. The voltage or power gain at the output is simply a multiplication of the gains of each individual block. In decibels, cascaded gain is the addition of the gains of each block. If one or more of the blocks shows attenuation or insertion loss, the "gain" of the block expressed in decibel is negative.

Put *picture of a cascaded gain block*

This makes it quite simple to add and subtract the gain of each block in a cascaded system to calculate overall gain.
### Noise

In a previous article, we looked at sources of electronic noise. We use a different perspective from a system point of view. We are not concerned with the actual source of noise, but only metrics that define how noisy a circuit is.
#### Input-referred noise

To do this, we use the concept of *input-referred noise*, and is common in analog circuit design. It is represented by a series voltage source and a shunt current source connected at the input of a noiseless circuit. The composite noise from each of these sources, in presence of the noiseless circuit, is equal to the noise from the original circuit. The voltage and current noise sources are often correlated too.

> Put *picture of input referred noise*

Why *input-referred*? Depending on the gain of the circuit, the noise at the output is also amplified. This makes it difficult to compare noise performance of circuits with different gain. The simpler way is to define noise at the input of the circuit.

How do we find the values of the voltage and current noise sources?
- **Voltage noise**: Short the input terminal to eliminate current noise. Measure the output noise, and divide it by the voltage gain (Vout/Vin) to obtain input-referred voltage noise.
- **Current noise**: Open the input terminal to eliminate voltage noise. Measure the output noise, and divide it by the transimpedance gain (Vout/In) to get input-referred current noise.

> Put *picture showing how voltage and current noise is obtained*
#### Noise Figure
For simple circuits, the concept of input-referred noise works nicely. For complex RF blocks, finding voltage and transimpedance gain is not trivial. Instead, we can define another metric in terms of signal to ratio (SNR).

If an amplifying RF block has a signal at its input terminal, the amplification increases both the signal and noise by the same level at the output. In terms of SNR, nothing has changed from input to the output: SNRin = SNRout. This is only assuming that the amplifier itself did not contribute any noise by itself.

In reality, in addition to the amplification of input noise, there is noise generated by the RF block. As a result, the SNRout is lower than SNRin, which leads itself to a simple definition of noise in terms of Noise Figure (NF) which is given by
$$NF = \frac{SNR_{in}}{SNR_{out}}$$
Noise figure is most often expressed in terms of decibels by taking 10xlog(NF). A noiseless circuit has a NF=1 or 0dB.

**Using input-referred noise to calculate NF**
However, signal-to-noise ratio is not always convenient to calculate and we can look at noise figure in a more intuitive way if we were to express it only in terms of noise voltages. At least for single RF blocks, we know that the relationship between the input and output signal is its voltage gain. 

Let us dive in a bit deeper with an example. Take the case of an amplifier with gain Av and input impedance Zi. This amplifier is noisy and produces an equivalent output noise voltage Vn,out. The amplifier is fed with a supply whose input resistance is Rs, generating a thermal noise 4kTRs. This scenario is shown in the figure below.

Due to the differing impedances Zi and Rs, there is a lower voltage at node X. Instead of SNR, we can use the idea of input-referred noise voltages to find NF as follows.
1. Find the input-referred noise voltage at node X; the gain from X to the output is Av
2. Find the input-referred noise voltage at input node; the gain from input to X is ɑ

We can define noise figure in terms of input-referred noise as follows:
> NF is the ratio of the input-referred voltage noise to the noise due to the source resistance.

A point of great importance here is to note that the NF depends on the relative mismatch of the input of the amplifier to the source resistance Rs, as represented by ɑ. When we visit amplifier design in a future article, it is important to remember this: **The noise performance of the amplifier depends on the choice of the source matching network**.

> Put *noise figure of amplifier example*

**Noise Figure in a Cascaded RF System**



[[projects/newsletter/long form/CascadingRFblocks.excalidraw]]










