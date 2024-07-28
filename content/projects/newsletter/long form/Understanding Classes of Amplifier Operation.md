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
In this series, I'd like to discuss power amplifiers, and since the scope can be very large, we will focus on amplifier classes labeled by alphabet. Not all letters in between are amplifier classes, not all are even RF (they're audio range), and we might even argue about whether thats how a particular class is defined. But herein lies the fun.

This series is an ambitious undertaking and will take many articles to cover to the level of depth I envision. It might happen that each of these articles takes longer than one week to write, and are published across different time intervals, not necessarily in linear fashion. Please consider subscribing to the newsletter to have all posts delivered to you.

Thanks for reading Vik's Newsletter! Subscribe for free to receive new posts and support my work.

It is not easy to define a specific power level after which an amplifier becomes a "power amplifier (PA)." For example, a cell phone amplifier outputs about 1 watt, audio amplifiers output hundreds of watts, while low power bluetooth circuits might output only 10 milliwatts. An amplifier at any output power can be made to operate in different classes, depending on the needs of the application and the performance we desire from it.

Before we dive into the deep end, we need to set the stage with the proper concepts that we will constantly mention in this series. These ideas are the foundations on which we will build upon. As simple as some of these topics might seem, it is still worth dedicating a post to. 

**Specifically, we will cover:**

- IV-relationship of an active device
    
- Load lines (DC / AC / static / dynamic)
    
- Conduction angle
    
- Efficiency
    

**Read Time**: 9 mins

---

### Current-Voltage (IV) Relation of an Active Device

First, we need to understand the ideal operating behavior of an active, amplifying device. This is the foundation on which amplifier classes and operation will be defined.

In general, an active transistor generates current when a voltage is applied to it. For a bipolar transistor with a voltage at its collector, injecting a base current results in a large collector current. The ratio of collector current to base current is called the _current gain_, β. Bipolar junction transistors can be made on silicon, or they can employ heterojunctions such as Silicon-Germanium (SiGe) or Gallium Arsenide (GaAs). 

For a field-effect transistor (FET) with a voltage at the drain, increasing the gate voltage above a threshold value causes drain current to flow. The amount of drain current for a change in gate voltage is called _transconductance_ (often represented as gm). The FET can be made on silicon, such as a bulk-silicon or silicon-on-insulator (SOI), or it can be made on GaAs using pseudomorphic high-electron mobility transistors (pHEMTs). A more recent development involves the use of Gallium Nitride (GaN) FETs, which provide high power operation.

The current-voltage relationship of an ideal MOSFET looks like in the figure below. A similar characteristic can be drawn for bipolar transistors.
![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F25696dbc-e0bc-4d68-8a8d-11e23321ae24_1173x378.heic)

Real devices do not behave in such an ideal fashion, but we will describe transistor operation in a simple way, so we can keep our eye on the prize - amplifier classes. 

- Vk is the _knee voltage_, after which increasing drain voltage will not increase the current because it is in _saturation_. Below knee voltage, the device is basically a gate-voltage controlled resistor.
    
- Vt is the _threshold voltage_ on the gate, which is the minimum value of voltage needed to make the device conduct. Below this value, the device will be in the _cut-off region_, and there will be no current. For a given drain voltage, increasing gate voltage beyond _saturation voltage (_Vsat_)_ will not increase drain current.
    
- Imax is the maximum value of current that the device is capable of supplying.
    
- When the device is above cut-off but hasn't its maximum drain current Imax yet, the device is said to operating in the _quasi-linear_ region.
    

Ideally, we want a device that can provide a high value of Imax, have a low knee voltage, and equally spaced, flat lines on the Id-Vd space as the gate voltage is increased. In the Id-Vg space, we want a linear relationship between current and gate voltage in the quasi-linear region.

### Load Line

An amplifying device converts the output current into a voltage only when a load is placed at its output. The choice of this load affects the voltage-gain and total power extracted from the output of the transistor. On the IV space, the _load-line_ is a diagonal line whose slope depends on the load value.

In reality, the load is a complex value and is constructed as a combination of inductors, capacitors, transformers and resistors. As a result, the _AC load line_ is usually different from the _DC load line_ because the presence of reactive elements results in a different load line that varies with frequency compared to a purely resistive DC load.

![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F9babc65d-ac06-4323-8ac6-df07f2f4ed28_1052x351.heic)

The load network is a usually a carefully designed, complex impedance. There are two fundamental methods to design load networks (although it can get very complicated in actual amplifier designs):

