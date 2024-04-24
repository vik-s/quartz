---
title: Impairments Dual Conversion Receivers
tags:
  - systems
project: substack
date_published: 
status: 🚧
final title:
---
In the last article, we looked at the how to allocate frequencies in a superheterodyne system. We will need to understand a few more details to round out our understanding of the receiver before moving on to more complex implementations.

In this article, you will learn:
- thing1
- thing2
- thing3

Read time: X minutes

--

Any block in the RF transmit or receive chain such as an amplifier, filter or mixers has three metrics associated with it that are used in design optimization. They are:
- Gain (or attenuation/loss)
- Noise
- Linearity

When designing an RF system, they are all attributed some value depending on what is reasonably achievable in circuit implementation with a given technology. The overall system design often looks something like this.

Put *figure from Matlab RF budget analysis*

If we were to start optimizing such a system, it is important that we understand the three metrics and how they change when blocks are cascaded. Let's dive into each of them in detail. If you find this rather basic, feel free to skip ahead.

### Gain
Gain is the level of the output signal of a block relative to its input signal. When expressed as a ratio of voltages, Vout/Vin, it is called voltage gain. If the input and output impedances are known, they can also be expressed in terms of power ratios, Pout/Pin. In RF engineering, these quantities are often represented in decibels (dB).

Power gain is expressed as
$$
A_P = 10 \log \frac{P_{out}}{P_{in}}
$$
If power is expressed as V-squared over R, then *if input and output resistance R is the same*, we can express voltage gain as
$$
A_V = 20 \log \frac{V_{out}}{V_{in}}
$$
It is important to remember when to use the factor of 10 or 20 when calculating decibels. It depends on whether the input and output is expressed in power or voltage. This often becomes a simple source of error for RF engineers, which is why we are addressing it right at the start.

Also note that both of these quantities are only ratios, and says nothing about how much actual voltage or power is present at the input or output. When talking about absolute terms, we use yet another decibel metric called dBm - decibels over milliwatt.

$$
P_{dBm} = 10 \log\frac{P_{sig}}{1 \text{mW}}
$$
This quantity tells you how much absolute power is present compared to a milliwatt. 30 dBm is 1 Watt of power. Sometimes dBW - decibels over watt is also used, in which case, 0 dBW = 30 dBm.

Consider two RF blocks that are cascaded as shown in the figure below. The voltage or power gain at the output is simply a multiplication of the gains of each individual block. In decibels, gain is the addition of each block. If one or more of the blocks shows attenuation or insertion loss, the "gain" of the block expressed in decibel is negative.

Put *picture of a cascaded gain block*

This makes it quite simple to add and subtract the gain of each block in a cascaded system to calculate overall gain.

### Noise




