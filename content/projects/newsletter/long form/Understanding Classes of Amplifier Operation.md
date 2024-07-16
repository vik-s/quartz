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

In this spirit, I'd like to start a series on amplifiers. Specifically, we will look at the classes of amplifier operation which are generally categorized by alphabets from A to S. Not all alphabets exist as amplifier classes. Some are exclusively used in audio applications. We will conceptually break down the seemingly random assignment of letters and look at the operation of each one closely.

This is a challenging undertaking and will take many articles to cover fully. Please consider subscribing to the newsletter so that you will get all the articles of the series delivered to your inbox.

In this article, we will discuss:

- thing1
- thing2
- thing3

Read Time: X mins

## Current-Voltage (IV) Relation of an Active Device

First, we need to understand the ideal operating behavior of an active, amplifying device. This is the foundation on which amplifier classes and operation will be defined.

In general, an active transistor generates current when a voltage is applied to it. For a bipolar transistor, a constant current is held at the base terminal, and the collector voltage is varied to generate a collector current. Bipolar junction transistors can be made on silicon, or they can employ heterojunctions like in Gallium Arsenide (GaAs) devices. The latter is more popularly used for GHz-range power amplifier designs.

For a field-effect transistor (FET), the gate is held at a constant voltage and the drain current is varied to generate a drain current. The FET can be made on silicon, such as a bulk-silicon or silicon-on-insulator (SOI) MOSFET, or it can be made on GaAs using pseudomorphic high-electron mobility transistors (pHEMTs). A more recent development involves the use of Gallium Nitride FETs, which provide high power operation.

Regardless of what kind of device is being used, the current-voltage relationship of an ideal active device looks like in the figure below.

*Put picture of IV curve*

Real devices do not behave in such an ideal fashion, but we will describe transistor operation in a simple way, so we can keep our eye on the prize - amplifier classes. Let's assume we're dealing with a FET device for the sake of terminology.

- Vk is the "knee voltage", after which increasing drain voltage will not increase the current because it is in *saturation*. Below knee voltage, the device is basically a gate-voltage controlled resistor.
- Vt is the "threshold voltage" on the gate, which is the minimum value of voltage needed to make the device conduct. Below this value, the device will be in the *cut-off region*.
- Imax is the maximum value of current that the device is capable of supplying.
- When the device is above cut-off but hasn't its maximum drain current Imax yet, the device is said to operating in the *quasi-linear* region.

Ideally, we want a device that can provide a high value of Imax, have a low Vknee voltage, and equally spaced, flat lines on the IV space as the gate voltage is increased.
## Load Line

An amplifying device converts the output current into an output voltage only when a load is placed at its output. The choice of this load affects the voltage-gain and total power extracted from the output of the transistor. On the IV space, the *load-line* is a diagonal line whose slope depends on the load value. The figure shows a simplistic representation of a purely resistive load.

In reality, the load is a complex value and is constructed as a combination of inductors, capacitors, transformers and resistors. This is because the output impedance of a transistor is usually capacitive, and depending on the purpose of the amplifier, the load network is a carefully designed, complex impedance.

There are two fundamental methods to design load networks (although it can get very complicated in actual amplifier designs):
* **Conjugate Match**: The load impedance is designed to be the complex conjugate of the device output impedance. This provides maximum power transfer from the device to the load *provided that the active device has **no limitations** on the power it can deliver*.
* **Power Match:** The load impedance is designed to deliver maximum power to the load, *while considering the power limitations of the device*. This is usually not the complex conjugate value. This optimal impedance is often experimentally determined with a special measurement called *load-pull*.
## Quiescent Bias Point, and Dynamic IV

A classical amplifier that uses an amplifying device with a load at its output, is biased at a specific voltage and current setting called its *quiescent bias point*, that lies on the load-line. This is a very important choice for amplifier operation.

If the amplitude of the input RF signal is low enough and gain isn't too terribly high, the devices might not be sufficiently disturbed from their quiescent bias condition. This is usually the case in low power amplifiers, such as low-noise amplifiers. For medium and high-power amplifiers, the bias point will move with the input RF signal, or if the output signal swing is high enough, with the output RF signal.

In such a scenario, we need to think of a dynamic IV space where the bias point will instantaneously reside during the process of amplifying an RF signal. This complicates matters: (1) the amplifier operation starts being non-linear and (2) the IV behavior itself might change based on the previous bias point it was in (this is called memory effect). We won't get into all the complexities right away, but it is useful to form a clear mental picture of what goes on at a device level.

https://www.qorvo.com/design-hub/blog/model-based-gan-pa-design-basics-what-and-why-intrinsic-iv-waveforms

## Conduction Angle

In the simplest case of a low-power amplifier with a constant (not dynamic) quiescent bias point, the transistor can be conducting for the whole duration of amplification. In other words, the transistor is always conducting for all 360 degrees on the input sinusoidal signal. The *conduction angle* in this case is said to be 360 degrees.

But we already saw that the RF waveform is capable of changing the operating condition of this device. Instead of wasting power by keeping the transistor in conduction all the time, we can keep it off by default and let the RF signal swing push it into conduction. In this case, the transistor will conduct only when the RF signal is sufficiently high to turn on the transistor. For the rest of the time, it will stay off. In such cases, the *conduction angle* will be less than 360 degrees.

We'll encounter this idea quite a bit as we go through the different amplifier classes. Let's start with the simplest one.
## Class A

Class A operation is the classical linear amplifier that most basic textbooks introduce. In this class of operation, the device operates only in the quasi-linear region. To ensure that the output current does not get limited by cutoff region or reach the peak current of the transistor at the peak or trough, the transistor is biased at Imax/2 and a voltage Vdc that is sufficiently above knee-voltage.

*put picture of transistor in class A operation; look at sedra/smith*

Because we have been so careful to only have the voltage and current operate in the quasi-linear region, the output voltage is a faithful amplification of the input signal. The negative swing of the signal does not enter cutoff, and the positive swing does not enter saturation. The high fidelity of the output signal makes the class of operation highly linear. This means that there is minimal distortion of the amplified signal.

During the entire cycle of the RF signal, the transistor is always conducting, and the angle of conduction is 360 degrees.

### Efficiency