- **Conjugate Match**: The load impedance is designed to be the complex conjugate of the device output impedance. 
    
    - This provides maximum power transfer from the device to the load _provided that the active device has_ **_no limitations_** _on the power it can deliver_. 
        
    - This is usually not an issue for low-power amplifiers because the devices are not pushed to deliver high power. They can always deliver the instantaneous current and voltage expected of them. As a result, a conjugate match is usually the right choice for the load.
        
- **Power Match**: The load impedance is designed to deliver maximum power to the load, _while considering the power limitations of the device_. 
    
    - This is usually not the complex conjugate of the device impedance. Even if the complex conjugate ensures maximum power transfer from the device, it will not be possible if the device is required to deliver more instantaneous voltage and current than it is capable of. Due to power limitations imposed by the device, the power delivered will drop. 
        
    - Instead, there is another optimal impedance called the _power_ match that will ensure maximum power at the output while taking power limitations of the device into account. This is often experimentally determined with a special measurement called _load-pull_.
        

As an aside, in an earlier article, we looked in-depth into how various input and output match conditions define the gain from an amplifying circuit. Give it a read.
### Static and Dynamic Bias Point

A classical amplifier that uses an amplifying device with a load at its output, is biased at a specific voltage and current setting called its _quiescent bias point_, that lies on the load-line. This is a very important choice for amplifier operation, and we will see why when we define various amplifier classes later in this series.

If the amplitude of the input RF signal is low enough and gain isn't too terribly high, the devices might not be sufficiently disturbed from their quiescent bias condition. It can be considered to be _static_ during amplifier operation. This is usually the case in low power amplifiers, such as low-noise amplifiers. 

For medium and high-power amplifiers, the bias point will move with the input RF signal, or if the output signal swing is high enough, with the output RF signal. In such a scenario, we need to think of a dynamic IV space where the bias point will instantaneously reside during the process of amplifying an RF signal. This complicates matters because:

1. the amplifier operation starts being non-linear
    
2. the IV behavior itself might change based on the previous bias point it was in (this is called memory effect). 
    

We won't get into all the complexities right away, but it is useful to form a clear mental picture of what goes on at a device level.
![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fa15c606b-ade4-4aa6-a686-bbda53436c70_864x350.heic)
### Conduction Angle

A common approach to classifying amplifier operation is based on _conduction angle_.

> Conduction angle is the total phase angle of a sinusoidal signal for which the transistor is kept in operation, or equivalently, in conduction, where it consumes DC power.

If the transistor is always conducting for all phases of the input sinusoidal signal, the _conduction angle_ is 360 degrees. If the transistor is placed in cutoff for part of the signal cycle, then the conduction angle will be _less than_ 360 degrees.

Depending on how long the transistor is kept conducting, we will later classify amplifier operation into class A, B, C, and so on. The main idea behind turning off transistors for part of the time is to save on DC power dissipation, and improve efficiency of the amplifier (we’ll discuss this next). While efficiency improves when transistors are partially turned off, the output signal is more distorted. There is a constant trade-off between linearity and efficiency.

![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F0852e6b9-9500-43e9-9903-349704d18712_799x287.heic)

Red shows where the transistor is conducting.

### Efficiency

Efficiency is a metric of great importance for a power amplifier, and is loosely a measure of how much of the supplied DC power is converted to RF power at the output. An efficient amplifier converts most the supplied power into RF, and implies better battery life for handheld devices, and lower heat generation in the active devices.

There are two important efficiency metrics we need to define:

- **Power Added Efficiency (PAE)**: It is the ratio of the output RF power after accounting for the gain of the amplifier, to the DC power supplied to the amplifier. This is a more general definition that is applicable to all amplifiers regardless of their gain level.
    
- **Drain Efficiency (DE)**: It is the ratio of the output RF power to the DC power supplied to the amplifier. This definition is valid only when the gain is sufficiently high such that the output power is much higher than the input power. For example, drain efficiency approaches PAE when the gain is 1000x (or 30 dB), in which case, ignoring the input power is a negligible source of error.

![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F830a6c18-4976-40e6-b407-f5c56fd2b7dd_775x98.heic)

Many engineers and even vendors erroneously use these efficiency definitions interchangeably regardless of amplifier gain. So always make sure to clarify with your colleagues or vendors what efficiency definition being referred to.

While this article might seem like a collection of partially connected concepts, they will come together when we discuss class A amplifiers in the next article.

See you then.

