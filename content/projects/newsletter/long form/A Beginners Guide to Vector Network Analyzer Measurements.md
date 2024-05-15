---
title: A Beginners Guide to Vector Network Analyzer Measurements
tags:
  - metrology
project: substack
date_published: 
status: 🚧
final title:
---
Scattering (S) parameter measurements are the bedrock of RF engineering. They are used to calculate gain, matching, stability, noise, and efficiency, among other metrics. The process of measuring S-parameters involves sending an RF signal to a multiport device, and finding out the ratio of reflected and transmitted powers at each port. If you want a nice visual introduction to s-parameters, then check out this video.
https://www.youtube.com/watch?v=CEA8njh4tLU

I once attended a lecture by Prof. Andrea Ferrero, from Politecnico di Torino, who gave a talk on Vector Network Analyzer (VNA) measurements. His enthusiasm for the subject was infectious and his description of S parameter measurements with a VNA is something I never forgot.

> "It's like trying to measure the weight of a penny on a balancing scale, with a giant piece of ham on one side."
> \-Prof. Andrea Ferrero, Politecnico di Torino

The giant piece of ham is all the error in the system that needs to be calibrated out to make it sufficiently sensitive to measure the weight of a penny.

In this article, we will look at best practices to make accurate scattering (S) parameter measurements.
- thing1
- thing2
- thing3

Read time: X mins

--
## Working of a Vector Network Analyzer

A Vector Network Analyzer (VNA) is an instrument used to measure S-parameters of any multiport microwave network. It could be a one-port network like an antenna, a two-port like an amplifier or a multiport like a power splitter or directional coupler. VNAs are most commonly available in two- and four-port configurations. It is called a vector analyzer because the magnitude and phase of s-parameters are measured. In contrast, scalar network analyzers do exist when there is no need for phase information.

Modern VNAs are extremely complicated machines which cost half a million dollars when configured with all the bells and whistles. But, you can get a basic understanding of a VNA with the following block diagram.

Put *block diagram of VNA* (inspired by following links)

- https://cdn.hackaday.io/files/20500877072000/VNA%20Block%20Diagram%2001.jpg
- https://www.allaboutcircuits.com/uploads/articles/the-inner-workings-of-vector-network-analyzers-exploring-the-signal-source-and-receivers-fig1.jpg

A frequency synthesizer provides a highly stable input signal that is adjusted for level. Depending on whether we are making forward (from port 1 to 2) or reverse (from port 2 to 1) measurements, the switches connect the source to the test terminal, or to a 50 ohm reference impedance. For example, for forward measurements, port 1 is connected to the test terminal, and port 2 is terminated to 50 ohm.

The first input directional coupler samples the power that is being input to the device under test (DUT) (R1). The second input directional coupler samples the reflected power from the input of the DUT (A). The ratio of these measured quantities (A/R1) gives S11.

Similarly, at the output, the first directional coupler measures the power incident at the output port (R2) and the second directional coupler measures the reflected power from the output power (B). The ratio of these measurements (B/R2) gives S22.

Accordingly, S21 and S12 are the ratios B/R1 and A/R2, respectively.

The measurements of the four quantities are made with four receivers each of which employ a superheterdyne architecture with two intermediate frequency (IF) stages for best image frequency rejection. These are systems designed to have best signal detection possible. Component cost and power efficiency are not major concerns like in communication receivers. Dual IF architecture uses more components but provides exceptional signal detection capability. 

Modern VNAs use a three receiver architecture to still save on component cost, by eliminating a reference receiver that is not being used by the incident signal and instead measuring "switch terms," a concept we will save for a future article. 

Regardless of the architecture (three or four receivers, 2 or 4 port), none of the components used in a VNA are ideal. Cables, couplers, amplifiers, filters, mixers all have losses associated with them that must be calibrated out. This is the ham we must carefully weigh our device measurements against.

The systematic errors in a four receiver (or sampler) VNA architecture can completely be characterized by what is called an 8-term error model, and the three sampler architecture by a 12-term error model. Learning these models in detail involves signal flow graphs, equations and a whole lot of goodness not entirely suited to an introductory article. So we'll punt that to another time as well.

For now, we will only concern ourselves with how to make good s-parameter measurements in the lab using a VNA. 

## A Step by Step Guide to Good VNA Measurements

### Frequency Range

### Input power

### Resolution bandwidth

### Averaging and smoothing

### Input and output attenuation

### Calibration Techniques
- SOLT
- LRM
- TRL
- LRRM
### Validation of Calibration
### Cable Practices

### Torque Specifications

### On-wafer, Co-ax standards, Ecal













