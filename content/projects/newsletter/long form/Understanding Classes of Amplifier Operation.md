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
- Common-source Class A amplifier
- Choice of bias conditions and load line
- Load network design
- Peak and back-off efficiency
- Design procedure

**Read time**: X mins

### Common-Source Class A Amplifier

Class A amplifiers are ideal for applications where linear amplification is most important, not efficiency. A class A FET amplifier design shown below.


The circuit shows a common-source amplifier, where the "common" refers to the terminal to which gate and drain voltages are referred to. When source is the common terminal, any mention of gate or drain voltage really refers to the voltage between the gate-source or drain-source terminals (Vgs/Vds).

Here is an explanation of the schematic:

- On the gate input side of the amplifier is a source resistance RS and a time-varying signal that requires amplification. 
- On the drain output side of the amplifier is a load resistance RL to which amplified power is delivered.
- On both the input and output sides are matching networks that convert RS and RL into a complex impedance that is presented to the gate and drain terminals of the device.
- There are bias generation circuits on the gate and drain that provide a gate voltage (VG) and a drain voltage (VD) to appropriately bias the FET device. They are feed through a choke inductor large enough to pass only DC through. DC blocking capacitors allow on RF signals to pass.

To make this circuit operate as a Class A amplifier, we need to bias the FET device so that the output waveform has as little distortion as possible.
### Biasing and Load Line for Class A

Setting the quiescent bias point (Q-point) of the active device for Class A operation entirely depends on its current-voltage (IV) characteristics. The basis for doing so is stated as:

> Choose Q-point so that instantaneous voltage and current in the device stays in quasi-linear (or active) region of operation.

*put picture of transistor in class A operation using only IV curves*

From the IV space of the device, we can set voltages as follows:
- Choose a drain voltage VD such that its instantaneous value during amplification:
	- will not exceed the maximum allowed drain voltage
	- will not put the transistor drain below knee-voltage, where it is primarily a voltage controlled resistor (keeps it in saturation)
- Choose a gate voltage VG so that the instantaneous current:
	- will not exceed the maximum drain current (Imax) supported by the device
	- will not drop to zero due to device entering cut-off

The result of these choices is that the Q-point often lies smack dab in the middle of the IV space that offers linear operation. VD is chosen to about half the maximum voltage tolerated by the transistor. VG is chosen so that the quiescent drain current is about half the maximum current supported by the device (Imax/2).

The next question is what kind of load should be presented at the output. If the drain voltage is VD and the drain current is Imax/2, then the optimum load resistance is
$$
R_{opt}=\frac{V_D}{I_{max}/2}
$$
If the device has a non-zero knee voltage Vk, then the optimum resistance can be modified as
$$
R_{opt}=\frac{V_D-V_k}{I_{max}/2}
$$
### Load Network Design

Now that we know the optimum load that should be presented to the output of the transistor, we need to create a matching network that synthesizes this load.

It might be tempting to think that all we need is a conjugate match at the output. This is true if gain is the only metric we are looking to optimize. In the case of a class A PA, our goal is to maximize the output power. For this we need a power match, which is what the calculation of Ropt is. It is quite unlikely that Ropt will be close to 50 ohms, and will therefore result in mismatch (poor return loss) at the output of the amplifier. We will revisit this point in a bit more detail later.

Load matching networks are usually implemented with lumped element or transmission-line based elements to manufacture the required impedances. These networks are inherently frequency limiting, and as a result, the amplifier tends to operate well in a finite bandwidth around a center frequency.

The losses in impedance matching networks also reduce the overall efficiency of the amplifier, and therefore a lot of effort is put into reducing the losses and improving the quality factor of passive components in power amplifiers.
### Conduction Angles and Power Efficiency

The output current and voltage waveforms shown below will help calculate some important properties of Class A amplifiers. For all phases of the input sinusoidal signal, the transistor stays biased at its Q-point and conducting all the time. 

> The conduction angle for a Class A amplifier is 360°

The voltage and current waveforms are opposite in phase. This is consistent with the assumption that voltage goes up at the output terminal when current comes out of the device.

*draw instantaneous voltage, current, and power graphs*

