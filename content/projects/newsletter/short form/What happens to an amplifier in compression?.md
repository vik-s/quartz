---
title: What happens to an amplifier in compression?
tags:
  - atomic
style: 
written: ✅
published: ✅
---
When input signal to an amplifier is high, the output power and gain drops. The amplifier is in compression. But where does this power go?

If you answered "heat" or "thermal dissipation" -  you're not entirely wrong, yes there is some of it, but it's not the predominant cause for power drop.

The key is understanding that you are measuring output power at the fundamental frequency, and when the amplifier is operating in a highly non-linear mode, the output signal is significantly distorted and no longer resembles a pure sinusoidal signal.

The output signal has a significant amount of power in not only the fundamental, but also the harmonics of the fundamental. It is the transferring of power away from the fundamental tone, into harmonic frequencies, that causes the output power to drop.

There is significant effort in the power amplifier design community to "engineer" these output waveforms for most efficiency in compression. This often involves presenting the right impedances at the harmonics of the fundamental signal, and is important considering how much power is present at these harmonic frequencies in compression.

Follow me (🔔) for posts on RF engineering.
Subscribe to my newsletter: https://www.viksnewsletter.com