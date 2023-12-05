---
title: Why you should know Y and Z parameters
tags:
  - atomic
style: educational
written: ✅
published: ✅
---
Learning to use Y and Z parameter networks makes you look like a math genius.

Let's say you have some s-parameter data. Just 2-ports for simplicity.

You want to terminate port 2 in a short, so that you can measure say trace inductance. Or you want to leave port 2 open to find the loading capacitance at port 1.

I've seen too many RF engineers drop the s-parameter file into a schematic (like ADS), put in a 50 ohm termination on port 1, add a open/short on port 2, add a s-parameter simulation controller and then deal with 1-port s-parameter data.

There is an easier way.

Let's revisit the definition of Y and Z parameters.

Y11 = I1/V1 when V2=0. This means port 2 is a short.
Z11 = V1/I1 when I2=0. This means port 2 is an open.

All you need to do is convert the original s-parameter matrix in Y or Z (ADS has stoy() and stoz() functions) and then look at Y11 or Z11.

For many on-wafer measurements, you can derive many active and passive device properties from Y and Z parameters by assuming a PI- or T-model respectively.

Understanding this comes in handy to derive various circuit elements from s-parameter measurements on the fly.

♻️ Repost if you found it helpful
👉 My upcoming newsletter (2024): https://www.viksnewsletter.com/

Follow me (🔔) for posts on EE, career, and growth.

![[Excalidraw/ZandY parameters.excalidraw]]

 