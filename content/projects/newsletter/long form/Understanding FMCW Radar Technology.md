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

The delay from the reflected signal is usually a small fraction of the chirp time frame (like 5%).

Longer the observation window, the better the resolution of the radar. This has something to do with FFT needing a long enough observation time to be able to distinguish between two tones. An observation window of T can separate frequencies spaced apart 1/T Hz.

Consider the case of multiple targets. Depending the distance to target you will get different IF tones. This will be seen as different peaks on the spectrum (it can be plotted with range on X axis, this is called a range FFT in literature). To differentiate these two signals, we need a long obseravation window of the IF signal. This means that we will need a wider chirp bandwidth. 

What if you have two chirps with different durations but same chirp bandwidth? Which chirp has better resolution? What is the intuition behind this?

Another thing is that the IF signals are digitized by the ADC and then sent to DSP. The maximum IF frequency is set by Dmax the maximum distance seen by the radar, and the Slope of the chirp. Ultimately, the ADC sampling frequency which must be greater than S2d/c (or is it twice that?) can become a limiting factor for max distance a radar can see. This can be traded off by reducing the slope of the chirp.

An RF bandwidth from 77GHz - 81 GHz (4GHz) translates to a range resolution of 4cm.

--

In this series of articles, I explore how radar systems work, particularly Frequency Modulated Continuous Wave (FMCW) radar. We've nearly all heard of Radar and if you haven't, it stands for Radio Detection and Ranging. While this is not my main field of expertise, the concepts and inner workings seem so interesting that I decided to learn as I go. I invite you to join me on this journey. If you are an expert, feel free to leave a comment below so that we can all learn from you.

## What is FMCW Radar?

FMCW is the most commonly used type of automotive radar. It is used for adaptive cruise control, blind spot detection, rear collision warning, object classification, among others. 

FMCW is a continuous wave radar, which means that the RF signal is continuously on during the period of radar sensing. This is distinct from pulsed radar, which transmits short bursts of energy and waits for the reflected signal to arrive. The FM means that the frequency of the RF signal is not constant, but actually continuously modulated to increase in frequency.

The fundamental signal used in FMCW radar is called a chirp.  It consists of an RF signal that goes from a starting frequency F1 to an ending frequency F2 during a time period called the chirp duration Tc. The bandwidth of the chirp B (=F2-F1), and the frequency slope S (=B/Tc) are critical system parameters as we will see later.

Put *picture of a chirp signal* Compressed HI Resolution Pulse
### The Need for a Chirp

But why do we even need a chirp? It seems rather complex to generate signals like this. Fortunately, there is good reason for this. 

But first, we need to understand the concept of a matched filter. A matched filter is a signal processing idea used to extract a known signal from a noisy reflected signal received by a radar. The way this is done is to find out how correlated the received signal is, to a known waveform known as a *template* signal. This is done by *convolving* these two signals together. 

Put *picture of matched filter operating*

Let's see how this works for a radar that uses constant frequency pulses. The transmitter sends out a RF pulse at a certain frequency for a duration Tc. It is reflected from a target and received along with noise. Next, compare this signal with a constant frequency pulse as template signal. As long as the pulse does not overlap the template, the correlation is zero. As the pulse starts to overlap, there is some correlation, and it reaches a maximum when it is completely aligned.

The peak of the matched filter output tells us the delay between the transmitted and received waveforms and is useful for calculating the distance of the target object. Using a constant frequency pulse has two problems:

**SNR**: As the noise level rises, it quickly becomes difficult to tell where the peak is. We could increase the power level of the transmitted pulse, but it makes it hard to design linear transmit amplifiers that work well.

**Resolution**: If there are reflections from two targets, the received pulses might overlap making it difficult to detect any peaks. The ability of a radar to distinguish between distinct objects is called its *resolution*. To improve resolution, we could make the pulses shorter to minimize the overlap between signals. But shorter pulses are harder to distinguish from noise. There is always a  trade-off between resolution and SNR.

Put *pictures of how poor peaks are in SNR, and how overlap from multiple targets kills the peaks and makes it undetectable.*

The ability to resolve targets in the presence of noise dramatically improves when a chirp is used. When an RF signal with continuously increasing frequency is used, the output of the matched filter produces sharper peaks. To understand how, let's look at the correlations of a received chirp with its corresponding template signal.

As before, when the two signals do not overlap, the correlation is zero. When they start to overlap, the correlation is still low because the waveforms do not line up when they are of different frequencies. The correlation is maximum only when the two FMCW signals exactly line up. This results in a more detectable peak that is easy to identify even in the presence of noise. The sharper peaks will also be separate when two reflected signals overlap due to their different frequencies at any instant of time.

Put *pictures of how FMCW matched filter operation gives sharper peaks even in the presence of noise, and how overlapping signals produce distinct peaks.*




## FMCW in Nature
