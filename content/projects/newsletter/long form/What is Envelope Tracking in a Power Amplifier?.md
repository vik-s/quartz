---
title: What is Envelope Tracking in a Power Amplifier?
tags:
  - circuit
project: substack
date_published: 2023-12-31
status: 🟢
final title: Envelope tracking for efficient power amplifiers
---
Envelope Tracking is a rather recent technology that has made our phones run cooler and batteries last longer. In this article, you will learn the basics of Envelope Tracking: how it works and what the challenges are.

Let's say we have a modulated RF signal going into a power amplifier (PA). Modulation is the process of encoding information into a high frequency signal, and is usually done by changing the amplitude or phase (or both) of the high frequency signal according to the information being encoded. The PA has a supply voltage that provides the DC power needed for amplification. The amplified signal is sent out to the antenna to be broadcast. Think of the power amplifier as a karaoke machine with a DC power adapter.

A key performance metric of a PA is it's efficiency. It is a measure of how much output power is obtained relative to the DC power provided to it. The more the better. Nature usually takes its energy tax, so the output is always lesser than input. Efficiency is always lesser than 100%.

Consider a signal which is only phase modulated. Such signals were common in early communication systems such as GSM. Let's say such a signal input to the PA is within the limits of its power supply voltage. Now imagine you throw a tablecloth over this waveform. The shape of the tablecloth on the top is the envelope of the signal. In this case, the envelope is flat.



The advantage of the envelope not touching the power supply voltage is that the amplification will be linear. If the envelope touches the power supply voltage limit, the output waveform will appear squished at the top and bottom, and the result will be nonlinear. The person you are speaking to on the phone may start to sound like the Terminator.

The disadvantage of the extra room between the envelope and power supply voltage is that the excess is wasted power not being used for amplification and being dissipated as heat.

A simple solution is to increase the level of the input signal so that there is minimum overhead between the envelope and power supply, but still not distorting the output. Now you have minimum energy dissipated as heat, and efficiency is better. This is exactly what was done in early communication systems. The PA is said to running in compression, that is, a signal level that gives maximum efficiency.

Unfortunately, it is not possible to guarantee that the input signal is always at the optimum level. Sometimes it drops, and in that case, the PA is said to be operating in a power "back-off" mode. Now we again have wasted energy from excess overhead, and the PA efficiency drops.

But wait, there's more. Modern communication standards like 4G LTE target high data rates and this requires modulation of both amplitude and phase. Depending on the modulation scheme and end-application, the signal can have large peaks relative to the average level. The metric that describes this property of a modulated signal is Peak to Average Power Ratio (PAPR). It is the power of the signal peaks relative to the average power level, and can be as high as 10 times.

Now our imaginary tablecloth over such a signal is no longer flat. The envelope of this signal is continuously varying.

In this situation, increasing signal level to accommodate the peaks implies that the overhead will be too large for the rest of the signal. You cannot risk distorting the signal by clipping the peaks to minimize wasted power. 

Enter Envelope Tracking (ET).

We can no longer have a constant power supply voltage to the PA. The only way to minimize wasted energy is to continuously change the supply level to just about accommodate the envelope signal. The power supply is now "tracking the envelope" of the input signal.

Here's an analogy to ET. The best way to avoid wasted water while brushing your teeth is to shut off the faucet and turn it on only when needed. The water is our energy and the faucet is the power supply to the PA. Turn on as much of the supply you need, when you need it - and you will keep your efficiency high.

An important feature of ET is that even when the input signal level drops, the efficiency does not degrade like in the case of a fixed power supply PA because the supply voltage will track the lower envelope level ensuring minimal wasted energy. Generally an efficiency of 70-80% can be achieved with ET and it remains relatively constant in power back-off.

To continuously change the PA power supply, we need an "Envelope Amplifier" that takes the digital envelope information directly from the baseband signal processor (the thing thats doing the modulation to begin with) and provides a voltage level that tracks the envelope. Designing an envelope amplifier is a challenge all on its own. You have to guarantee that the voltage it provides can actually keep up with how quickly the envelope varies. If the envelope signal is rapidly changing, it is said to have a high signal bandwidth and the envelope amplifier design gets correspondingly harder.

It is also absolutely critical that the envelope and the modulated input signal are perfectly synchronized. If they are not, then the envelope amplifier will end up providing too little voltage needed to cleanly amplify the input signal, or too much voltage degrading the efficiency. The linearity and efficiency of the PA are both affected.

To ensure time alignment, we can take a digitized sample of the amplified output signal envelope and compare it with the required input signal envelope. If there are differences, then it is possible to digitally alter the input signal envelope so that the output signal matches the desired input signal envelopes. This is called adaptive digital predistortion (DPD).  Usually, this adds cost and complexity to the PA system, but as digital technology scales down, the energy overhead and overall cost of DPD is constantly dropping.

ET PAs have become a reality in cell phones ever since the envelope amplifier could be implemented in CMOS technology. Also, most cell phones today use a simplified form of ET called Average Power Tracking (APT) that tracks the average power instead of the envelope thus easing the requirements of the envelope amplifier. The power supply of your cell phone PA changes even on a second-to-second basis using a DC-DC converter chip to make sure your battery life is prolonged as much as possible.

Do give ET a fleeting thought next time you make a phone call!

## References

https://www.electronics-notes.com/articles/radio/rf-envelope-tracking/what-is-envelope-tracking-basics-primer.php

