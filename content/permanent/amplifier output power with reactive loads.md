---
title: "amplifier output power with reactive loads"
created: 2023-05-04 08:20
status: #permanent
tags: #ee/amplifiers
---

We found two points on a constant power contour by [[permanent/amplifier output matching for specified power|using two different purely resistive loads]]. To build other points on the contour, consider adding reactive elements to the load network.

#### Case 1: Reactance $\pm jX_m$ in series with a resistive load $R_{LO}$

![[permanent/Pasted image 20230504082345.png]]

The impact of adding this reactance is that the voltage swing is increased, while the current swing remains at $I_{max}$. But, how does this guarantee constant output power? The answer to this lies in the relative phase between the V and I waveforms. Notice that in the case of [[permanent/amplifier output matching for specified power|purely resistive loads]], the V and I are exactly out of phase, and the peak magnitudes of V and I coincide (sign does not matter for instantaneous power delivered). When it is phase shifted with an added reactance, the V and I waveforms are not exactly out of phase, and therefore the instantaneous power involves the multiplication of two smaller quantities. Thus the average power delivered in both cases is the same.

But there is a maximum to the reactance that can be added. Remember that the output voltage swing cannot exceed that of the optimal power match case $2V_{DS}$. Thus the maximum magnitude of the load impedance cannot exceed $R_{opt}$. Thus the maximum reactance that can be added is constrained by
$$
\sqrt{R_{LO}^2+X_m^2}=R_{opt}
$$
The arc of constant power that is followed when a series reactance is added, conveniently follows the constant resistance circle of $R=R_{LO}=R_{opt}/p$.

#### Case 2: Susceptance $\pm jY_m$ in shunt with a resistive load $R_{HI}$

![[permanent/Pasted image 20230504090501.png]]

To complete the other side of the contour, add a shunt susceptance $jB_m$ in parallel to load resistance $R_L=p.R_{opt}=1/G_{opt}$. In this case, the addition of a parallel element means that the total output voltage is unaffected, but the magnitude of current can be increased by the addition of susceptance. Again, note that the phase shift in the voltage means that the instantaneous power may be different with the addition of susceptance, but the total output power does not change.

In this case too, the addition of susceptance can only increase output current up to $I_{max}$ which means that the maximum amount of susceptance that can be added is constrained by
$$
\sqrt{G_{HI}^2+B_M^2}=G_{OPT}
$$
In this case, the arc of constant output power follows the constant conductance circle $G=1/(p.R_{opt})$.

> [!warning] Why is it that in both reactance and susceptance cases, the phase of current does not ever change?

When you combine the constant power contours due to resistive, reactive and susceptive loads, the resulting power contour, which is a combination of the reactance circle $R_{opt}/p$ and susceptance circle $p.R_{opt}$, results in an ==oblong, rugby ball shaped contour==, which is characteristic of power contours in load pull measurements. They never follow pure circles like that for constant gain.

![[permanent/Pasted image 20230504091859.png]]

In this figure, the mismatch circles are plotted alongside the power contours. Mismatch circles means points of constant magnitude of  $S_{22}$ on the smith chart. Note that, they do not line up with the power contours. This is evidence that power match contours do not form the way they do because of how $S_{22}$ moves in the presence of a large signal.