---
title: "Interpretation of Mason's Invariant U as a Gain Maximum"
created: 2023-04-10 10:56
status: #permanent
tags: #ee/basics
---

[[Mason's Invariant U]] is the maximum achievable power gain of an amplifer provided that the following conditions are met:

1. The [[Excalidraw/embedding_2port_network.excalidraw|embedding network]] is linear, lossless, reciprocal two-port
2. The device + embedding network is unilateralized (the embedding network is chosen such that the composite is a [[permanent/unilateral device|unilateral device]])
3. No other connection between source and load networks, except through device
4. Source and load impedances are passive. Gain is maximized with respect to these variables.

The important point here is that _the embedding network should unilateralize the device_, and be a lossless, reciprocal network. After unilaterization, provided that the [[permanent/ conditions for unilaterized device to be absolutely stable|unilaterized device is absolutely stable]], setting the source and load impedances to complex conjugates at their respective terminals would mean that maximium power gain of the unilaterized device is same as U of the intrinsic device.

> [!important] U is not max power gain
> U is not the highest power gain that can be obtained from the device in an arbitrary circuit. In an active device (U>1), maximum power gain is infinite as in the case of an oscillator circuit.

The beauty of U is that it is defined for passive and active devices, or absolutely stable or potentially unstable devices. It's interpretion as a gain metric depends on certain conditions being met.

## References

- http://rfic.eecs.berkeley.edu/~niknejad//ee217sp05/mason.pdf