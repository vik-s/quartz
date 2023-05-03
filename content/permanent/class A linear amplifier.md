---
title: "class A linear amplifier"
created: 2023-05-03 13:27
status: #permanent
tags: #ee/amplifiers
---

Assume that the transistor IV relationship is as shown in the figure below. There is a "linear" characteristic between 0V and 1V, and after 1V, the current is limited to a value Imax.  To achieve perfectly linear distortion free operation, the transistor's operating point must be biased as shown in the picture. 

The RF current can swing by Imax/2 in each half of the sinusoidal signal, and the resulting output power spectrum with be a pure sinusoid with no distortions. In reality, a class A amplifier is weakly nonlinear even at small drive power because the transfer characteristic is not perfectly linear as shown in the dotted line.

![[permanent/Pasted image 20230503132805.png|500]]

In the class A amplifier shown below, it is clear that the optimum power match point (see [[permanent/Loadline match can deliver more output power]]) is when
$$
R_{opt}=V_{dc}(I_{max}/2)
$$
and it will deliver an RF power
$$
P_{opt}=(1/2)V_{dc}I_{dc}
$$

This is a classical class A amplifier with a drain efficiency of 50%.

![[permanent/Pasted image 20230503133238.png]]