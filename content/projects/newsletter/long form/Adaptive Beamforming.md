---
title: Adaptive Beamforming
tags:
  - systems
project: substack
date_published: 
status: 🚧
final title:
---

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
