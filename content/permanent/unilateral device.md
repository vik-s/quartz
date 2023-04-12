---
title: "unilateral device"
created: 2023-04-12 08:20
status: #permanent
tags: #ee/basics
---

A unilateral two-port device is one that has no reverse transmission of signals, from the output port to the input port. In terms of Z-parameters,
$$
Z_{12} = 0
$$
Real devices are usually not unilateral, and are usually unilateralized by the means of an embedding network as shown below. There are many ways to implement unilateralizing networks.

![[Excalidraw/embedding_2port_network.excalidraw|center]]

The design of these embedding networks (they can also be viewed as feedback networks between input and output) are essential in the design of amplifiers, where it is preferred to decouple the input and output for the sake of designing a [[matching network]]. This way, one can independently design the input and output networks without them influencing each other.

## References
- http://rfic.eecs.berkeley.edu/~niknejad//ee217sp05/mason.pdf
- [[permanent/example design of a unilateralizing network]]