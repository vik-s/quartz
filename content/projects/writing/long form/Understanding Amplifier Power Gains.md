---
title: Understanding Amplifier Gains
tags:
  - fundamentals
project: substack
date_published: 
status: 🚧
final title:
---
1. ﻿﻿﻿What is the most important point?
	1. To understand the various kinds of gain, when and where to use them.
2. ﻿﻿﻿Why is that the most important point? (what can you achieve with it)
	1. To fully understand what kind of performance an active device can provide
3. ﻿﻿﻿Why should people care? (what's the benefit)
	1. People can choose the correct technology if they understand it well
	2. Be more precise in understanding vendor datasheets
4. ﻿﻿﻿What is the easiest way to understand the most important point?
	1. Provide a visual that someone can pin up in their cubicle that tells you what gain is what
5. ﻿﻿﻿How do you want the reader to feel?
	1. Like they now clearly understand amplifier gains
	2. Happy they got a resource they can use at work
6. ﻿﻿﻿What should the reader do next?
	1. Share my visual and post on social media
	2. see if you can leave them with a small puzzle / homework problem?

*Section 4.6 from Rohde*
- 50ohm transducer gain is the smallest gain when no matching circuits are used (?)
- Masons gain is the highest gain obtainable from the device by lossless feedback and matching
	- People rarely design for unilateral gain because
		- It is narrow band
		- very sensitive to s-parameter accuracy, esp S12, which is very small.
		- hard to achieve stability at all frequencies in unilateral amplifier
		- it is only a figure of merit quoted by the manufacturer
- Table 4.5 shows 9 power gains with their equations
- Fig 4.10 shows various power gains vs freq, and what is higher and lower that what
- Otherwise this section of the book provides very little insight into what all this means

*Section 8.2.1 from Rohde*
- If k>1, both ports of the transistor can be conjugately matched to achieved G_ma, the maximum available gain.
- If k<1, carefully extract G_ms, max stable gain and stability across all frequencies
- A common misconception is that if k<1, then the max gain is G_ms. That is not true. The correct answer is infinity since the transistor may oscillate and deliver RF output power with only noise as input.
- A better way to interpret G_ms is to consider loading the transistor resistively till k=1, then match the two-port simultaneously. Then the gain in G_ms.
- This is not the recommended way to design amplifier because adding resistors usually degrades amplifier performance.
- The preferred way is to design the reflection coefficients looking into the source and load to be in the stable regions without adding resistors.

*Section 8.2.2 from Rohde*
- Gma is the gain, when k>1, and input and output are conjugately matched. The S11 and S22 values are zero. Gma_reverse can be used to specify the gain in reverse, and is related to S12.
- To push the gain beyond Gma, you need to unilateralize the 2-port with lossless feedback. The S11, S12, and S22 for this amplifier are zero. This gives Masons Unilateral gain and is the highest achievable *stable* gain at this frequency.
- The gain formulas usually only give the magnitude. The phase of the S21 will depend on the implementation on matching circuits, and there is no unique answer for phase S21 in the calculation of Gma.
- Fmax is the frequency where Masons gain is unity. Beyond fmax, the transistor is a passive component. It is also called maximum frequency of oscillation (probably because you need the device to still be active to create an oscillator)

----

Transducer gain, power gain, available gain and unilateral gain.

I've always had trouble quickly remembering what each of these two port amplifier gains mean, what reference planes define input and output power, what the matching conditions are, and what are the assumptions made.

In this article, I hope to create a reference we can quickly use whenever we need to work with these gains. The purpose is avoid complex derivations and provide only the relevant formulas you can use for calculation. The references at the end will have more comprehensive resources on the subject.

You will learn the following:

- Definitions of each of the power terms
- Formula to calculate them
- others?

Let's dive in!

**The two port amplifier network**
The simplest two port amplifier is shown in Fig. 1. It consists of an active device that is capable of amplification and matching networks at the input and output. The purpose of the matching networks is to present a specific impedance at the device terminals for optimal operation. To do this, matching networks are usually implemented with passive elements such as inductors, resistors, capacitors and transformers. In this article, we will consider these matching networks to be lossless.

The purpose of this network is to amplify any RF signal at the input so that the output signal has a higher voltage swing or absolute power compared to the input signal. The ratio of output power to the input power is called gain. Depending on which point in this diagram you define as input and output, you can have different definitions of gain.
*add fig1*
Before we get to that, we need to clearly define the terminology we will use.

**Impedance definitions**
Fig 2 shows all the impedance definitions in the two port amplifier.  We will address each one in detail.
*add fig2*

*Source and Load impedance*
The use of an input matching network transforms the reference impedance Z0 of the system into a different impedance we can represent as ZS looking into the output of the matching network towards the signal source. The act of matching the input of an amplifier is choosing the proper value of ZS to meet the design specifications. Usually, ZS affects the gain and noise performance of the amplifier and appropriate trade-offs are usually made. The source reflection coefficient can be written as
*put eqn for GammaS*

Similar to the source impedance, the output matching network transforms the reference impedance Z0 into an impedance we can represent as ZL, looking into the input terminal of the output matching network towards the load impedance. To match the output of the amplifier, a proper value of ZL needs to be chosen. Depending on the application, i.e., where it is a low noise amplifier, high power amplifier or anything in between, the design of the output matching network can get quite sophisticated to meet the end requirements of the amplifier. The load reflection coefficient can be written as
*eqn for GammaL*

*Device Input and Output impedance*
The impedance looking into the terminals of the active device is affected by both the s-parameters of the device itself *and* the matching network down the chain from the device. Specifically:
- Input impedance ZS is affected by the device s-parameters and output matching network and can be calculated by *eqn for Gamma_in*
- Output impedance ZL is affected by the device s-parameters and the input matching network and can be calculated by *eqn for Gamma_out*

It is interesting that if the active device is "unilateral" which means there is no transfer of power from output to input, then S12=0. The input and output reflection coefficients reduce to S11 and S22 respectively. This is important for when we define "Unilateral Gain" of an amplifier later.

**Power Definitions**
Whenever there is an impedance mismatch between a matching network and an active device terminal, some of the RF power is reflected and some of it is transmitted. Only under specific matching conditions where the source/load impedance is a complex conjugate of the device impedance, will there be maximum power transfer. This is called conjugate matching. 

When amplifiers have an arbitrary source/load impedance, there will be different power levels at different points in the two port amplifier network. Fig 3 shows all the power definitions in a two port amplifier. Understanding these will be key to defining various amplifier gains in the next section.

- Power available from the source (Pavs): Maximum power that can be delivered to the active device from the source. This is only possible when the source impedance ZS is chosen to be the complex conjugate of input impedance Zin looking into the device.
- Power delivered to the input (Pin): Power delivered to the input terminals of the active device. This does not make any assumptions about the input matching network. For any arbitrary ZS, there will be some reflected power back into the source, and the rest of the power delivered to the device is Pin. Pin is always less than or equal (under conjugate match) to Pavs.
- Power available from the network (Pavn):  Maximum power available from the output device terminal after amplification that can be delivered to the load. If the output impedance ZL is a complex conjugate of Zout, the impedance at the output of the device terminal, then this is the maximum power that can actually be delivered to the load.
- Power delivered to the load (PL): Depending on the choice of output matching network and ZL, some power may be reflected back into the output device terminal, and the rest of it is transmitted to the load. This is the actual power delivered to the load circuit. PL is always less than or equal (under conjugate match) to Pavn.

*add fig3*

**Transducer power gain

Transducer power gain is defined as
> The ratio of the power delivered to the load to the power available from the source.

This is the most general and highly used definition of power gain in a two port amplifier. It makes no assumptions on the source and load impedances, or the behavior of the active device.

Fig 4 shows the reference planes and the formula to calculate the transducer power gain in a two port amplifier.

*add fig4*

Even though there is no explicit dependence of the gain on S12, remember that it is included in the calculation of Gamma_in from equation (3). The makes it a general definition of gain under all circumstances.

In the absence of matching networks, ZS = ZL = 50 ohms, or GammaS = GammaL = 0 (from equations (1) and (2)). In this case, the transducer power gain reduces to 

*add eqn*

This is the lowest possible gain you can obtain from the amplifier. Addition of any matching circuits will increase the power delivered to the active device and the load, hence increasing the gain.

Another useful approximation is to assume that S12=0. This is a reasonable assumption for many transistor devices whose reverse transmission is negligibly low. Under this condition, Gamma_in = S11 (from equation 3), which gives us a way to calculate the transducer power gain of an amplifier from only the s-parameters of the transistor and source/load reflection coefficients of the matching networks. 

Additionally, you can rather conveniently view the overall gain as a cascade of the gains of the source match, intrinsic device and load match.

*add eqn*

To find the maximum unilateral transducer gain (GTUmax), the input and output needs to be conjugately matched, and by setting Gamma_in = S11* and Gamma_2 = S22*, we get

*add eqn*

**Power Gain**
Power gain is defined as
> The ratio of the power delivered to the load to the power delivered to the input of the active device.

The gain definition will vary depending on the load matching network, but is independent of the source matching network because any reflections back into the source are already accounted for. In reality, the behavior of the active device depends on the source impedance presented to it, but we won't worry about it for now.

Fig 5 shows the reference planes used for calculation of power gain and the formula to do so.

*add fig and eqn*

Notice that this expression does not contain Gamma_S, making it independent of the source matching network. Power gain tells you how much power will be present at the load in the presence of a matching network when you provide a given power across the input terminals of the device.

If you need to calculate power gain with the source conjugately matched to the input, then it is as simple as setting Gamma_in = S11*. 

**Available Gain**
Available gain is defined as
> The ratio between power available from network to the power available from the source.

Fig 6 shows the reference planes used in the calculation of available gain and the formula used to do so. 

In contrast to power gain which was independent of the source matching network, available gain is independent of the load matching network, as shown in equation (9). Available gain tells you the maximum output power you can get from the device, when you provide all the power from the source to it.

If you need to calculate available gain with the load conjugately matched to the output, then set Gamma_out = S22*. 

**Putting it together**

All these gain definitions are tools to help you estimate if a given active device is suitable to meet the required gain specification from the amplifier and to gauge how hard it is to get that performance.

The first metric to look at while choosing an active device is maximum unilateral transducer gain (GTU,max) which makes the simplistic assumption that S12=0 and conjugate matching at both input and output. It gives you a sense of the power gain that is readily available from the device.

Designers rarely design for unilateral gain because the resulting amplifier is usually narrow band, sensitive to transistor s-parameters (especially S12) and it is hard to achieve stable performance at all frequencies.

By no means is GTU,max the absolute maximum gain possible from the device. With the proper kind of feedback, gain can even be infinite. When a device is pushed into oscillation, it produces output power with only noise power as its input. This results in gain values can exceed GTU,max.

Power gain can help estimate the designed gain while isolating only the load network, while being independent of the source network. Available gain allows you to do the same with the source network, while isolating the load network. They serve as intermediate gain estimates during the design process.

Transducer gain is the only gain that ultimately matters and represents the actual performance that is available from the amplifier in the presence of the actual, optimized source and load networks. This is the value that should ultimately be reported on data sheets.

**Key Takeaways**

There are several definitions of gain for a two port amplifier and understanding them is essential to RF amplifier design.

- Transducer gain: This is the most realistic gain that can be reported for an amplifier that represents its actual performance in an RF system.
- Maximum unilateral transducer gain: This is useful to understand what kind of gain is readily available from a device that has little feedback from output to input, and is conjugately matched.
- Power and Available gain: These are useful to understand the amplifier gain by isolating the source and load networks, and are good for intermediate estimates during the amplifier design process.




*Can you make a chart summarizing all the gains? Use that as key takeaway*

[[Excalidraw/UnderstandingAmplifierGains.excalidraw|UnderstandingAmplifierGains.excalidraw]]

