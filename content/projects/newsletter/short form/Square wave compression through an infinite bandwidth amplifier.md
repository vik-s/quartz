---
title: Square wave compression through an infinite bandwidth amplifier
tags:
  - atomic
style: analytical
written: ✅
published: ✅
---
This thought experiment really tested my understanding of amplifier compression. 👇🏼

In my newsletter article, I explained how power is redistributed from fundamental to harmonics during compression. Check it out first before continuing: https://www.viksnewsletter.com/p/understanding-compression-and-nonlinearity

Now, imagine a square wave whose power in all harmonics is 0.1W.

It is fed to an amplifier with the following properties:
↳ 100x gain
↳ distortion free
↳ infinite bandwidth
↳ near 100% efficiency

The output is a 10W output square wave and the amplifier consumed 10W DC power. The peak of the square wave perfectly touches the upper and lower rail voltage, say 10V.

Now increase the input signal level to 0.5W.

The output power should be 50W, but the supply limits it to 10W.

The gain has dropped to 20x compared to the original 100x, but the relative harmonic levels to fundamental did not change even when amplifier is in compression (distortionless + infinite bandwidth).

Why is it compressing then?

This example outlines the supply limits perspective of compression I explain in the newsletter. It doesn't always have to be harmonics.

The explanation based on fundamental to harmonics power redistribution only applies to a weak-moderate nonlinearity cases, which is the case for 1dB compression.

Follow me (🔔) for posts on RF engineering.
Repost (♻️) if you found it helpful.
Subscribe to my newsletter: https://www.viksnewsletter.com