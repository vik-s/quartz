---
title: Conjugate vs Power match
tags:
  - atomic
style: XvsY
---
An RF transistor is like a child. It needs the right environment to perform well.

The load you present at the input and output terminals of the transistor determine the performance you will get from it. To present the right load, you need matching networks.

The easiest way to understand this is to look at conjugate matching. You look into the device terminal and design a matching network to present the complex conjugate of the impedance you see. As a result, you will get good gain (not necessarily max) from the transistor.

This makes one major assumption.

That there are no limits on the power supply in terms of the voltage and current it can provide during the amplification process. In reality, this is not true.

Power supplies have limits on the voltage and current they can provide. They all have a maximum wattage rating.

Due to this limitation, conjugate matching may give you good gain, but most certainly won't provide maximum output power.

For this, you need a power match.

You can find a unique load that is not the complex conjugate that maximizes the output power from the transistor. This certainly won't give you the best gain.

The way this is done in practice is via a "load-pull" measurement. You can sweep the load impedance at the device terminal and find the point of maximum output power. This is commonly done in power amplifier design.

Upcoming newsletter: https://www.viksnewsletter.com
Follow me (🔔) for more posts on EE, career, and growth.



