---
title: Understanding FMCW Radar Technology
tags:
  - systems
project: substack
date_published: 
status: 🚧
final title:
---
- Why use FMCW radar over others?
- Architecture of FMCW radar system
- Detection of range, angle, ...
- ??

https://www.ti.com/video/series/mmwave-training-series.html

FMCW measures the range, velocity and angle of the object in front of it.

Some questions to be answered:
- How does the radar estimate range of the object in front of it?
- What if there are multiple objects?
- How can two closeby objects be resolved?
- How far can a radar sense an object?

The heart of FMCW radar is a signal called a chirp (Why do we even need a chirp?). It is a sinusoid whose frequency increases linearly with time within a given frequency bandwidth. The rate at which this frequency rises or the slope is an important parameter. The bandwidth of the signal and slope of the chirp are important system parameters.

Single-TX, Single-RX system.

A frequency synthesizer generates a chirp that is amplified and sent out via a TX antenna. The signal bounces off the object and is received by the RX antenna.  The received signal is mixed with  the original chirp to generate an intermediate frequency.

The mixer here serves two important functions:
1. Generate a frequency that is the difference of the *instantaneous* frequencies of the TX and RX signal (remember that frequency is linearly increasing)
2. The instantaneous phase of the mixed signal has a value equal to the difference of the instantaneous phases of the input signals.

The RX chirp is a time delayed version of the original TX one because it is only a static object. Therefore the output of the mixer at any instant is a signal with constant IF frequency that depends on how far away the object is. The greater the distance, the higher the IF value.

The delay in the signal is the time taken by the signal to travel to the object located at a distance d, and back, divided by the speed of light. Thus, the IF generated at output of the mixer is represented by S*(2d/c). The IF signal is valid only when the RX chirp is received, up to the point in time that the TX chirp is still present. Thus the ADCs should sample the IF signal only in this window.


