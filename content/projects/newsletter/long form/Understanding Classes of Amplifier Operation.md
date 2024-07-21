---
title: Understanding Classes of Amplifier Operation
tags:
  - circuit
project: substack
date_published: 
status: 🚧
final title:
---
[[projects/newsletter/long form/Understanding Classes of Amplifier Operation 2024-07-20 07.15.02.excalidraw]]
# Part 1: Fundamentals
I recently concluded a 4-part mini-series on automotive radar, and found that it is much easier for me to write these articles if I can hold a train of thought on a particular topic. And since lot of electrical engineering is so complex to explain, most topics will benefit from being its own mini-series. This way I can go sufficiently in-depth while keeping the content manageable in length, and not rushing through the explanations.

In this spirit, I'd like to start a series on power amplifiers. The scope can be very large. Here, we will focus on amplifier classes labeled by alphabet. Not all letters in between are amplifier classes, not all are even RF (they're audio range), and we might even argue about whether thats how a particular class is defined. But herein lies the fun.

It is not easy to define a specific power level after which an amplifier becomes a "power amplifier." For example, a cell phone amplifier outputs about 1 watt, audio amplifiers output hundreds of watts, while low power bluetooth circuits might output only 10 milliwatts. An amplifier at any output power can be made to operate in different classes.

This series is a challenging undertaking and will take many articles to cover fully. Please consider subscribing to the newsletter so that you will get all the articles of the series delivered to your inbox.

In this article, we will define some basics, get our terminology in line and look at a simple amplifier:

- thing1
- thing2
- thing3

Read Time: X mins

## Current-Voltage (IV) Relation of an Active Device

First, we need to understand the ideal operating behavior of an active, amplifying device. This is the foundation on which amplifier classes and operation will be defined.

In general, an active transistor generates current when a voltage is applied to it. For a bipolar transistor with a voltage at its collector, injecting a base current results in a large collector current. The ratio of collector current to base current is called the *current gain*, β. Bipolar junction transistors can be made on silicon, or they can employ heterojunctions such as Silicon-Germanium (SiGe) or Gallium Arsenide (GaAs). 

For a field-effect transistor (FET) with a voltage at the drain, increasing the gate voltage above a threshold value causes drain current to flow. The amount of drain current for a change in gate voltage is called *transconductance* (commonly represented as gm). The FET can be made on silicon, such as a bulk-silicon or silicon-on-insulator (SOI) MOSFET, or it can be made on GaAs using pseudomorphic high-electron mobility transistors (pHEMTs). A more recent development involves the use of Gallium Nitride (GaN) FETs, which provide high power operation.

Regardless of what kind of device is being used, the current-voltage relationship of an ideal active device looks like in the figure below.

*Put picture of IV curve*

Real devices do not behave in such an ideal fashion, but we will describe transistor operation in a simple way, so we can keep our eye on the prize - amplifier classes. Let's assume we're dealing with a FET device for the sake of terminology.

- Vk is the "knee voltage", after which increasing drain voltage will not increase the current because it is in *saturation*. Below knee voltage, the device is basically a gate-voltage controlled resistor.
- Vt is the "threshold voltage" on the gate, which is the minimum value of voltage needed to make the device conduct. Below this value, the device will be in the *cut-off region*, and there will be no current.
- Imax is the maximum value of current that the device is capable of supplying.
- When the device is above cut-off but hasn't its maximum drain current Imax yet, the device is said to operating in the *quasi-linear* region.

Ideally, we want a device that can provide a high value of Imax, have a low Vknee voltage, and equally spaced, flat lines on the IV space as the gate voltage is increased.
## Load Line

An amplifying device converts the output current into a voltage only when a load is placed at its output. The choice of this load affects the voltage-gain and total power extracted from the output of the transistor. On the IV space, the *load-line* is a diagonal line whose slope depends on the load value. The figure shows a simplistic representation of a purely resistive load.

In reality, the load is a complex value and is constructed as a combination of inductors, capacitors, transformers and resistors. This is because the output impedance of a transistor is usually capacitive, and depending on the purpose of the amplifier, the load network is a carefully designed, complex impedance. As a result, the *AC load line* is usually different from the *DC load line* because the presence of reactive elements results in a different load line that varies with frequency compared to a purely resistive DC load.

There are two fundamental methods to design load networks (although it can get very complicated in actual amplifier designs):
* **Conjugate Match**: The load impedance is designed to be the complex conjugate of the device output impedance. This provides maximum power transfer from the device to the load *provided that the active device has **no limitations** on the power it can deliver*.
* **Power Match:** The load impedance is designed to deliver maximum power to the load, *while considering the power limitations of the device*. This is usually not the complex conjugate value. This optimal impedance is often experimentally determined with a special measurement called *load-pull*.
## Quiescent Bias Point, and Dynamic IV