To find out how efficient a Class A amplifier is, we need to calculate how much RF power is generated for a given DC power. Instantaneous RF power is calculated as:
$$
P_{rf}=v_0\sin \theta \times i_0\sin \theta 
$$
The average power over a full sinusoidal cycle is
$$
P_{rf,av} = \frac{1}{2\pi}\int_0^{2\pi}{v_o i_o \sin^2 \theta}d\theta = \frac{1}{2}v_o i_o
$$
So what are the amplitudes vo and io of the sinusoidal waveforms? Remember, we already put the quiescent bias point around the middle of the IV space. Our choice of VD is approximately half the maximum voltage supported by the device. This means that the AC signal can only swing to a maximum level of VD. So, let us set vo=VD.

Similarly, by choosing the DC current level at Imax/2, we can only expect the AC signal to swing another Imax/2 before it reaches it maximum possible value. So, let us set io=Imax/2.

The maximum possible average RF power is therefore only delivered when the input signal swings over the entire range of the allowed input values (not for smaller input signals). It can be expressed as,
$$
P_{rf,max} = \frac{1}{2}V_D \frac{I_{max}}{2}=\frac{V_D I_{max}}{4}
$$
The DC power supplied is simply a product of the Q-point voltage and current.
$$
P_{dc}=\frac{V_D I_{max}}{2}
$$

Computing drain efficiency for a Class A amplifier is now easy.
$$
\eta=\frac{P_{rf,max}}{P_{dc}}\times 100= 50\% 
$$
> The maximum efficiency achievable from a Class A amplifier is 50%

The drain efficiency is same as the power-added-efficiency (PAE) if the gain is high enough (link). But we begin to realize that **half the supplied power is wasted in the pretext of linear amplification**. This is why Class A amplifiers are not the preferred type for applications that rely on battery life. Having a 360° conduction angle continuously burns power in the active device, and lowers efficiency.

In reality, the presence of a non-zero knee-voltage (say Vk is 10% of Vmax of the device) in active device further reduces the maximum efficiency available to about 45%.

### Backoff Efficiency

Notice that we mentioned that maximum efficiency is achieved only when the input drive signal is strong enough to occupy the entire allowable quasi-linear voltage range.

What happens when the input signal levels are reduced, or "backed-off" from the maximum level? This condition might occur if we simply do not want the amplifier to operate at its maximum power output all the time. Emission levels are regulated by the FCC and the radio transmitter is expected to function within those specifications.

Let us recalculate the average RF power output when the voltage and current swing are half the maximum allowed levels. 
$$
P_{rf,backoff} = \frac{(V_D/2)(I_{max}/2)}{4} = \frac{1}{4}\times P_{rf,max}
$$
The output power drops to one-fourth the maximum power value. In terms of decibels, that is a 6 dB drop. This is a commonly used number in power amplifiers, and is called *6-dB backoff*.

If you recalculate it, **Class A efficiency in 6-dB backoff is 12.5%.** This means that 7/8ths of the power is being wasted in the amplifier, and not being used for amplification. That is an unacceptably low level in power amplifiers and we will later see how this is improved in other classes of amplifiers.
### Design Procedure for a Class A Amplifier

How exactly do you go about designing your own Class A power amplifier then? Here's a step-by-step approach:

1. **Identify the active device**: Determine the active transistor you will use. They are often engineered for power amplifier applications to deliver maximum output power. Ensure that your choice of transistor will meet your power needs.
2. **Determine Q-point for Class A**: Look at the current-voltage transfer characteristics of the device and identify the voltage and current range over which your signal will swing. Find a Q-point that ensures that the transistor is always operating in the linear region.
3. **Determine optimum load**: Once you determine the Q-point, calculate the optimal load that needs to be presented to the device. Most often this is a complex number and is a result of load-pull measurements of a device. For a given transistor, you will have an optimum load and bias conditions that will deliver maximum output power. If you are using a discrete transistor, it might be part of the datasheet. In integrated transistors, foundries and internal teams in companies perform measurements to find the optimal load and bias conditions.
4. **Design load network**: If your power amplifier is driving a 50 ohm load, then design a matching network that will transform 50 ohms into the optimum complex load required to power match the device. Make sure you use high quality passives to keep overall efficiency high.
5. **Design input match network**: The input match can be designed based on the principles of low-noise amplifier design. You can find the optimum input impedance to get the best gain using gain circles^[This needs an article on its own^], or if you are not too concerned, a complex conjugate match to the input impedance of the transistor should suffice.
6. **Verify the design**: Once proper biasing and matching networks are designed, verify that the DC operating point, gain, output power and linearity are as expected from circuit simulations.

