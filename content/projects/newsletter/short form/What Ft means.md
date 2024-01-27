---
title: What Ft means
tags:
  - atomic
style: educational
written: ✅
published: ✅
---
Ft is an important metric for the AC response of a transistor. Here's a quick low down on it.

Let's assume you have a transistor (like a BJT). You feed it with a little AC current at the input, short the output terminal, and measure the output AC current.

This is called current gain.

As you increase the AC current frequency, the capacitance at the input terminal shunts more and more current away from the transistor.

At a high enough frequency, the transistor cannot amplify AC current any more. This frequency is called "Transit Frequency" represented by Ft.

If you can build a transistor with a very low input capacitance, it would shunt away lesser AC current and therefore have a higher Ft.

If that is not possible, you have to find ways to improve the magnitude of current gain to improve Ft (like improve mobility).

To measure Ft, you can convert S-parameters to H-parameters, and extrapolate H21 (=I2/I1) to unity current gain. The frequency where H21=1 gives you Ft.

The amount of time taken by a signal to go from input to output is inversely proportional to Ft. Higher the Ft, lesser the time, faster your circuit.

This is why Ft remains such a key metric for transistor manufacturers.

My upcoming (in 2024) newsletter: https://www.viksnewsletter.com
Follow me (🔔) for posts on EE, career, and growth.