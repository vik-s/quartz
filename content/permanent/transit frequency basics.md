---
title: "transit frequency basics"
created: 2023-03-17 08:30
status: #permanent
tags: #ee/rf
---

Transit frequency fT is a measure of the intrinsic speed of a transistor and is defined as:
>[!important] fT is the frequency at which the *small signal current gain* of the device becomes unity

A conceptual measurement setup for fT is shown below:
![[images/ft_measure.png]]

A sinusoidal current $I_{in}$ is injected into the base or gate at a given frequency $f_{in}$, and the resulting output AC current $I_{out}$ is measured, as the frequency is swept.

As the frequency increases, the input impedance $Z_{in}$ decreases and thus more of the current $I_{in}$ is shunted away and not available at the output, thus reducing the current gain. At unity current gain, the device no longer amplifies any input current, and therefore ceases to be useful as an amplifying device.

For an amplifier, current gain is more if the transconductance $g_m$ is higher, and less of it is shunted to ground if the input capacitance $C_{in}$ is low. The transit frequency in radians, is expressed as:
$$
\omega_T = \frac{1}{\tau_T} \approx \frac{gm}{C_{in}}
$$
So far the effects of $C_{bc}$ and $C_{gd}$ are neglected. But it is important to note that collector-substrate or drain-bulk capacitance does not affect fT because there is already an AC ground at the output.

$\tau_T$ is called the transit time of an electron in the channel, i.e., the amount of time it takes to go from source to drain.

# References

- [[literature/B-razavi-microelec]]
- [[permanent/deriving expressions for transit frequency of a MOSFET]]