If you would like a more detailed example of a Class A amplifier design, then check out Chapter 2.7 in "RF Power Amplifiers for Wireless Communications" by Steve C. Cripps (2nd ed.)

### Difference between LNA and Class-A PA 

We should understand the difference between LNA and Class A PA design. Both are linear amplifier designs but serve different purposes.

In LNAs, the main focus is high gain with low noise. This means that the voltage excursions on the device will not span a wide-range in the IV space especially because received signals are usually weak. This means that we will do just fine with a conjugate match at the device output.

In Class A PAs, the focus is on sufficient gain with maximum output power and high efficiency. This means that we operate the device over its entire linear IV space by running the PA at high input signal levels. Since we are always burning power in a PA due to 360° conduction angle, backing off input power will drop efficiency. As a result, we need to have a power match based on an optimal load.

As a result, Class A PAs might not always have the best output return loss because the main intention is to deliver maximum power and not entirely worry about the load impedance. RF systems often use circulators to avoid reflections back into the PA output. Whereas, in LNA design, there is a much higher emphasis on having good output matching.

In the next article, we will see how conduction angle can be reduced to improve amplifier efficiency, while paying the price for linearity.

Stay tuned!

**~END OF ARTICLE~**
# Part 3: Class B Amplifiers

In this article, we will look at the Class B amplifier.

The other articles in this series are listed below, and contains the fundamentals leading up to the discussion in this post. Check them out if you haven't already.

1. Foundations
2. Class A Operation

In this post, we will discuss the following as related to Class B amplifiers:
- Amplifier operation
- Efficiency
- Output harmonics
- Load network (output match, harmonic traps)
- Push-pull amplifiers

**Read time**: X mins

~~
### Class B Amplifier Operation

In the article on Class A amplifiers, we mentioned that the conduction angle is 360°. That is, the transistor is operating in the quasi-linear region for all phases of the input signal.

In Class B operation, we keep the transistor in the quasi-linear operation only for one-half of the input sinusoidal signal. For the other half, the transistor is kept in cut-off and does not provide amplification.

> The conduction angle for a Class B amplifier is 180° or ᴨ radians.

