---
title: Understanding Noise Figure and its Measurement Methods
tags:
  - metrology
project: substack
date_published: 
status: 🚧
final title:
---
### 4. Noise Factor or Figure

While there is noise received by the antenna in a communication system, each component in the receiver adds its own noise. The noise could be from various sources such as thermal noise, 1/f noise, phase noise or shot noise. Regardless of what the underlying source is, noise factor is a metric that defines the noise added by any circuit in the system based on signal-to-noise ratio (SNR):

> Noise factor is defined as the ratio of the SNR at the input to the SNR at the output of a circuit. When expressed in decibels, it is called noise figure.

For reasons we will see in a future article, it is critical that the noise figure of any circuit that comes before the low-noise amplifier be as low as possible. Once the signal is amplified, the noise figure of subsequent blocks in the system becomes less important.

In fact, a passive component like a filter can be assigned a noise figure equal to its insertion loss because the SNR degrades due to signal loss even if minimal noise is being added. As a result, it is important that any system components before the amplifier also has low loss. 

This is the main reason that RF switches are implemented with silicon-on-insulator technology and low loss SAW/BAW filters are used in the RF front end. We discussed this in a [previous article].