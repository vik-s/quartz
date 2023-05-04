---
title: "amplifier output matching for specified power"
created: 2023-05-04 08:02
status: #permanent
tags: #ee/amplifiers
---

In [[permanent/class A linear amplifier]], we saw that there is a specific optimal resistive load that delivers maximum power to the load in a linear class A amplifier.

Let's say that we want a specified power that is lower by a factor $p$, so that $P_o=P_{opt}/p$. There are two resistive terminations that will result in this output power.

![[permanent/Pasted image 20230504080723.png]]

#### CASE 1: $R_{LO}=R_{opt}/p$

When $R_L=R_{LO}$, the current swings to the value of $I_{max}$, so the resulting peak-peak output voltage will be $V_o=2.I_{max}.R_{opt}/p = 2.V_{dc}/p$

#### CASE 2: $R_{HI}=p.R_{opt}$

When $R_L=R_{HI}$, the voltage swings to the value of $V_{ds}$, so the resulting peak-peak output current will be $I_d=2.V_{ds}/(p.R_{opt}) = 2.I_{max}/p$


In both cases, the power delivered to the output is $P_{opt}/p$. You can see on the smith chart that the values of $R_{LO}$ and $R_{HI}$ lie on the real axis. These are two points on the load-pull contour for a given output power.

The circles that pass through the $R_{LO}$ and $R_{HI}$ points are constance resistance and constant conductance circles. We will see later that this is important to draw power contours for a given output power on the smith chart.

## References

- Steve Cripps - RF Power Amplifiers for Wireless Communications Chap 2.4