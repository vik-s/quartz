---
title: Fundamentals of Phased Array Antennas
tags:
  - circuit
project: substack
date_published: 
status: 🚧
final title:
---
 Assume that there is an isotropic antenna - one that radiates in all directions. Its not an ideal pattern for antenna radiation because energy is lost in many directions. The solution to this is to place the in a radar dish.

If the beam needs to rotate, you have to move mass around with motors and this is quite slow. You cannot steer the antenna beam in fractions of a second.

Phased arrays are a method of creating an electronically steerable antenna pattern using an array of antennas in which each antenna is fed a phase shifted version of the orginal signal.

Assume antenna is radiating a sine wave. Place another antenna 1/2 wavelength away from the original one. *draw a diagram here* You will notice that there are several places where the signal from the first antenna cancels the signal from the second. Where the signal is inphase, they constructivevly add.  Even with 2 antennas, the resulting beam is more directional.

To make it even more directional, you can increase the number of elements in the antenna array, and with each additional antenna, the resulting interference pattern results in a more directional antenna beam

*overlay the gain azimuth plot over an interference pattern to tell people how to read an antenna gain plot*

But if you see this plot in 3D, it will look something like a snail shell that is not very sharp beam at all.

To make a conical directed beam, you will need a 2-dimensional array of antennas. 
*add a picture*

Array Factor:
- how many elements
- what is their spacing
- orientation of elements
- element pattern (isotropic or sinc)

Using sinc and an 8x8 elemetn array really gives a sharp beam

How do we steer the antenna beam now?

Consider two isotropic antenna spaced half wavelgnth apart  but delay the signal to the second antenna by 1/2 wavelength of 180 degrees. The resulting interference pattern shows that there is no energy in the boresight (or 0 degree azimuth) of the antenna array. Instead, the energy is directed entirely to the -90 and +90 directions.

The beam has been electronically steered by changing the relative phase between the two antenna elements. Instead of 180 degrees, the phase shift between the antenna elements can be any value, allowing us to steer the antenna beam smoothly along the azimuth.

In an multi element array, the phase shift is equally spaced between all the array elements. In a linear 8 element array for example, there are 7 phase shifts between the first and last element.

So, arraying the antennas forms the directed beam, and applying phase shifts to each antenna allows us to steer the direction of the beam.

The video has a nice animation to show this, but as you steer the antenna beam away from the boresight, the beam gets less sharp. Because of this there is only about 120 degree of usable range in both elevation and azimuth. To overcome this, you will need to use either multiple phased arrays or conformal antenna arrays.

What is beamforming?

In reality there is even more control you can have over antenna elements in the phased array. You can control both the gain and the phase of the signal being fed to elements in the array. In addition, with fast A-D converters availalbe, you can digitally control each element in the array resulting in adaptive beamforming.

Why do we need to control the shape of the beam? Its not always about having the narrowest main beam. We care about the overall signal to noise ratio of the system. The presence of side lobes in the antenna pattern means that interfering signals coming from directions other than where the main beam is pointing will decrease the SNR of the system.

So we need to reduce the amount of side lobes in the antenna beam. This is done with something called Gain Tapering. By providing the peripheral antenna elements with lesser gain, and the antennas in the center of the array with more gain, you can reduce the amount of side lobes. The downside of this is that you will end up with widening of the main beam, but the overall SNR of the system is still improved due to reduction of the side lobes. So you trade off radar resolution for lower side lobe gain.

Older radar systems used a fixed attenuator in series with the antenna elements and used a predetermined tapering pattern. Then changed the phase of the signals to steer the beam.  This is conventional beam forming.

With full digital control, we can pick any gain and any phase shift to any elements. Most combinations produce undesired patterns so you have to be careful.

To represent what kind of gain and phase needs to be applied to each element of the antenna array, you specify a weight vector. Adaptive beamforming involves finding these actual weights. With full digital control, we can find the optimal weights *depending on the environment that the antenna is in*.

One adaptive algorithm is called MVDR. Minimum Variance Distortionless Response adaptive beamformer. This algo needs 2 inputs:
- total Received signal at the array
- Give it angle of arrival of the main signal.

Minimize total received power, but power in direction of signal is maintained. This is a constrained optimization problem. This can be done with prepaackaged code from Matlab. 

---
### Intro
- Where are phased array antennas used and why?
- How was it implemented in the past?
- Why is it relevant today in 5G?

### Old school beam steering

Isotropic antennas are radiating elements that transmit or receive in all directions. Such antennas are not preferred because they transmit energy where its not always required, or receive interference from all directions.

We would much rather have a directional beam that transmits energy only in the preferred direction while not picking up interference from any other direction. The traditional approach to doing this is to use a parabolic dish with a dipole or horn antenna placed at its focal length. Parabolic antennas produce some of the narrowest antenna beams and can cover a wide range of frequencies by even having several antennas operating at different frequencies mounted at the focal point.

By increasing the size of the parabolic dish, more energy can be collected from a distant source and reflected into the receiving antenna at the focal point. This is why some radio telescopes use gigantic parabolic dishes (https://theconversation.com/china-completes-worlds-largest-radio-telescope-raising-hopes-of-finding-new-worlds-and-alien-life-62237) to capture weak signals from the distant universe.

To steer the beam in different directions, the whole antenna system is mounted on a motorized system that moves around a circle (azimuth) and up/down (elevation). Since this method usually involves moving mass around, beam steering is usually slow.

Phased array antennas can produce electronically steerable beams that change directions in milliseconds. Let's first see how antenna arrays work.

### How Antenna Arrays work

Let's say we have an antenna radiating a sine wave in space at a given frequency. The red circles represent peaks of the sine waves, and blue circles represent troughs. Place another similar antenna exactly half a wavelength away from the original one. Then observe how the radiation patterns from these two antennas interfere in space.

You notice that the red circles intersect in front of the antenna resulting in "constructive interference." This means the signals from each antennas add up to create a stronger signal.

At points to left and right of the two antennas, you notice that the red and blue circles intersect resulting in "destructive interference." The signals from each antenna cancel each other out, resulting in low radiation in that direction.

Simply by putting two identical antennas a fixed distance apart, you now have a narrower antenna beam that a single antenna alone.



References
- https://youtube.com/playlist?list=PLn8PRpmsu08q9U0y7_63Dfz5cawEnicxi&si=c_Dh9PPoI8xrqs3O
- 