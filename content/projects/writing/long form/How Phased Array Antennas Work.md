---
title: How Phased Array Antennas Work
tags:
  - circuit
project: substack
date_published: 
status: 🚧
final title:
---
In a previous article, we discussed how arraying antennas causes the radiated pattern to narrow due to wave interference. I'd recommend you check it out if you haven't already. In this article, we will build on that concept to understand how to steer the radiated beam to any desired direction using phase shifts to the antennas in an array. The phased array antenna is widely used in radar and most recently in 5G cellular technology and modern WiFi to improve the signal to noise ratio.

In this article, you will learn:

- Why antenna beams need to be steered
- How phase shifts cause antenna beam directions to change
- Phased Array Architectures
- The concept of adaptive beamforming

Let's dive in!

### Why Steer Antenna Beams?

It's quite simple. Unlike an omnidirectional 

- Radar in aircraft
- LEO satellites
- Automotive radar
- 5G mm-wave applications
- Beamforming in Wifi7

### Steering the Beam

We have assumed that each element in the antenna array is fed at the same time. What happens when they're not?

Lets go back to the two element linear array case, and delay the signal to one antenna by half a wavelength or 180 degrees. Observe where the red and blue circles now intersect. Destructive interference causes the radiation to cancel out right in front of the antenna. Instead, constructive interference causes the radiation to double up on the left and right sides.

By delaying the signal to one antenna, we have effectively steered the beam away from the front of the antenna, to the sides.

This is a bit of an extreme example as you notice that there are two beams formed on either side. Usually, the steering angle is limited to 60 degrees on either side for a total steering angle of 120 degrees. Unwanted effects occur if the beam is steered too far out beyond that.

We already know that the beam will be sharper if we extend this to an 8 element linear array. To steer this beam, the signal fed to each antenna is equally and progressively delayed from the one next to it. An 8 element array will have seven equal phase shifts. For example, if you have a total phase shift of 70 degrees from the first to eighth antenna, each antenna in the array is delayed by 10 degrees.

To steer a beam in both around in azimuth and up/down in elevation, we need to phase shift the signal to all antenna elements in a two dimensional planar array. Depending on the phase shift applied to each linear dimension of the 2-D antenna array, the beam can be made to point to any desired direction.

### Adaptive Beamforming

We have only considered applying delays or phase shifts to the signal being fed to the antennas in the array. In theory, we could control amplitude of the signal to each antenna too. 

When early phased array researchers were working on stealth radar for aircraft, they quickly realized that they cannot afford to transmit energy in the side lobes of the radiation pattern. This unwanted energy transmission could be detected by enemy radar. 

They found that by reducing the signal amplitude to the peripheral elements of the antenna array, the gain of the side lobes decreased. This technique is called Gain Tapering. An unwanted side effect is that the main antenna beam got wider. The design trade-off was to balance radar resolution with lower side lobes so that the overall signal-to-noise ratio of the array can be improved.

In the modern age, with the advent of semiconductor technology, both the amplifier and phase shifter can be implemented right next to the antenna element and controlled digitally to provide desired amplitude and phase.

Conveniently, this makes it possible to represent the amplitude and phase shift for each element in the antenna array by a complex number, also called a weight. For the whole antenna array, we can represent the required amplitude and phase values in terms of a complex weight vector.

By providing the correct weight vector to the antenna array, the direction of the beam and extent of the side lobes can be controlled digitally. This is called beamforming.

The choice of weight vector need not be static. Depending on the environment the antenna is in, the direction of signal source, and the locations of interference, the antenna beam can be adaptively formed to maximize the signal to noise ratio.

This is usually done with the help of sophisticated algorithms that determine the weight vector to ensure that the main beam is pointed at the information signal, while creating nulls in the side lobes in directions where interference is present.

In the age of artificial intelligence and machine learning, everything from a simple multi-layer perceptron network to a deep convolution neural network has been utilized to rapidly predict the antenna array weights required to optimally adapt to any given radio interference environment with minimal computation.

The area of phased arrays and beamforming has many different aspects from pure electromagnetics to complex digital signal processing. Architectural choices among analog, digital and hybrid beamforming each have their pros and cons and then there is the actual implementation of variable gain amplifiers and phase shifters at RF, mm-wave and terahertz frequencies, all of which are greatly interesting!

For now, we'll leave it here for an introductory article on phased array antennas.



### References

https://archive.ll.mit.edu/publications/journal/pdf/vol12_no2/12_2devphasedarray.pdf