The schematic of a Class B amplifier is shown below, and is fundamentally the same as the Class A amplifier, with slight modifications.
- The output load is modified to have harmonic traps
- The amplifier is often implemented in push-pull configuration (schematic shown later)
We will get into the reasons for both modifications later in this post.
![[projects/newsletter/long form/Understanding Classes of Amplifier Operation 2024-07-20 07.15.02.excalidraw.md#^group=4S9QkDW7IPUtJqystm1CX]]

The main difference lies in where we choose the quiescent bias point for this amplifier class. The Q-point is chosen right at the edge of transistor cutoff. The transistor is driven into conduction by the positive cycle of the input signal, and remains in cut-off during the negative cycle. 

In Class B, the current waveforms in the drain of the transistor are easy to draw since it only conducts in positive half cycles. The voltage will remain at the Q-point VD, till the current flows through the transistor, at which point the voltage drops. Current and voltage are still opposite in phase to each other.
![[projects/newsletter/long form/Understanding Classes of Amplifier Operation 2024-07-20 07.15.02.excalidraw.md#^group=XCHz4_EwD-5FFdRQWgpUr]]

We immediately get a sense that the efficiency should improve because the transistor is kept off half the time. But since only half the sinusoid is amplified, the output waveform is quite distorted degrading the amplifier linearity.
### Class B Efficiency and Backoff
To calculate efficiency of this mode, like we did in Class A, we need a mathematical representation of the current and voltage waveforms. Unfortunately, this is where it gets hairy because half-sinusoids are not mathematically simple. We will deal with them anyway using Taylor series expansions (link).

$$
i_0 = i_0\sin\theta, 0 \le \theta \le \pi
$$

We will make two observations about the output current waveform to make this much simpler immediately.
1. It has no odd-order harmonic components
2. We will remove all the even-order components so we don't have to deal with them (using harmonic shorts, explained later)

Now, the output current equation is much easier to deal with.

*insert simple drain current equation*

It consists of a DC component Io/π and a fundamental frequency time-varying component (Io/2)sinθ, which we can use to calculate load lines and efficiency.

If the maximum amplitude of the half-sinusoid is Imax, then the DC component of the drain current is Imax/π. Remember that the equivalent DC current in Class A was Imax/2. Due to lower DC current, it is apparent that Class B is already more efficient. If the drain voltage is set at VD, then the DC power dissipation is

$$
P_{DC} = \frac{V_DI_{max}}{\pi}
$$
We can calculate the RF power delivered from the time-varying part of the drain current.
$$
P_{RF}=\frac{1}{2\pi}\int_0^\pi{v_oi_osin^2\theta d\theta}=\frac{1}{4}v_oi_o
$$

The maximum RF power delivered is when vo=VD and io=Imax, which gives
$$
P_{RF}=\frac{1}{4}V_DI_{max}
$$
If you compare this with the output power from Class A (link), you will realize that Class B delivers the same output power as Class A. Which is cool if you think about it -- it delivers the same output power while using lower DC power.

So what's the improved efficiency?

$$
\eta = \frac{P_{RF,max}}{P_{DC}} \times 100\% = \frac{\pi}{4} \times 100\% = 78.5\%
$$
> Maximum possible efficiency of Class B operation is 78.5%

This is much better than the Class A value of 50%. We just got this by turning off the transistor for half the cycle, and didn't even affect the output RF power.

This almost feels like free lunch, but we pay in a couple of ways:
1. **Linearity**: The output waveform is not a faithful replica of the input signal anymore. This is not acceptable for most applications. Thus, Class B is often implemented in a push-pull circuit configuration to recover the original sinusoidal waveform, at the cost of increased complexity.
2. **Drive strength**: Input signal to the amplifier needs to be much stronger to drive the output current positive peak to +Imax and the negative peak to -Imax (which will be cutoff anyway). In contrast, Class A amplifier current needs to only swing from 0 to Imax *link*. If the output current has to have twice the peak-to-peak value, then **the drive power requirement for Class B increases four-fold, or 6-dB, over a Class A amplifier**. Needing higher drive strength means that the power-added efficiency (PAE) *link* will drop, as will the power gain, which is not desirable.

A quick recalculation of the efficiency at 25% maximum output power, or 6-dB-backoff condition, where the voltage and current are half their peak values will reveal that **the efficiency of a Class B amplifier at 6-dB back-off is 39.2%.** This is much better than the 12.5% efficiency at 6-dB backoff from a Class A amplifier.

### Output Harmonic Content
While the Class A amplifier provided faithful amplification with near-zero harmonic levels by operating in a quasi-linear region of the transistor, Class B operation generates significant harmonics at the output due to half the waveform being cut off.

We already saw from the drain current Taylor series that all odd-order harmonics will naturally have a zero value. But the even-order harmonics exist.

From the coefficients of the Taylor series, the magnitude of the fundamental and even-order harmonics of the drain current are shown in the table below for up to the 10th harmonic.

*insert table of fundamental and even-order harmonics up to 10th harmonic*

The most dominant harmonic is the 2nd harmonic, while the magnitudes of higher even-order components fall away according to the square of the order. The second harmonic amplitude is the same sign as the fundamental, which means it is in-phase with the fundamental component, while the fourth harmonic is out-of-phase with the fundamental component, and so on.

This second harmonic component, when correctly engineered in a PA, is useful in reducing the drive requirements to the PA. That will be a topic for another day, however.
### Load Network and Harmonic Traps

Up until this point, we have still not discussed how the load line should be determined for a Class B amplifier. This is because the Class A load-line applies to Class B as well. 

The maximum current Imax only flows through the device when the instantaneous VD is low, and relatively close to knee-voltage. Just like in Class A, the load line can be calculated as:
$$
R_{opt} = \frac{V_D-V_k}{I_{max}/2}
$$
Once the optimal load is determined, the output matching network implements it by transformation from a 50-ohm termination, or from the input impedance of the following stage if the amplifier acts as a driver stage. Matching networks can be implemented with lumped passive elements or transmission lines.

Apart from this, remember that we assumed that all even-order harmonics were removed in the analysis of efficiency. The way this is implemented in practice is with a separate network called a *harmonic trap*. 

> A harmonic trap provides a short circuit at a harmonic frequency of operation, effectively removing its contribution to the output waveform.

Ideally, the harmonic trap does not interfere with the output match at fundamental frequency, but this is rarely the case in practice. The interactions will need to be accounted for via circuit simulation.

In integrated circuit designs, harmonic traps are implemented as on-chip LC-resonators, or off-chip with surface-mount components. In hybrid designs (discrete transistor on a printed circuit board, or PCB), a widely used approach is to use a quarter-wavelength (λ0/4) (at fundamental f0) short-circuited stub. This provides two main advantages:
1. It presents an open-circuit at the fundamental frequency f0, making it invisible to the output matching network.
2. It presents a short at 2f0, 4f0, etc., effectively shorting out multiple even order harmonics.

In reality, the bandwidth of the harmonic trap implemented with stubs is eventually limited, with higher characteristic impedance lines providing greater bandwidth. As a result, you will often see harmonic traps implemented as narrow traces meandered on a PCB to save space, in many hybrid PA designs.
*insert picture of harmonic trap implementation using LC or stub*
*can you find a pcb meandered stub implementation of trap?*
### Push-Pull Topology

As we mentioned earlier, the Class B amplifier output is still highly nonlinear due to only the positive half-sinusoid being amplified. A clever solution to improve linearity is the *push-pull* topology for Class B amplifiers.

> A push-pull amplifier design recovers the linearity degradation in Class B amplifiers by amplifying the negative half-sinusoid as well, and combining it with the amplified positive half-sinusoid.

The figure below shows the circuit implementation of a push-pull amplifier. 

*insert picture of push-pull amplifier*

The working principle of a push-pull amplifier is as follows:
- It uses two Class B amplifiers, of which, only one of them actively amplifies the signal at any point in time.
- The input has a *balun* (**bal**anced-**un**balanced) which divides the input signal into two paths which are 180° offset in phase from each other.
- Amplifier 1 only amplifies the positive half-sinusoids
- Amplifier 2 only amplifies the negative half-sinusoids (which are actually positive half-sinusoids after 180° input phase shift)
- The output also has a balun that combines the outputs of amplifiers 1 and 2. Because there is again a 180° shift between the paths, the reconstructed signal is assembled as a pure sinusoidal wave.

The output power and efficiency assuming lossless baluns are the same as a single Class B working on its own because only one of them is amplifying at any given time.

There are two major benefits of using push-pull amplifier topology:

**Wideband operation**: If a wide bandwidth balun can be implemented at the input and output, the push-pull amplifier configuration is capable of very broadband operation. If no harmonic traps are implemented at the outputs of the Class B amplifiers, the push-pull configuration is capable of reconstructing the full input signal at the output, even if it's not sinusoidal. This makes this topology very attractive when high linearity is needed is needed over a broad bandwidth of operation (even up to several octaves of frequency.)

**High input/output impedance**: The input and output impedance of the balun-connected amplifier stages is two-times that of a single ended amplifier. For example, if Ropt is the load-line needed for a single-ended PA, then the push-pull implementation requires 2Ropt. This is a great advantage for high power PAs where the device size is so massive that Ropt is less than 1 ohm. Using a push-pull approach boosts that value so it becomes easier to design matching networks. 

### Difficulty of Push-Pull at RF
Unfortunately, the use of push-pull amplifiers is only widely used at frequencies below about 300 MHz. At GHz frequencies, there is one major limitation that limits the use of push-pull amplifiers: **balun loss**.

At lower frequencies, push-pull implementation is possible due to the availability of toroidal ferrite-core balun-transformers (up to 30 MHz) and coaxial transmission-line based balun-transforms (up to 400 MHz). If you're interested, check out this 700W amplifier from Microsemi that operates from 1 - 52 MHz (thats over a decade of frequency!) and utilizes primarily ferrite based baluns at the input and output.

https://www.microsemi.com/document-portal/doc_view/132525-a-700w-broadband-amplifier-using-vrf2944

Baluns are notoriously difficult to design for high power PA applications at GHz frequencies because dissipative losses wipe out any advantages obtained from a push-pull implementation. That is not to say researchers have not tried to implement push-pull amplifiers at GHz frequencies. In 2020, Maktoomi et al. implemented a microstrip balun design with about 3dB insertion loss and still managed to design a 1.8-2.7 GHz push-pull PA with 60-75% efficiency.

https://ieeexplore.ieee.org/abstract/document/9194327

As a final word, the push-pull topology is not only restricted to Class B amplifiers. The idea can be applied to any reduced conduction angle amplifier to improve the overall linearity and bandwidth of operation.

PS: you never really mentioned cross-over distortion in push-pull. Maybe you can reserve it for the mini ebook or something.

**~~ END OF ARTICLE**

# Part 4: Class AB / C Amplifiers



