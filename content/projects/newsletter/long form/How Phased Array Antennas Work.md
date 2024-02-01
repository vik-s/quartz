---
title: How Phased Array Antennas Work
tags:
  - circuit
project: substack
date_published: 2024-02-11
status: 🟢
final title: Phased Array Antennas and Architectures
---
In a previous article, we discussed how arraying antennas causes the radiated pattern to narrow due to wave interference. Consider reading that before getting into this one. In this article, we will build on that concept to understand how to steer the narrow beam using phase shifts.

In this article, you will learn:
- How phase shifts cause antenna beam directions to change
- Pros and Cons of phased array architectures
- about Dishy McFlatface

If you don't know who that is, read on!

### Why Steer Antenna Beams?

Unlike an omnidirectional antenna that can transit and receive in all directions, a narrow radiation beam from an array cannot do that. To get maximum signal reception, you have to point the antenna in the direction of the source. Historically, this was done with the help of motorized platforms that manually rotated the antenna.

For a lot of applications, such approaches are heavy, cumbersome and slow. Not to mention, unreliable due to mechanical wear and tear. Modern communications demand that the antenna beam be steered to a different direction in a matter of milliseconds.

The solution to rapidly steer beams with electronic control involves the use of phased array antennas. The fundamental operating principle is that you can steer the beam in any direction by precisely feeding each antenna in the array with a progressively delayed version of the signal (or a phase shift).

Let us see how this happens.
### Applying Phase Shifts to Antennas

In the article on (antenna arrays), we looked at how constructive interference sharpens the radiated beam when two antennas spaced half a wavelength apart are fed with signals of equal amplitude and phase.

What happens if the phase of the signal fed to one of the antennas is shifted (by delaying it) compared to the other one? Figure 1 shows two radiated patterns from an omnidirectional antenna; one with no phase shift and the other with a 180 degree phase shift. The wave peaks emitted by one antenna coincides with the troughs of the phase shifted antenna at any point in time.

> Fig1

Figure 2 shows the resulting interference pattern when two antennas are placed half a wavelength apart. On the left figure, the signals fed are of the same phase. On the right, they are shifted by 180 degrees. 

> Fig 2

When there are no phase shifts present, constructive interference in the top and bottom results in the energy being more directed in that direction while destructive interference to the left and right sides produce nulls. Such an array is called a *broadside antenna array*.

With 180 degree phase shift between the two antennas, constructive interference occurs to the side instead, while destructive interference produces nulls in the top and bottom. Such an array is called an *endfire antenna array*.

Simply by introducing a phase shift in the signals fed to the antenna, we were able to steer the beam from the vertical to the horizontal direction. We have converted a broadside antenna to an endfire antenna.

Using a phase shift between 0 and 180 degrees between the signals will result in the antenna beam pointing somewhere between the broadside and endfire directions. In a practical phased array, the antenna beam is only steered on either side of the broadside direction, and never really all the way to endfire, to avoid distortions to the radiated beam.

In both of these cases, the beam can be made narrower using more antenna elements in the array. The question then arises: what phase shifts should be provided to each antenna element in the array? Let's look at this closely.

Figure 3 shows a 6-element linear antenna array. The squares represent radiating antenna elements color coded to show various phase shifts to the applied signal. Depending on the phase shift applied to each antenna, the following radiation patterns can be achieved.

- Broadside: Each element in the array is fed with a signal with same amplitude and phase. The resulting radiation pattern has its maximum radiation in the +/- 90 degree direction in the azimuth plane.
- Endfire: Each alternate antenna is fed with either 0 degree or 180 degree phase shift. The resulting radiation pattern has its peaks in the 0 and 180 degree directions in the azimuth plane.
- Phased: Each consecutive element in the array is fed with a *progressive* delay of +50 or -50 degrees. The main beam can be steered on either side of the broadside direction. Increasing the phase shift to each antenna element will further steer the beam away from the broadside direction.

To steer a beam in both around in azimuth and up and down in elevation, we need to phase shift the signal to all antenna elements in a two dimensional planar array. Depending on the phase shift applied to each linear dimension of the 2-D antenna array, the beam can be made to point to any desired direction.

>Fig 3

### Phase Shifting Architectures

In principle, it is simple to understand that the antenna element needs a phase shifted version of the signal to steer the beam. In practice, there are several places in the radio system where this phase shift can be applied. Each approach has its pros and cons.
#### Passive vs Active
Passive arrays use a central transmitter/receiver (TR) module to handle the amplification of radio signals, while using a phase shifter at every antenna element of the array. This was the predominant design method in the early days of radar because the implementation of active circuits at every antenna element was cost prohibitive. Without amplitude control to each antenna, the functionality of passive arrays is limited. Features like gain tapering cannot be implemented.

