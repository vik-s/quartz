---
title: Automotive Radar Company survey
tags:
  - systems
project: substack
date_published: 
status: 
final title:
---
In previous articles on this newsletter, we covered the fundamental workings of automotive radar using frequency modulated continuous wave (FMCW) technology. Specifically, we looked at how to estimate range, velocity and angle of arrival.

In this article, we will do a general survey of companies working on developing automotive radar, what their approaches are and their latest product offerings. We 

Read time: 

~~

## Texas Instruments

TI's latest automotive radar offering is the [AWR2544](https://www.ti.com/product/AWR2544?bm-verify=AAQAAAAJ_____2vOdZzJLieWUjacrkkiwwzf2VhjiYBhAr6hgfh6mN73aelQiTIKMy3v6I6j5OXWVe4D0I4PAK3gLjxaXob5CC0VhONALJG2MaYOZGIMJhH_tiU3MUGofqKZ-_O3SIKSUdgU5XwBvWI-CssNf-CzYWwmgr7i6BRJ6_D6mY6luB2IYtAB-IfNj2ohHnQO4yvBPbNAWl2J_eq-HVIZFrZCFT6TxzCmBeNU3JNq6KurKDdWVkRtK47Aysxhxrbk-HWKdhYUKChoBmTzyKEStYc-tmuyGA#features) 76-81 GHz FMCW radar-on-chip sensor that they unveiled in CES 2024. It uses four transmit and four receive antennas with a special Launch-on-Package (LOP) interface. LOP is essentially the inclusion of a 3D waveguide on the back side of the PCB with the radar chip, and reduces the overall size of the sensor by 30%.

While most radar chips use edge architecture, the AWR2544 is the first in the industry to use a [satellite architecture](https://www.ti.com/document-viewer/lit/html/ssztcu7). What's the difference between the two?

Traditional radar sensors perform all the FFTs needed to track range, velocity and angle on the radar chip, and after object detection and classification, sends that information to the car's on board central driving assist system called the ADAS ECU (Advanced Driver Assistance System Electronic Control Unit), through a 100 Mbps ethernet link. The downside of this approach is that each radar sensor chip gets quite expensive because of all the computational complexity needed on each sensor on the chip. Self-driving cars can have 6-8 such sensors, driving up the cost.

A more efficient solution is to use a satellite architecture, where each radar sensor in the car only captures the reflected signal from target, digitizes it, calculates FFT and sends a compressed dataset to the central ECU via a 1 Gbps ethernet link. All the complex data processing is done centrally in the ECU and driving assistance is provided based on decisions made on the data. This is an efficient solution because it keeps the overall sensor cost low when complex computations are not required to be performed on it. Car OEMs can then make updates to the data processing algorithms via over-the-air updates to continuously improve the detection and classification of objects using sophisticated machine learning and AI algorithms.

Check out this [product marketing video](https://youtu.be/ZHZspS1HVO0?si=uuSE1LLnXx2hrxfI) for the AWR2544.

## Infineon Technologies

Infineon holds the biggest market share in automotive radar products and most recently they unveiled 24 GHz and 60 GHz radar system solutions for automotive and industrial applications, as part of the XENSIV product line.

The [BGT24ATR22](https://www.infineon.com/cms/en/product/sensor/radar-sensors/radar-sensors-for-automotive/24ghz-radar/bgt24atr22/) is a 24 GHz pulsed doppler radar with 250 MHz bandwidth built on 130nm Silicon Germanium technology. It has two transmit and two receive antennas, with integrated analog baseband and ADC. The analog section has both in-phase and quadrature basebands which [offers distinct improvements](https://www.ti.com/lit/wp/spyy007/spyy007.pdf) in sensor performance. While 24 GHz pulsed doppler radar does not have the advanced performance of 77 GHz FMCW automotive radar, it does provide a cost effective radar solution for low- to mid-tier automotive OEMs. 

The [BGT60TR13C](https://www.infineon.com/dgdl/Infineon-DS_BGT60TR13C-DataSheet-v02_49-EN.pdf?fileId=8ac78c8c7d718a49017d94bac88e5d43) is a 60 GHz FMCW radar sensor that operates from 58.0 to 63.5 GHz with a total bandwidth of 5.5 GHz, with one transmit and three receive antennas. The wide bandwidth allows resolution down to ~3cm and enables detection of human presence and both micro- and macro-motion tracking. A similar Infineon 60 GHz radar chip was used in the [Google Pixel 4](https://www.infineon.com/cms/en/about-infineon/press/press-releases/2019/INFPMM201910-003.html) to enable gesture controls via Motion Sense technology. The integration of radar into phones was part of the Google Soli project which ultimately [did not see the light of day](https://www.techdigiexpress.com/google-to-close-down-its-soli-undertaking/). In fact, future generations of the Google Pixel did not include radar based tracking and a guess as good as any is that the power consumption was so high that the Pixel 4 ended up having [terrible battery life](https://www.androidpolice.com/google-pixel-4-killed-motion-soli-radar-future/).

Add about Infineon and Aurora labs.