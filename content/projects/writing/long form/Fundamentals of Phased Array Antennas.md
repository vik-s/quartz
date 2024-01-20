---
title: Fundamentals of Phased Array Antennas
tags:
  - circuit
project: substack
date_published: 
status: 🚧
final title:
---
Phased array antennas and beamforming have become rapidly popular since the adoption of 5G new radio (NR) technology, especially for communication systems that involve millimeter wave frequencies. Millimeter waves when radiated out into free space don't travel very far due to high propagation path loss in the atmosphere. To overcome the loss, the antenna must transmit all its energy towards the receiver using a phased array antenna that can form an antenna beam pointed at the receiver.

While a lot goes into how this works and the applications are much more diverse, in this article, we will cover the absolute basics of phased array antennas and beamforming. 

You will learn:

1. The need for phased array antennas
2. How antenna arrays create narrow beams
3. How to electronically steer the narrow beams
4. What is beamforming and why its useful

Let's dive in!
### The Need for Phased Antenna Arrays

Isotropic antennas are radiating elements that transmit and receive in all directions. Such antennas are not preferred because they transmit energy where its not always required, or receive interference from all directions.

We would much rather have a directional beam that transmits energy only in the preferred direction while not picking up interference from any other direction. The traditional approach to doing this is to use a parabolic dish with a dipole or horn antenna placed at its focal length. The antenna is pointed towards the dish, so that the resulting beam is a collection of parallel rays reflected from the parabolic dish.

Parabolic antennas produce some really directed radiation beams can cover a wide range of frequencies by even having several antennas operating at different frequencies mounted at the focal point.

When receiving energy from faint sources such as stars and far away galaxies, the size of the parabolic dish can be increased to collect more energy and direct it towards the receiving antenna mounted at its focal point. For example, the FAST radio telescope in China boasts an antenna diameter of 500 meters, making it the largest radio telescope in existence today. (https://theconversation.com/china-completes-worlds-largest-radio-telescope-raising-hopes-of-finding-new-worlds-and-alien-life-62237)

To steer the antenna beam in different directions, any antenna system must be mounted on a motorized system that moves around a circle (azimuth) and up/down (elevation). Since this method usually involves moving mass around, beam steering is usually slow and the mechanical components needed are bulky.

While this is acceptable for some applications, it is hard to implement in communication systems like the ones mounted on aircraft. For these use cases, we would prefer that the beam is electronically steered thereby eliminating the need for servos that physically move antennas around.

Phased antenna arrays are the answer to electronic beam steering, and in the following section, we will look at how it works.
### How Antenna Arrays work

Let's say we have an antenna radiating a sine wave in space at a given frequency. The red circles represent peaks of the sine waves, and blue circles represent troughs as shown in Fig 1.

Place another similar antenna exactly half a wavelength away from the original one. Then observe how the radiation patterns from these two antennas interfere in space.

You notice that the red circles intersect in front of the antenna resulting in "constructive interference." This means the signals from each antennas add up to create a stronger signal.

At points to left and right of the two antennas, you notice that the red and blue circles intersect resulting in "destructive interference." The signals from each antenna cancel each other out, resulting in low radiation in that direction.

Simply by putting two identical antennas a fixed distance apart, you now have a narrower antenna beam that a single antenna alone.

What if you put the antennas further away? When the spacing between the array elements approaches a wavelength, the side lobes of the radiation pattern (also called grating lobes) become as strong as the main antenna beam. For this reason, half wavelength spacing is the most common choice in array design.

Adding antenna elements to a linear array will further narrow the beam. However, creating a one-dimensional antenna array only results in beam narrowing along one plane. The beam is still omnidirectional in the plane perpendicular to it. When viewed in three dimensions, the radiation pattern from the 8 element linear array looks more like a donut cut in half, rather than the narrow conical beam we were intending to get.

To narrow the radiated antenna beam in both directions, we need a two dimensional antenna array. The same principles we encountered in the constructive and destructive interference patterns resulting in narrowing of a beam, now occurs along two perpendicular planes. This gives us the narrow conical beam we are envisioning.

We have been considering only isotropic antennas as antenna array elements so far. In reality, we could have more directional antennas in the array. When an antenna with a sharper beam is used in an antenna array, the resulting beam is even sharper.

### Steering the beam

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

References
- https://youtube.com/playlist?list=PLn8PRpmsu08q9U0y7_63Dfz5cawEnicxi&si=c_Dh9PPoI8xrqs3O
- 