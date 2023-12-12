---
title: What Fmax means
tags:
  - atomic
style: educational
written: 
published:
---
Fmax is a much more useful metric than Ft for microwave design. Here is a quick note on Fmax:

First, let's assume we do this at one frequency:

🔹 Put a network around an active device that makes Z12=0
🔹 Match the device+network at input and output for max power gain

This gives you Mason's gain, U, at that frequency.

Now increase the frequency and calculate Mason's gain, U.

Find the frequency at which U=1 (or 0 dB). You just found Fmax of the transistor.

As opposed to Ft, which is just current gain, Fmax deals with Power Gain, which is a much more practical quantity for microwave design.

Additionally, Fmax takes into account things like intrinsic base resistance (or gate resistance) which has significant impact on RF amplifier design.

My upcoming (in 2024) newsletter: https://www.viksnewsletter.com
Follow me (🔔) for posts on EE, career, and growth.