---
title: Terminology Every RF Engineer should know
tags:
  - fundamentals
project: substack
date_published: 
status: 🚧
final title: 5 Key Concepts Every RF Engineer should know
---
_Hey, I’m Vikram 👋 and thanks for reading!_ 

_Reply to this email and let me know about questions you have, topics you’d like to see or challenges you are facing. The feedback will help me improve the content quality. Even a few sentences will do! I reply to every email. 📝_

_You can also reach me on [LinkedIn](https://www.linkedin.com/in/vikramsekar/)/[X](https://twitter.com/vikramskr). I highly recommend joining the community on the Substack chat.

_If you like these articles, please let others know. Word of mouth helps grow this newsletter! 🙏_

This article explains a list of terminology or key metrics you will use in the design of most RF systems. Knowing their definitions is key to system design, or even understanding the data sheets of various RF components. This list is by no means exhaustive. It is often the most used in microwave engineering, but there are a lot of terms you will come across.

### 1. Gain

As opposed to voltage gain that you often see defined in operational amplifiers, in microwave engineering, we commonly deal with power gain. It is simply defined as

> the ratio of the power at the output to the power at the input

It is commonly expressed in decibels or dB. There are various definitions of power gain depending on what you consider the input and output in a system, especially when talking about amplifiers. Check out my earlier [detailed post] on that topic.

When gain is above 0 dB (or 1), there is signal amplification which is often the case when working with active devices such as amplifiers and mixers. If gain is below 0 dB (or between 0 and 1), there is insertion loss which is characteristic of passive devices like filters or attenuators. 

### 2. Compression Point

A linear amplifier will faithfully increase the level of the input signal without modifying the output waveform. However, components that use active devices for amplification or mixing are inherently nonlinear. 

One source of nonlinearity is the voltage-dependent capacitors arising from semiconductor junctions in a transistor which cause distortions of the output signal depending on the level of the input signal.

Let's think of this in the frequency domain. If you inject an amplifier with a pure signal at only one frequency, you would expect a higher output power at the same frequency and nothing else. This is almost true at a low input signal level, and we refer to this value as linear gain.

As you raise the level of the input signal, distortions in the active device start to increase the level of harmonics at the output and power is transferred from the fundamental tone to the harmonic frequencies. The output power level at the fundamental frequency starts to drop, giving lower gain at fundamental. 

> The power level at the input or output at which the gain of the active device reaches 1 dB below linear gain is called compression point.

The choice of 1 dB is fairly arbitrary. Engineers use 0.1 dB or even 4 dB on occasion.
### 3. Linearity

Instead of characterizing an RF component with a single frequency tone, linearity is measured by injecting two closely spaced frequencies into an RF component. 

The reason for this is to evaluate the response of a component to an in-band interference closely spaced to the desired channel. In-band interference, as we discussed in a [previous post], cannot be easily filtered by the RF front end due to limited filter selectivity. The RF component needs to tolerate the neighboring interference without irrecoverably destroying the desired signal.

At the output, both fundamental tones are amplified to a higher level depending on the gain. In addition, power is generated in new frequency components due to the nonlinearity of the circuit. These new components are called intermodulation (IM) products.

IM products are a result of the mixing of two signals in a nonlinear system. With some trigonometry, it is possible to show that each of these IM products occur at a combination of the frequencies of the input tones. For simplicity, Fig? lists out the frequencies of the first five IM tones generated from a nonlinear mixing process.

As the input power is increased, the level of IM products also increase at a rate that depends on the order of nonlinearity. The 2nd order IM product will increase twice as fast as the fundamental, the 3rd order thrice as fast and so on. 

Now we can define the most common linearity metric, intercept point (IP), as:

> The input or output power level at which the Nth order IM product has the same power level as the fundamental tone is called the N-th order intercept point (IPN)

When referred to the input or output power, the linearity is called Input Intercept Point (IIP), or Output Intercept Point (OIP). It is quite common to look at the 2nd and 3rd IM products for amplifiers and mixers, and their corresponding linearity metrics will be listed as IIP2, OIP2, IIP3, and OIP3. The output and input referred intercept points only differ by the gain of the circuit.

To measure intercept point, the input level cannot be increased to the point where the IM product has the same power as the fundamental tone. This is often too much power for the component to handle, and it would reach compression much before all this or get irreparably damaged.

Intercept points are always extracted from extrapolating a few measurements at low input power, fitting a line through the measurements and finding where these lines intersect. For convenience, many measurements in industry as made at a single input power, and intercept points are calculated assuming a 2:1 or 3:1 slope for 2nd and 3rd order components respectively. This is a matter of simple algebra, and the several handy equations are listed in Fig? should you need to use them.

Interestingly, the 1-dB compression point and IIP3 points are related on a first order basis. The 1-dB compression usually occurs about 10 dB before the IIP3. This can be 12-13 dB at times, but it serves as a good sanity check in practice to verify either measurement. If you are interested in why there is a 10 dB difference, check this out.
### 4. Noise Factor or Figure

While there is noise received by the antenna in a communication system, each component in the receiver adds its own noise. The noise could be from various sources such as thermal noise, 1/f noise, phase noise or shot noise. Regardless of what the underlying source is, noise factor is a metric that defines the noise added by any circuit in the system based on signal-to-noise ratio (SNR):

> Noise factor is defined as the ratio of the SNR at the input to the SNR at the output of a circuit. When expressed in decibels, it is called noise figure.

For reasons we will see in a future article, it is critical that the noise figure of any circuit that comes before the low-noise amplifier be as low as possible. Once the signal is amplified, the noise figure of subsequent blocks in the system becomes less important.

In fact, a passive component like a filter can be assigned a noise figure equal to its insertion loss because the SNR degrades due to signal loss even if minimal noise is being added. As a result, it is important that any system components before the amplifier also has low loss. 

This is the main reason that RF switches are implemented with silicon-on-insulator technology and low loss SAW/BAW filters are used in the RF front end. We discussed this in a [previous article].

### 5. Efficiency

While the term efficiency can be used in many contexts in an RF system, we will talk about two common ones: (1) Antenna (2) Power amplifier.

> The antenna or radiation efficiency of an antenna refers to the ratio of the radiated power from the antenna to the power applied at its input terminals. 

It can be expressed in percent (like 50%) or in decibels (-3 dB). Conductor and dielectric losses in an antenna contribute to loss of efficiency in an antenna.

Radiation efficiency assumes that the antenna is perfectly matched, but in practice, there are always mismatch losses at the input. When the radiation efficiency is multiplied by the mismatch (a number between 0 and 1), it is called total efficiency of the antenna. In practice, total efficiency is always less than radiation efficiency.

In a power amplifier, efficiency refers to the ratio of the RF power delivered at the output to the DC power used to do it. Any loss of efficiency is due to energy dissipation due to heat.

You will commonly encounter two different efficiency definitions:

##### Drain/Collector Efficiency 

This efficiency definition stems from the calculation of power at the output terminal of an amplifying device and is a commonly used figure of merit in power transistors. The drain and collector are the output terminals of FET and Bipolar transistors.

> Drain/Collector efficiency is the ratio of the RF power at the output terminal to the DC power supplied to it.

In general, this definition of efficiency does not take input power into account. Depending on the gain of the amplifying device, this definition is misleading because the power transistor can have zero gain but high drain efficiency. This only means that all the input power is simply transferred to the output without amplification. You will still end up with a high efficiency number. 

If the amplifying device has a sufficiently high gain (> 30dB or 1000 times), then the input power is negligible compared to the output power and drain/collector efficiency is a useful and reasonable efficiency metric. 

There are other practical uses to this definition. In a multi-stage power amplifier, it is usually the output stage that has the highest efficiency. But it is difficult to measure how much input power is fed into it because it is integrated with other amplifying stages. In such a case, it is only reasonable to calculate efficiency from the output power alone. It is quite likely that gain is sufficiently high in a multi-stage amplifier anyway.
##### Power Added Efficiency (PAE)

Power added efficiency or PAE is a much better definition for lower gain amplifiers, and is defined as:

> Power added efficiency is the ratio of the amount of excess power generated by the amplifier relative to the input power, to its DC power consumption.

By accounting for the input power in the calculation, we take into account the gain of the device as well. A low gain device cannot have a great efficiency, since after all, not much amplification is happening. for the DC power being consumed. 

Again for sufficiently high gain (>30 dB), the drain/collector efficiency and PAE should be quite close. PAE can also be calculated from drain efficiency if the gain G is known according to (formula).


