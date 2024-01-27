---
title: How Phased Array Antennas Work
tags:
  - circuit
project: substack
date_published: 
status: 🚧
final title:
---
In a previous article, we discussed how arraying antennas causes the radiated pattern to narrow due to wave interference. Consider reading that before getting into this one. In this article, we will build on that concept to understand how to steer the radiated beam to any desired direction using phase shifts to the antennas in an array. The phased array antenna is widely used in radar and most recently in 5G cellular technology and modern WiFi to improve the signal to noise ratio.

In this article, you will learn:

- Why antenna beams need to be steered
- How phase shifts cause antenna beam directions to change
- Phased Array Architectures
- The concept of adaptive beamforming

Let's dive in!

### Why Steer Antenna Beams?

Unlike an omnidirectional antenna that can transit and receive in all directions, a narrow radiation beam from an array cannot do that. To get maximum reception, you have to point the antenna in the direction of the source. Historically, this was done with the help of motorized platforms that manually rotated the antenna.

For a lot of applications, such approaches are heavy, cumbersome and slow. Not to mention, unreliable due to mechanical wear and tear. Modern communications demand that the antenna beam be steered to a different direction in a matter of milliseconds.

The solution to rapidly steer beams with electronic control involves the use of phased array antennas. The fundamental operating principle is that you can steer the beam in any direction by precisely feeding each antenna in the array with a progressively delayed version of the signal (or a phase shift).

Let us see how this happens.
### Steering the Beam

In the article on (antenna arrays), we looked at how constructive interference sharpens the radiated beam when two antennas spaced half a wavelength apart are fed with signals of equal amplitude and phase.

What happens if the phase of the signal fed to one of the antennas is shifted (by delaying it) compared to the other one? Figure 1 shows two radiated patterns from an omnidirectional antenna, one with no phase shift and the other with a 180 degree phase shift. The wave peaks emitted by one antenna coincides with the troughs of the phase shifted antenna at any point in time.

> Fig1

Figure 2 shows the resulting interference pattern when two antennas are placed half a wavelength apart. On the left figure, the signals fed are of the same phase. On the right, they are shifted by 180 degrees. 

> Fig 2

When there are no phase shifts present, constructive interference in the top and bottom results in the energy being more directed in that direction while destructive interference to the left and right sides produce nulls. Such an array is called a *broadside antenna array*.

With 180 degree phase shift between the two antennas, constructive interference occurs to the side instead, while destructive interference produces nulls in the top and bottom. Such an array is called an *endfire antenna array*.

Simply by introducing a phase shift in the signals fed to the antenna, we were able to steer the beam from the vertical to the horizontal direction. We converted a broadside antenna to an endfire antenna.

Using a phase shift between 0 and 180 degrees between the signals will result in the antenna beam pointing somewhere between the broadside and endfire directions. Usually, the steering angle is limited to 60 degrees on either side for a total steering angle of 120 degrees. Unwanted effects occur if the beam is steered too far out beyond that.

In both of these cases, the beam can be made narrower using more antenna elements in the array. The question then arises: what phase shifts should be provided to each antenna element in the array? To answer that, we will look at three configurations: 1) the broadside array, 2) the endfire array and 3) the phased array. Each of these configurations are shown in Figure 3 for a 6-element linear antenna array.

- Broadside: Each element in the array is fed with a signal with same amplitude and phase. The resulting radiation pattern has its maximum radiation in the +/- 90 degree direction in the azimuth plane.
- Endfire: Each alternate antenna is fed with either 0 degree or 180 degree phase shift. The resulting radiation pattern has its peaks in the 0 and 180 degree directions in the azimuth plane.
- Phased: Each consecutive element in the array is fed with a *progressive* delay of 50 or 100 degrees. It is clear that the main beam of the antenna can be steered accordingly


To steer a beam in both around in azimuth and up/down in elevation, we need to phase shift the signal to all antenna elements in a two dimensional planar array. Depending on the phase shift applied to each linear dimension of the 2-D antenna array, the beam can be made to point to any desired direction.

### Case Study: Dishy McFlatface

Commercial low earth orbit (LEO) satellite-based broadband internet providers like Starlink and Amazon's similar initiative Project Kuiper, aims to enhance global connectivity by deploying thousands of interlinked satellites in a constellation. 

Take Starlink's dish antenna (Dishy McFlatface or Dishy) for example. It consists of 1280 circular patch antennas each about a centimeter in diameter arranged in a hexgonal honeycomb. Each antenna is fed with a 12 GHz modulated signal carrying information that is to be transmitted. Depending on where the satellite is positioned in the sky, the generated beam from this array needs to be pointed exactly in a specific direction. To do this, each element in the array is fed with a progressively delayed version of the signal.

Here's the challenge. The beam needs to be precisely transmitted to a satellite located 550 kilometers away that is moving at a speed of 27,000 kilometers per hour. When the satellite is out of line-of-sight, it needs to quickly switch over to the next available satellite.

The fact that this is even possible is the magic of the phased array antenna. 

I'll leave you with this fantastic video explaining how everything about Dishy works.
https://youtu.be/qs2QcycggWU?si=PIbktv3ZYGikdO5C

### References

https://archive.ll.mit.edu/publications/journal/pdf/vol12_no2/12_2devphasedarray.pdf

- Starlinks Phased Array Antenna - Dishy McFlatface https://www.linkedin.com/pulse/overview-how-starlinks-phased-array-antenna-dishy-works-curtis-arnold/
- Kuiper phased array antenna - https://www.aboutamazon.com/news/innovation-at-amazon/amazon-marks-breakthrough-in-project-kuiper-development?ots=1&tag=arstech20-20&linkCode=w50
- https://youtu.be/h6MfM8EFkGg?si=dBO341izpGSJck7t The Signal path's detailed discussion on Starlinks Phased Array design.
- Supreme video about dishy mcflatface https://youtu.be/qs2QcycggWU?si=PIbktv3ZYGikdO5C

[[Excalidraw/PhasedArrayFundamentals.excalidraw|PhasedArrayFundamentals.excalidraw]]