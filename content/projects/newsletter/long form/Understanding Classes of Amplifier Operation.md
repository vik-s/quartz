---
title: Understanding Classes of Amplifier Operation
tags:
  - circuit
project: substack
date_published: 
status: 🚧
final title:
---
# Class A, B, and AB
I recently concluded a 4-part mini-series on automotive radar, and found that it is much easier for me to write these articles if I can hold a train of thought on a particular topic. And since lot of electrical engineering is so complex to explain, most topics will benefit from being its own mini-series. This way I can go sufficiently in-depth while keeping the content manageable in length, and not rushing through the explanations.

In this spirit, I'd like to start a series on amplifiers. Specifically, we will look at the classes of amplifier operation which are generally categorized by alphabets from A to S. Not all alphabets exist as amplifier classes. We will conceptually break down the seemingly random assignment of letters and look at the operation of each one closely.

This is a challenging undertaking and likely will take several articles to cover fully. This article will cover Classes A, B, and AB, which should be relatively straightforward. The going will get tough for alphabets to come later. It should be an exciting journey. Please consider subscribing to the newsletter so that you will get all the articles delivered to your email inbox.

In this article, we will discuss:

- thing1
- thing2
- thing3

Read Time: X mins

## Current-Voltage Relation of an Active Device

First, we need to understand the ideal operating behavior of an active, amplifying device. This is the foundation on which amplifier classes will be defined.

In general, an active transistor generates current when a voltage is applied to it. For a bipolar transistor, a constant current is held at the base terminal, and the collector voltage is varied to generate a collector current. Bipolar junction transistors can be made on silicon, or they can employ heterojunctions like in Gallium Arsenide (GaAs) devices. The latter is more popularly used for GHz-range power amplifier designs.

For a field-effect transistor (FET), the gate is held at a constant voltage and the drain current is varied to generate a drain current. The FET can be made on silicon, such as a bulk-silicon or silicon-on-insulator MOSFET, or it can be made on GaAs using pseudomorphic high-electron mobility transistors (pHEMTs). A more recent development involves the use of Gallium Nitride FETs, which provide high power operation.

Regardless of what kind of device is being used, the current-voltage relationship of an ideal active device looks like in the figure below.

*Put picture of IV curve*

Real devices do not behave in such an ideal fashion, but we will make some simplifying assumptions here so we can keep our eye on the prize - amplifier classes - and not get distracted by device non-idealities.

- When a voltage above zero is applied to the collector/drain, it conducts current. The level of current depends on input current/voltage, provided it is above a threshold value.
- The region where the device provides constant current is called the *saturation* region.
- When voltage is below zero, there is no conduction of current. This is called the *cut-off* region.
- The amount of voltage needed to reach a constant level of current is called *knee voltage* (Vk). The region between zero and knee-voltage is called *quasi-linear* region. Most often knee voltage is only a fraction of maximum allowed terminal voltage.

With this view of simple transistor operation, we can start talking about amplifier classes.
## Class A

Class A operation is the classical linear amplifier that most basic textbooks introduce. In this class of operation, the device operates only in the quasi-linear region. The sinusoidal signal at the output will have a maximum voltage of Vk and a maximum current of Imax. To ensure that the sinusoidal signal does not get cut off at the peak or trough, the transistor is biased at Imax/2 and a voltage Vdc that is below knee-voltage.

*put picture of transistor in class A operation*

Because we have been so careful to only have the voltage and current operate in the quasi-linear region, the output voltage is a faithful amplification of the input signal. The negative swing of the signal does not enter cutoff, and the positive swing does not enter saturation. The high fidelity of the output signal makes the class of operation highly linear. This means that there is minimal distortion of the amplified signal.

### Efficiency
