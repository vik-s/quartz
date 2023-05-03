---
title: "power match versus conjugate match"
created: 2023-05-02 10:23
status: #permanent
tags: #ee/amplifiers
---

Matching a transistor at its output for maximum power output can give significantly higher output power compared to a conjugate match. Conjugate match most often provides higher gain at lower input power, where non-linearity has not become significant.

![[permanent/Pasted image 20230502102704.png|400]]

In the example above, S22 match clearly gives better gain at lower power, but by matching for power, both the points of weak nonlinearity A, and moderate nonlinearity B are improved by about 2 dB. This means that the more power is delivered to the load.

At lower Pin, notice that conjugate match gives better gain, or more power is transferred to the output. This is in agreement with classical conjugate matching for maximum power transfer since the drive strength is low enough that a [[permanent/Loadline match can deliver more output power|loadline match]] is not required. In comparison, a loadline or power match will result in lesser power output low drive levels, but when reaching limits of I and V at high drive levels, delivers more power to the output.

## References

- Steve Cripps - RF Power amplifiers for Wireless Communications, Chap 2.2.