A classical amplifier that uses an amplifying device with a load at its output, is biased at a specific voltage and current setting called its *quiescent bias point*, that lies on the load-line. This is a very important choice for amplifier operation.

If the amplitude of the input RF signal is low enough and gain isn't too terribly high, the devices might not be sufficiently disturbed from their quiescent bias condition. This is usually the case in low power amplifiers, such as low-noise amplifiers. For medium and high-power amplifiers, the bias point will move with the input RF signal, or if the output signal swing is high enough, with the output RF signal.

In such a scenario, we need to think of a dynamic IV space where the bias point will instantaneously reside during the process of amplifying an RF signal. This complicates matters: (1) the amplifier operation starts being non-linear and (2) the IV behavior itself might change based on the previous bias point it was in (this is called memory effect). We won't get into all the complexities right away, but it is useful to form a clear mental picture of what goes on at a device level.


*draw a picture of static vs dynamic load lines inspired by the link below*

https://www.qorvo.com/design-hub/blog/model-based-gan-pa-design-basics-what-and-why-intrinsic-iv-waveforms

## Conduction Angle

In the simplest case of an amplifier with a constant (not dynamic) quiescent bias point, the transistor can be conducting for the whole duration of amplification. In other words, the transistor is always conducting for all 360 degrees on the input sinusoidal signal. The *conduction angle* in this case is said to be 360 degrees.

But we already saw that the RF waveform is capable of changing the operating condition of this device. Instead of wasting power by keeping the transistor in conduction all the time, we can keep it off by default and let the RF signal swing push it into conduction. In this case, the transistor will conduct only when the RF signal is sufficiently high to turn on the transistor. For the rest of the time, it will stay off. In such cases, the conduction angle will be *less than* 360 degrees.

We'll encounter this idea as we go through the different amplifier classes.
*Draw a picture of conduction angle*
## Efficiency

Efficiency is a metric of great importance for a power amplifier, and is loosely a measure of how much of the supplied DC power is converted to RF power at the output. An efficient amplifier converts most the supplied power into RF, and implies better battery life for handheld devices, and lower heat generation in the active devices. As we will see later, efficiency almost always comes at the expense of amplifier linearity. 

As we discussed in the previous section, having a conduction angle of 360 degrees means that the transistor is burning DC power the whole time. A reduced conduction angle saves power by keeping the transistor off through at least some part of the signal cycle, thereby increasing efficiency.

There are two important efficiency metrics we need to define:
- **Power Added Efficiency (PAE)**: It is the ratio of the output power after accounting for the gain of the amplifier, to the DC power supplied to the amplifier. This is the more accurate definition, and is generally applicable to all amplifiers regardless of their gain level.
- **Drain Efficiency (DE)**: It is the ratio of the output power to the DC power supplied to the amplifier. This definition is valid only when the gain is sufficiently high such that the output power is much higher than the input power. For example, drain efficiency approaches PAE when the gain is 1000x (or 30 dB), in which case, ignoring the input power is a negligible source of error.

*add the formulas for PAE and DE*

Many engineers and even vendors erroneously use these efficiency definitions interchangeably regardless of amplifier gain. So always make sure to clarify with your colleagues or vendors what efficiency definition being referred to.

With these definitions in place, we can delve into class A amplifier operation in the next article. See you there!

**~END OF ARTICLE~**
# Part 2: Class A Amplifier

Class A operation is the classical linear amplifier that most basic textbooks introduce. Here we will choose the quiescent bias point to be smack dab in the center of the quasi-linear range. The input voltage is constrained to swing only in the limited range where the transistor response is linear. The current is set to Imax/2 so that the signal swing can utilize the entire linear range of output current, without being limited by the cutoff region, or Imax of the device.

*put picture of transistor in class A operation using only IV curves*

Because we have been so careful to only have the voltage and current operate in the quasi-linear region, the output voltage is a faithful amplification of the input signal. The negative swing of the signal does not enter cutoff, and the positive swing does not enter saturation. The high fidelity of the output signal makes the class of operation highly linear. This means that there is minimal distortion of the amplified signal.

However, having the transistor conduct for all 360 degrees of the signal cycle is bad for efficiency because it is dissipating power all the time. 

*Add an equation / picture to show that efficiency of the amplifier is at best 50%*
## Circuit Example

A simple emitter/source follower is a good example of a class A amplifier. 