With the advent of integrated circuits, active arrays have become a possibility where the amplification and phase shift are implemented using compact TR modules at each antenna in the array. With complete control over the signal being fed to each antenna, we have the ability to shape of the radiated beam as required by the system.
> Fig 4

#### RF Beamforming
This has been the predominant method of beamforming since the early days of phased arrays. The received and amplified signal from the antenna is phase shifted at RF frequencies in the GHz range. The simplicity of this approach makes it cost-effective and simple to implement. After combining signals from each antenna in the array, the beam has high directivity. This makes it simple to reject any interference before reaching the digital transceiver. As a result, the transceivers linearity requirements are greatly reduced.

#### IF and LO Beamforming
In this architecture, the phase shift to the antenna is implemented in the Intermediate Frequency (IF) range or using the Local Oscillator (LO). Phase shifters are easier to design for a narrow band of IF frequency, or in the LO approach, the phase shifter is not in the RF path to affect performance. However, there are a few downsides to this approach:
1. A mixer is required at each antenna element increasing the overall cost of the array
2. The mixer is subject to interference due to wide antenna beam (remember this is the raw antenna element before it is narrowed into a beam), and the resulting interference will propagate throughout the system.
3. For certain applications like in satellites, a very low noise local oscillator is required which eliminates the possibility of using integrated oscillators.
#### Digital Beamforming
This is the holy grail of antenna beamforming where all the phase shifting is implemented entirely in the digital domain by weighting each antenna signal received in the transceiver. The complexity and demands of implementing such a system is significant, but it provides the maximum flexibility in reconfiguring the antenna array dynamically. 

By implementing all control in the digital domain, the array can be dynamically split up into sub-arrays to implement multiple beams, each with its own scan angle and sidelobe level. With the advent of artificial intelligence and machine learning, arbitrary antenna patterns can be synthesized on the fly to achieve the maximum signal-to-noise ratio in any radio interference environment.

> Fig 5
### Dishy McFlatface

Commercial low earth orbit (LEO) satellite-based broadband internet providers like Starlink and Amazon's similar initiative Project Kuiper, aims to enhance global connectivity by deploying thousands of interlinked satellites in a constellation. 

Take Starlink's dish antenna (Dishy McFlatface or Dishy) for example. It consists of 1280 circular patch antennas each about a centimeter in diameter arranged in a hexgonal honeycomb. Each antenna is fed with a 12 GHz modulated signal carrying information that is to be transmitted. Depending on where the satellite is positioned in the sky, the generated beam from this array needs to be pointed exactly in a specific direction. To do this, each element in the array is fed with a progressively delayed version of the signal.

> Fig 6

Here's the challenge. The beam needs to be precisely transmitted to a satellite located 550 kilometers away that is moving at a speed of 27,000 kilometers per hour. When the satellite is out of line-of-sight, it needs to quickly switch over to the next available satellite.

The fact that this is even possible is the magic of the phased array antenna. The sheer amount of engineering in phased arrays can be staggering - involving  integrated circuit design, electromagnetics, digital computation, signal processing - whose applications range from your pocket cellphone all the way to space. 

Its fascinating to say the least.

I'll leave you with this fantastic video explaining how everything about Dishy works.
https://youtu.be/qs2QcycggWU?si=PIbktv3ZYGikdO5C

### References

https://archive.ll.mit.edu/publications/journal/pdf/vol12_no2/12_2devphasedarray.pdf

- Starlinks Phased Array Antenna - Dishy McFlatface https://www.linkedin.com/pulse/overview-how-starlinks-phased-array-antenna-dishy-works-curtis-arnold/
- Kuiper phased array antenna - https://www.aboutamazon.com/news/innovation-at-amazon/amazon-marks-breakthrough-in-project-kuiper-development?ots=1&tag=arstech20-20&linkCode=w50
- https://youtu.be/h6MfM8EFkGg?si=dBO341izpGSJck7t The Signal path's detailed discussion on Starlinks Phased Array design.
- Supreme video about dishy mcflatface https://youtu.be/qs2QcycggWU?si=PIbktv3ZYGikdO5C
- https://www.mwrf.com/technologies/embedded/systems/whitepaper/21139652/analog-devices-phased-array-antenna-patterns
- https://www.mwrf.com/technologies/components/article/21849977/analysis-of-a-24-to-30-ghz-phased-array-for-5g-applications-part-1
- https://www.mwrf.com/technologies/components/article/21850061/analysis-of-a-24-to-30-ghz-phased-array-for-5g-applications-part-2

[[Excalidraw/PhasedArrayFundamentals.excalidraw|PhasedArrayFundamentals.excalidraw]]