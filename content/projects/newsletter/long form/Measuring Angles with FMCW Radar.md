---
title: Measuring Angles with FMCW Radar
tags:
  - systems
project: substack
date_published: 
status: 🚧
final title:
---
In this article, we continue the discussion on automotive radars. Previously, we looked at how chirp signals are used to measure distance or range of objects. A lot of the fundamentals of frequency modulated continuous wave (FMCW) radar are covered in the article below.
*Put link to chirp article*
Next, we looked at how to estimate velocity using the phase of the intermediate frequency (IF) signal that was obtained while mixing the transmitted and received chirps together using a two dimensional Fast Fourier Transform (FFT) that used individual FFTs to estimate the range (across the fast time axis) and velocity (across the slow time axis). The concepts in this article are essential to understanding the measurement of angles of arrival with FMCW radar. 
*Put link to velocity article*

In this article, we will focus on the estimation of angle of arrival of objects using multiple antennas. Specifically we will cover:
- thing1
- thing2
- thing3

Read time: X mins

## Understanding the Radar Cuboid*

fn: Literature calls it a Radar Cube, but I refuse to use that nomenclature because it implies all dimensions of cube are the same. As we will see quite quickly, it is almost never so. A more accurate term is cuboid, even if it does not roll off the tongue.

Here's the scenario. There is a transmitting antenna that emits a chirp frame that is reflected off an object located far away, and is received by multiple antennas each spaced a distance *p* apart. For our discussion, it does not matter if the object is moving or stationery. Our purpose is to evaluate the angle of the object to the radar receiver.

*Put picture of one tx and 2 rx antennas with all angle indications*

Just like before, a received chirp is converted to IF, digitized by the ADC and an "in-line" FFT is calculated by the hardware accelerated, FFT-optimized radar chip on board the system. On the first axis, we get the range FFT from which we can identify the peaks to directly relate the IF signal frequency to distance. The size of this dimension depends on the FFT length used to calculate range (like 256 or 512).

Remember that we are collecting data simultaneously on multiple antennas. So along the second axis will be the range FFT for each antenna, per chirp. In other words, along the second axis, at any point in time, you will have range FFT data corresponding to any given antenna, for a particular chirp. The size of this dimension depends on how many receiving antennas are present (like 3 or 4).

On the third axis, you will have range FFT data corresponding to each antenna, for every chirp in the frame. Along this axis, doppler FFT is calculated to extract the velocity of the objects in the radar field of view. The size of this dimension depends on how many chirps there are in a frame (like 256).

If you visualize the data collected along these axes, for every chirp transmitted, the received data is a radar cuboid containing range, velocity and angle information. In essence, this is the basic data structure received by the radar receiver for every frame. 

*Draw a radar cuboid*

## Estimating Angle of Arrival

Let us simplify our analysis to the case where there are only two receiving antennas. Depending on the location of the object, the chirp signal will travel an extra distance Δp to one antenna compared to the other. If the distance between the antennas is p, then Δp=p.sinθ. From our last article (https://www.viksnewsletter.com/i/145685890/velocity-measurement-from-phase) we know that an extra distance Δp results in a phase shift ΔΦ given by
$$ \Delta\phi = 2\pi f_c.\Delta t = 2\pi f_c.\frac{p.\sin(\theta)}{c} = 2\pi.\frac{p\sin\theta}{\lambda_c} $$
where λc and fc is the signal wavelength and frequency respectively.

We can elegantly calculate the angle of arrival from the phase shift between the signals of the two antennas.
$$ \theta = \sin^{-1}\left( \frac{\Delta\phi \lambda_c}{2\pi p} \right)$$
While velocity measurement from phase shift was a linear relationship, the measurement of angle of arrival is not. The inverse trigonometric relationship makes it inherently nonlinear. The relationship between phase shift and angle of arrival is relatively linear for angles close to zero degrees, and becomes significantly nonlinear as the angles approach ±π/2. Thus, **the angle of arrival estimation is most accurate when the object's location is somewhat in front of the receiver antenna, and gets less accurate for wider angles**.

Similar to the case of velocity measurement, the phase shift between antennas is unambiguous only if the total phase shift is less than π radians. Setting ΔΦ=π in the above equation gives the maximum field of view of the multi-antenna system.
$$ \theta_{max} = \sin^{-1}\left(\frac{\lambda_c}{2p}\right) $$
Spacing the antennas half a wavelength apart (p=λc/2) gives the maximum field of view, θmax = ±π/2. This is the same condition needed in antenna arrays (https://www.viksnewsletter.com/p/fundamentals-of-antenna-arrays?r=222kot&utm_campaign=post&utm_medium=web) to form constructive and destructive interference patterns and produce focused beams with minimal grating lobes (oddly).
## Angle FFT

Looking back at velocity estimation, we saw that two chirps were insufficient to resolve velocity (https://www.viksnewsletter.com/i/145685890/doppler-fft-for-velocity-estimation) because there was no way to tell which how much phase shift could be attributed to each object at the same range. We had to use multiple chirps.

Similarly, for two objects at the same range and moving at the same velocity, two antennas are insufficient to unambiguously resolve angle of arrival. Having more antennas in the receive array will help resolve angle of arrival with certainty.

Each antenna is capable of angle and velocity estimation of the object using a range and doppler FFT (2D FFT) on the data obtained from multiple frames. Such an FFT allows us to create a range-doppler plot whose peak identifies the distance and speed on a two dimensional plane. However, the FFT peak in this plane has an angle associated with it too.

Taking an FFT across the 2D FFTs created for each antenna channel in the array will result in peaks corresponding to each object in the radar field of view. The angular velocity of the peaks can then be used to uniquely identify the angle of arrival of each object.

In case you've been counting, to resolve the range, velocity and angle of arrival of objects in an FMCW radar, we need a 3D FFT across all the data contained in a radar cuboid.

*Put a picture of angle FFT and how it works*

## Improving Angular Resolution


## Choosing number of transmit and receive antennas













