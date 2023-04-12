---
title: "example design of a unilateralizing network"
created: 2023-04-12 08:38
status: #permanent
tags: #ee/basics
---

It is simple to design a unilaterizing network using passive elements and we can find ways to do it by ensuring that $Z_{12}=0$ of the composite network as required by a [[permanent/unilateral device]]. Below shows an example of one such network.

![[Excalidraw/unilateralizing_network_example.excalidraw|center]]

This circuit works by ensuring that the reactance $x_2$ at the output port adjusts the phase of the output signal so that it is exactly in-phase (or out-of-phase), at the time when $I_1=0$ (this corresponds to the point of peak voltage), with the input voltage.

The transformer is then adjusted so that the magnitude of the phase-adjusted output signal is fed back into the input effectively cancelling it, ensure that $Z'_{12}=0$.
$$
Z'_{12}=Z_{12} - n(Z_{22}+jx_2)
$$
Hence, choose $x_2$ so that the complex terms of the two quantities on the right side are equal, and adjust $n$, the turns ratio of the transformer, to make their magnitudes zero.