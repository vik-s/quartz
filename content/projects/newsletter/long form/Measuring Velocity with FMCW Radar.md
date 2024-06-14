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

Several astute readers pointed out that phase information can be used to further resolve target range and velocity.  This is what we will discuss in further detail in this article.

## An Upgraded Perspective of a FMCW Chirp

To better understand how phase plays a role, we need to upgrade our visualization of the time-domain representation of an FMCW chirp - from two to three dimensions. A sinusoid when represented as a complex signal, is [a helix spiraling forward in time](https://youtu.be/YVLEsxq2kEA). To extend this idea to frequency modulated waves, we'll use an analogy.

Visualize a spring. A complex sinusoid at any given time is a point along the spring. As time passes, the point spirals forward along the spring. In an earlier article, we visualized this when understanding the need for negative frequencies. Give it a quick look over if you need a better mental picture.

If you look through the axis of the spring, you will see a circle. As the signal propagates, the value at any instant is given by an amplitude that corresponds to the radius of the circle, and an angle that changes with time. This is the complex representation of a sinusoid.

For an FMCW signal in complex form, visualize the same spring but more compressed on one end, and elongated at the other. This represents a complex signal whose frequency is continuously increasing, like in a radar chirp. Looking through the spring again, we will have a dot that traces a circle with a magnitude and phase as the wave propagates. The difference now is that it will spin faster around a circle as the frequency is linearly increased.

The main takeaway here is that both constant and FM signals can be represent in polar form, with magnitude and angle. We will use this information. 
## Velocity Measurement from Phase

The multiplicative mixing process between transmitted and received chirps not only results in a constant (fn: not frequency modulated because both chirps have the same slope) beat difference frequency, but it also does something to phase. **The IF signal has a phase that is the difference between transmit and received signal phases**. As it turns out, this phase difference is immensely useful in range, velocity and even vibration measurements.
$$ IF = A_0\sin((\omega_{TX}-\omega_{RX}) + (\phi_{TX}-\phi_{RX})) $$

*Show a visual representation of the starting phase*

When the IF signal is represented as a peak in the spectrum, we are only looking at half the story - the magnitude of the signal. The peak also has a phase value that is equal to the *initial phase*  of the IF signal. So how does phase change with the distance to the object. This is fairly simple to calculate if the round trip delay changes by Δt=2Δd/c, and the instantaneous wavelength is 𝜆c.

$$
\Delta\phi = 2\pi f_c.\Delta t=4\pi f_c\Delta d/c
$$
$$
\Delta\phi=\frac{4\pi\Delta d}{\lambda_c}
$$
So the movement of an object produces an IF shift of S⨉2Δd/c (as we calculated in the last newsletter), and a phase change Δϕ, both of which are directly proportional to the change in distance. Which measurement is more sensitive? 

For a 77 GHz radar with 4 GHz bandwidth and 40 microsecond chirp time, the IF shift would be about 660 Hz, while the phase shift would be about 180 degrees. 660 Hz would be indistinguishable in the fast fourier transform (FFT) spectrum (fn: used to convert time domain signals to frequency domain) unless a long observation window is used. Phase measurement is much more sensitive to small changes in range, and easily detectable.

The phase sensitivity is useful for other applications such as vibration detection and remote vital sign monitoring because small changes in distance produce easily measurable shifts in phase.

*Show a picture of two objects moved 1mm apart and show a diagram of 180 phase shift*

This sensitive phase shift can be used to estimate velocity of the object by estimating how much the phase changes in a given interval of time. To do this, two chirps are emitted spaced apart by chirp time Tc. Computing FFT on the IF signal (called Range FFT) would result in two peaks in the spectrum whose frequency values are closely spaced but with differing initial phases.

*Show picture of two chirps and how thats used for velocity estimation*

The object would have moved a distance of v times Tc, where v is the velocity of the object. Using vTc instead of Δd in the phase equation above would allow us to calculate velocity as
$$ v = \frac{\lambda_c \Delta \phi}{4\pi T_c} $$
## Doppler FFT for Velocity Estimation

So far we have looked at velocity measurement of a single radar target. What if there are multiple objects moving at different velocities? As long as they are at different distances, they will result in distinct FFT peaks each with phase change information that can be used to calculate velocity. 

The problem arises when multiple objects are in the same range, but moving at different velocities. In this case, the FFT peaks will overlap, and even if phase change information is available, it is hard to tell which phase change corresponds to which object.

The solution to this problem is to use **a sequence of N-chirps in succession, called a frame**. This is the fundamental unit of transmission in FMCW radar. Computing the range FFT of each chirp gives a series of peaks whose frequency is the same but containing different phase information. An object moving faster will accumulate more phase shift over the sequence of N chirps compared to a slower moving object.

Now compute FFT again, over the collection of range FFTs corresponding to each chirp. **An FFT computed over a sequence of range FFTs corresponding to N chirps in a frame is called a doppler FFT**. A doppler FFT will provide two peaks in the spectrum, corresponding to the velocity of each object.

*Draw a picture showing doppler FFT*

Immediately we are faced with the question of resolution: How close can the two velocities be, so that the peaks will be uniquely identifiable?



> How can we still tell if an object is moving towards or away from the radar?



