---
title: "reduced conduction angle - output current derivation"
created: 2023-05-05 09:25
status: #permanent
tags: #ee/amplifiers
---

Compared to a [[permanent/class A linear amplifier|class A amplifier]], the device is biased at a voltage $V_q$, that is closer to cut off. As a result, when the input signal goes below cutoff, there is no conduction at the output. The total part of the cycle of the input signal where the device is conducting is called the *conduction angle $\alpha$*. The lower the voltage $V_q$, the lower the conduction angle.

For the current to swing up to the equivalent current $I_{max}$ of the class A condition, the input drive needs to be stronger. The output current in the figure below is shown as a cosine function for ease of analysis.

![[permanent/Pasted image 20230505092738.png|400]]

The RF current waveform during conduction cycle can be written as:
$$
i_d(\theta)=I_q+I_{pk}.cos(\theta)
$$
where, $I_{pk}=I_{max}-I_q$.

At the end of the conduction cycle, at $\theta=\alpha/2$,
$$
I_q + I_{pk}.cos(\alpha/2) = 0
$$
or, 
$$
cos(\alpha/2)=-I_q/I_{pk}
$$
and substituting for $I_{pk}$,
$$
cos(\alpha/2)=\frac{I_q}{I_q-I_{max}}
$$
solving for $I_q$,
$$
I_q = \frac{I_{max}.cos(\alpha/2)}{cos(\alpha/2)-1}
$$
Now, we can write $i_d(\theta)$ only in terms of $I_{max}$ as,
$$
i_d(\theta)= I_{max}\frac{cos(\theta)-cos(\alpha/2)}{1-cos(\alpha/2)}
$$

This is the expression for output current as a function of angle, that will be used to separate the various classes of amplifier operation.

## References
- Steve Cripps - RF Power Amplifiers for Wireless Communications Chap 3.2