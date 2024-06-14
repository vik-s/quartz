---
title: Measuring Velocity with FMCW Radar
tags:
  - systems
project: substack
date_published: 
status: 🚧
final title:
---
## The Ambiguity Problem

In a previous newsletter, we looked at how frequency modulated "chirp" signals are used in FMCW radar systems. The transmitted chirp reflects off a target and is received after a time delay. Since the chirp signal has a continuously increasing frequency within the chirp period, there is always an instantaneous frequency difference between the transmitted and received chirps. 

These chirps are multiplied together in a mixer to generate a beat frequency, which is digitized by the ADC and processed in the digital domain. This beat frequency is proportional to the distance to the object.

The velocity of the target also manifests as a frequency shift in the received chirp due to Doppler effect. The simultaneous measurement of range and velocity results in an IF signal whose value cannot be solely attributed to range or velocity. There is now an ambiguity in the measurement since we cannot tell what contributed to the frequency shift.

*Put picture showing the ambiguity in the received chirp due to range and velocity*

In addition, we mentioned in passing earlier that it is difficult to tell if an object is moving towards or away from the radar because received frequencies both above and below the transmitted signal frequency mixes down to the same IF (the image problem.)

Several astute readers pointed out that phase information can be used to further resolve targets.  This is what we will discuss in further detail in this article.

## An Upgraded Perspective of a FMCW Chirp

The multiplicative mixing process between transmitted and received chirps not only results in a beat difference frequency, but it also does something to phase. **The phase of the IF signal is the difference between transmit and received signal phases**. As it turns out, this phase difference is immensely useful in velocity and even vibration measurements. We will see how.

*Put equation of the IF signal showing both frequency and phase diferences*

To better understand how phase plays a role, we need to upgrade our visualization of the time-domain representation of an FMCW chirp - from two to three dimensions. A sinusoid when represented as a complex signal, is [a helix spiraling forward in time](https://youtu.be/YVLEsxq2kEA). Visualize a spring. A complex sinusoid at any given time is a point along the spring. As time passes, the further down the spring we go. In an earlier article, we visualized this when understanding the need for negative frequencies.

If you look through the axis of the spring, you will see a circle. Any instantaneous point on this spring can be represented by an amplitude and a phase.

For an FMCW signal in complex form, visualize the same spring but more compressed on one end. This represents a complex signal that is increasing in frequency, as it travels through time.
