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

This article covers some exciting developments and product offerings by startups and established companies in the automotive radar space and their unique approaches to their solutions. My list is by no means comprehensive, but instead focuses on companies that I feel have innovative solutions to radar technology. There are companies like Aptiv, Continental AG, Valeo, and a whole bunch of others developing clever radar solutions. If you work for an automotive radar company, and would like to showcase your company's product on this newsletter please reply to this newsletter, connect with me on LinkedIn, or X.

Specifically we will look at:
- Digital Radar (Uhnder)
- Gesture Sensing (Infineon)
- Satellite Configurations (Texas Instruments/NXP)
- Distributed Aperture Radar (Zendar)
- All Range Radar (Vayyar)

Read time: 9 mins

~~
## Digital Radar (Uhnder)

Uhnder is an Austin based startup founded in 2015 by Dr. Manju Hegde and Curtis Davis, and is pioneering a fundamental shift away from traditional radar technology to implement a fully digital radar system using Digital Code Modulation (DCM) technology. Earlier this year, they announced a $50 million Series D funding round, and have raised about $95 million over the four rounds. They have currently shipped over 200,000 radar chips designed to meet automotive radar needs.

Their product differentiation comes from using binary phase modulated signals instead of FMCW chirps to create what is called phase-modulated continuous wave (PMCW) radar. This modulation scheme using *spreading codes*, which are unique sequences of +1 and -1 that have good autocorrelation properties. They could be a periodic or pseudorandom sequences. The RF signal is phase modulated based on the binary sequence by mapping +1/-1 into discrete phase shifts like +1=0 and -1=π. The reflected signals are digitized and processed with a [matched filter](https://www.viksnewsletter.com/i/145459210/pulsed-radar-chirps) to detect radar targets.

One significant advantage of using DCM for radar is low interference. In FMCW radar, if there is a nearby interfering radar (think of multiple cars on the road), then it gets difficult to tell whether the received signal is from a nearby radar, or from a reflected signal. With digital radar, each vehicle has a unique spreading code so that the received signal will have high correlation after matched filtering only if the spreading code matches the transmitted one. An interfering PMCW signal from a neighboring vehicle will use a different spreading code, and the received signal will have low correlation with the transmitted one after matched filtering.

The shift from analog to digital processing requires the use of much more sophisticated analog-to-digital conversion (ADC) circuits that operate in the gigahertz range compared to FMCW radars that only require ADCs in the 10s of megahertz range. However, with the continuous improvement of advanced CMOS technology nodes, the implementation of high speed, low power ADCs have become a reality at a competitive price point making digital radar a reality.

Uhnder's [S80](https://www.uhnder.com/images/data/S80_PTB_v2.0_1_.pdf) is their flagship product which operates in the 76-81 GHz frequency range, and has a staggering 192 virtual receive channels using 12 transmit antennas and 2x8 receive antennas, of which 96 virtual receive antennas operate in true MIMO. The receivers on-chip can switch between two banks of 8 receive antennas allow receiver division multiplexing. Their [S81](https://www.uhnder.com/images/data/S81_PTB_v1.0_(1)_.pdf) variant is their lower cost version that does not allow receiver division multiplexing and cuts the number of receiver antennas in half. Due to the use of DCM, these chips have excellent interference mitigation and are highly resistant to hacking. 

*Put some references to articles?*
## Gesture Sensing (Infineon Technologies)

Infineon is a big player in automotive radar products and most recently they unveiled 24 GHz and 60 GHz radar system solutions for automotive and industrial applications, as part of the XENSIV™️ product line.

The [BGT24ATR22](https://www.infineon.com/cms/en/product/sensor/radar-sensors/radar-sensors-for-automotive/24ghz-radar/bgt24atr22/) is a 24 GHz pulsed doppler radar with 250 MHz bandwidth built on 130nm Silicon Germanium technology. It has two transmit and two receive antennas, with integrated analog baseband and ADC. The analog section has both in-phase and quadrature basebands which [offers distinct improvements](https://www.ti.com/lit/wp/spyy007/spyy007.pdf) in sensor performance. While 24 GHz pulsed doppler radar does not have the performance of 77 GHz FMCW automotive radar, it does provide a cost effective radar solution for low- to mid-tier automotive OEMs. 

The [BGT60TR13C](https://www.infineon.com/dgdl/Infineon-DS_BGT60TR13C-DataSheet-v02_49-EN.pdf?fileId=8ac78c8c7d718a49017d94bac88e5d43) is a 60 GHz FMCW radar sensor that operates from 58.0 to 63.5 GHz with a total bandwidth of 5.5 GHz, with one transmit and three receive antennas. The wide bandwidth allows resolution down to ~3 cm and enables detection of human presence and both micro- and macro-motion tracking. 

A similar Infineon 60 GHz radar chip was used in the [Google Pixel 4](https://www.infineon.com/cms/en/about-infineon/press/press-releases/2019/INFPMM201910-003.html) to enable gesture controls via Motion Sense technology. The integration of radar into phones was part of the Google Soli project which ultimately [did not see the light of day](https://www.techdigiexpress.com/google-to-close-down-its-soli-undertaking/). In fact, future generations of the Google Pixel did not include radar based tracking and a reasonable guess is that the power consumption was so high that the Pixel 4 ended up having [terrible battery life](https://www.androidpolice.com/google-pixel-4-killed-motion-soli-radar-future/).

Regardless, ability to track human presence is helpful for proximity sensing in laptop PCs for [wake-on-approach](https://youtu.be/3WFx-8agAq4?si=GAnWEyKG1VTVDVw6), which results in a secure and smoother experience. It also has utility in [video doorbells](https://youtu.be/srLBuHDuiEs?si=IU9zwe1664GyxUdI) where the lights can be turned on, and video recording can be started once humans are detected in the field of view. 60 GHz radar is also incredibly useful in [monitoring falls in the elderly](https://youtu.be/m88YFalRsK8?si=KnBe5DPAOOOfjIvD), and offers a non-intrusive, private approach to 24/7 monitoring of elderly patients in their home. It's non intrusive because no extra equipment needs to be worn by the patient, and allows privacy because no images are recorded like in camera-based detection.
## Satellite Configurations (Texas Instruments / NXP)

Texas Instruments (TI) is a dominant player in automotive radar. TI's latest automotive radar offering is the [AWR2544](https://www.ti.com/product/AWR2544?bm-verify=AAQAAAAJ_____2vOdZzJLieWUjacrkkiwwzf2VhjiYBhAr6hgfh6mN73aelQiTIKMy3v6I6j5OXWVe4D0I4PAK3gLjxaXob5CC0VhONALJG2MaYOZGIMJhH_tiU3MUGofqKZ-_O3SIKSUdgU5XwBvWI-CssNf-CzYWwmgr7i6BRJ6_D6mY6luB2IYtAB-IfNj2ohHnQO4yvBPbNAWl2J_eq-HVIZFrZCFT6TxzCmBeNU3JNq6KurKDdWVkRtK47Aysxhxrbk-HWKdhYUKChoBmTzyKEStYc-tmuyGA#features) 76-81 GHz FMCW radar-on-chip sensor that they unveiled in CES 2024. It uses four transmit and four receive antennas with a special Launch-on-Package (LOP) interface. LOP is essentially the inclusion of a 3D waveguide on the back side of the PCB with the radar chip, and reduces the overall size of the sensor by 30%.

While most radar chips use edge architecture, the AWR2544 uses a [satellite architecture](https://www.ti.com/document-viewer/lit/html/ssztcu7). What's the difference between the two?

Traditional radar sensors perform all the FFTs needed to track range, velocity and angle on the radar chip, and after object detection and classification, send that information to the car's on board central driving assist system called the ADAS ECU (Advanced Driver Assistance System Electronic Control Unit), through a 100 Mbps ethernet link. The downside of this approach is that each radar sensor chip gets quite expensive because of all the computational complexity involved. Self-driving cars can have [6-8 such sensors](https://support.google.com/waymo/answer/9190838?hl=en), driving up the cost.

A more efficient solution is to use a satellite architecture, where each radar sensor in the car only captures the reflected signal from target, digitizes it, calculates FFT and sends a compressed dataset to the central ECU via a 1 Gbps ethernet link. All the complex data processing is done centrally in the ECU and driving assistance is provided based on decisions made on the data. This is an efficient solution because it keeps the overall sensor cost low when data processing is not done on it. Vehicle OEMs can then make updates to the data processing algorithms on the ECU via over-the-air (OTA) updates to continuously improve the detection and classification of objects using sophisticated machine learning and AI algorithms.

Check out this [product marketing video](https://youtu.be/ZHZspS1HVO0?si=uuSE1LLnXx2hrxfI) for the AWR2544.

NXP released the [SAF86xx](https://www.nxp.com/docs/en/fact-sheet/SAF86XX-FS.pdf) 76-81 GHz automotive radar SoC in early 2024, with four receive and four transmit antennas, and built on 28nm RF-CMOS technology. It is primarily directed towards ADAS applications, and like TI's AWR2544 chip, has the ability to operate in satellite architectures, streaming [radar cuboid](https://www.viksnewsletter.com/i/145908881/understanding-the-radar-cuboid) data in varying degrees of compression over a 1 Gbps ethernet connection. This allows the implementation of software-defined radar in vehicles, with continuous improvements via OTA updates. The lead customer for the SAF86xx is automotive radar is automotive supplier [Hella](https://www.hella.com/en/), who will leverage NXP's RF-CMOS radar technology for the next generation of automotive radar products.

## Distributed Aperture Radar (Zendar)

One of the major challenges in automotive radar is getting low angular resolution and as we saw in a previous article, that requires a large number of antenna elements in the MIMO array. Zendar is a startup co-founded by Vinayak Nagpal and Jimmy Wang in 2017 with about $20 million raised so far and offices in Berkeley (California), Germany and France whose focus is on using Distributed Aperture Radar (DAR) to improve radar angular resolution without including a massive number of antennas on chip. 

A loose way of describing antenna aperture is simply how *large* the antenna is. Higher the aperture, better the resolution of the antenna. Putting more number of antennas in an array does increase its aperture (like Uhnder's 192 virtual receiver antennas) but it comes at the cost of having increased electronics to handle multiple channels. Zendar, working in collaboration with NXP, has a different approach which involves putting multiple radar sensor chips on a vehicle and operating them *coherently* so that they act like one bigger antenna. 

Zendar is using the same SAF86xx chips from NXP whose application we already mentioned in satellite radar architecture. Their technology enables high angular resolution below 0.5 degrees offering LiDAR-like performance at a fraction of the cost. The advantage of this approach is that Zendar is able to collect data from multiple low cost radar sensors, fuse the data together in the central ADAS ECU and greatly enhance radar resolution. Their [marketing video](https://www.linkedin.com/posts/zendar_software-defined-radar-for-high-performance-activity-7153082346001289217-qskz?utm_source=share&utm_medium=member_desktop) has a nice visualization of how the radar sensors are mounted on automobiles for DAR.
## All Range Radar (Vayyar)

Typically, radar SoCs are classified according to their sensing range - short, medium or long, and several such sensors are deployed on a vehicle with long range radars placed in the front and back of the vehicle and medium or short range radars on the corners. A typical deployment in a vehicle requires about 8-10 such sensors, which increases cost and complexity of implementation. 

Vayyar is a Israeli company founded in 2011 that offers an "XRR" all range radar SoC that provides sensing capability from a range of 0 to 300 meters in a single chip at 60 and 79 GHz. They [recently secured](https://www.calcalistech.com/ctechnews/article/b1uyfsj00c) $108M series E funding, and has an estimated valuation of over $1B. 

To enable all ranges of detection, the chip crams an incredible 20 receive and 20 transmit antennas in a piece of silicon that enables hundreds of virtual receive channels. Just two of these sensors per vehicle implements complete radar coverage that replaces the functionality of ten such sensors. This offers a low-cost solution for the implementation of high performance automotive radar.

When the 60 GHz radar chip is placed inside the vehicle, a single chip detects and classifies eight occupants in three rows of seats for detecting the presence of a child, and enhanced deployment or deactivation of airbags. Having radar sensors within the cabin will allow the [detection of children](https://youtu.be/iVOE_HuVeeg?si=Jv-C-_V8t76CODlF) accidentally left behind in a hot car, which has claimed [nearly a thousand](https://www.consumerreports.org/cars/car-safety/anyone-could-forget-kids-in-hot-car-forgotten-baby-syndrome-a3901940661/) children's lives since 1998.

This [YouTube video](https://youtu.be/qyAt9R4kPis?si=jSkrxWuezYPuMXzk) from Vayyar paints a good picture of what the chip is capable of.

