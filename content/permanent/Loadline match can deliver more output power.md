---
title: "Loadline match can deliver more output power"
created: 2023-05-02 11:18
status: #permanent
tags: #ee/amplifiers
---

In the absence of any restrictions from the generator or device, conjugate match will deliver the same amount of power as a loadline match. But in reality this is not so. In reality, there will always be a maximum voltage Vmax, or maximum current, Imax, that can be sustained at the device terminals.

![[permanent/Pasted image 20230502112233.png]]

Let's look at some numbers to see why loadline match can deliver more power at the output of a device.

Consider that Ig = 1A and Rgen=100ohms. According to conjugate match, Rload = Rgen, so that,
$$
V_o = Ig.(R_{gen}||R_{load}) = 1 \times 50 = 50V
$$
In the absence of any restrictions, the power delivered to the load is $1A \times 50V$ = $50W$.

Let us now assume that Imax = 1A and Vmax = 10V, likely limited by the voltage supply used in measurement. In the case of such a restriction, Vmax cannot reach 50V to sustain the 1A from the generator. So the current Ig will be reduced.
$$
I_g = 10V / 50\Omega = 0.2A
$$
Total power delivered to load will be $0.2A \times 10V = 2W$, which is substantially lower than the $50W$ initially calculated.

To get the maximum output power in the presence of these restrictions, the load must be set to a loadline match. 
$$
R_{load}=V_{max}/I_{max}
$$
For the numbers assumed in this example, Rload = 10V/1A = 10ohms. Output power that can be obtained by setting this load value is $1A \times (100\Omega || 10\Omega) \approx 1A \times 10\Omega \approx 10W$. While this value is nowhere close to the 50W that can hypothetically be obtained from an ideal case, it is still way better than the 2W that can be obtained from a conjugate match.

## References

- Steve Cripps - RF Power Amplifiers for Wireless Communications Chap 1.6