**~END OF ARTICLE~**
# Part 2: Class A Amplifier

In this article, we will look at the Class A amplifier. It is a classical linear amplifier that delivers a faithful amplified version of the input signal.

The last article setup the foundational ideas we will use to discuss amplifier classes. Here's a quick summary:
1. An amplifier requires an active device biased at a given current and voltage called its quiescent bias point or Q-point.
2. The input and output loads presented to the active device determine the amplifier performance.
3. Amplifiers are classified according to their output waveform.
4. There is always a trade-off between linearity and efficiency.

*Insert previous article*

In this post, we will discuss the following:
- thing1
- thing2
- thing3

Read time: X mins

### The Common-Source Class A Amplifier

Class A amplifiers are ideal for applications where linear amplification is most important, not efficiency. One such use-case is the low-noise amplifier (LNA), whose purpose is to amplify the weak signal received from an antenna to a reasonable level for post-processing by the receiver chain. 

When faithful amplification of the input signal is the primary goal, a class A FET amplifier design shown below, is often a common choice. 

*Insert picture of class A schematic and bias point on IV*

The circuit shows a common-source amplifier, where the "common" refers to the terminal to which gate and drain voltages are referred to. When source is the common terminal, any mention of gate or drain voltage really refers to the voltage between the gate-source or drain-source terminals (Vgs/Vds).

Here is an explanation of the schematic:

- On the gate input side of the amplifier is a source resistance RS and a time-varying signal that requires amplification. 
- On the drain output side of the amplifier is a load resistance RL to which amplified power is delivered.
- On both the input and output sides are matching networks that convert RS and RL into a complex impedance that is presented to the gate and drain terminals of the device.
- There are bias generation circuits on the gate and drain that provide a gate voltage (VG) and a drain voltage (VD) to appropriately bias the FET device. 

To make this circuit operate as a Class A amplifier, we need to bias the FET device so that the output waveform has as little distortion as possible.
### Biasing for Class A

Setting the quiescent bias point (Q-point) of the active device for Class A operation entirely depends on its current-voltage (IV) characteristics. The basis for doing so is simply stated as

> Choose Q-point so that instantaneous voltage and current in the device stays in quasi-linear (or active) region of operation.

*put picture of transistor in class A operation using only IV curves*

From the IV space of the device, we can set voltages as follows:
- Choose a drain voltage VD such that its instantaneous value during amplification will not exceed the maximum allowed drain voltage. 
- Choose a gate voltage VG so that the instantaneous current will not exceed the maximum drain current (Imax) supported by the device. For this, we will need a gate voltage that establishes a quiescent current of Imax/2 so that the signal swing can utilize the entire linear range of output current, without being limited by the cutoff region, or Imax of the device. 
The result of these choices is that the Q-point often lies smack dab in the middle of the IV space that offers linear operation.

You can probably see how choosing the biasing condition is a chicken-or-the-egg problem. The voltage gain depends on the Q-point. However, choosing Q-point requires the voltage gain to be known. As a result, choosing Q-point is an iterative design process.

### Conduction Angles and Power Efficiency

The output current and voltage waveforms shown below will help calculate some important properties of Class A amplifiers. For all phases of the input sinusoidal signal, the transistor stays biased at its Q-point and conducting all the time. 

> The conduction angle for a Class A amplifier is 360°

The voltage and current waveforms are opposite in phase. This is consistent with the assumption that voltage goes up at the output terminal when current comes out of the device.

*draw instantaneous voltage, current, and power graphs*

To find out how efficient a Class A amplifier is, we need to calculate how much RF power is generated for a given DC power. Instantaneous RF power is calculated as:
$$
P_{rf}=v_0\sin \theta \times i_0\sin \theta 
$$
The average power over a full sinusoid cycle is
$$
P_{rf,av} = \frac{1}{2\pi}\int_0^{2\pi}{v_o i_o \sin^2 \theta}d\theta = \frac{1}{2}v_o i_o
$$
From our choice of Q-point, the peak voltage of the AC signal is 2VD, which is a voltage VD above the Q-point. So the instantaneous maximum voltage is vo=VD.

The peak current of the AC signal is Imax, which is Imax/2 above the Q-point. So the instantaneous maximum current in io=Imax/2.

The average RF power delivered is then,
$$
P_{rf,av} = \frac{1}{2}V_D \frac{I_{max}}{2}=
$$


## Circuit Example

A simple emitter/source follower is a good example of a class A amplifier. 







