---
title: Basic design considerations in a superheterodyne radio receiver
tags:
  - systems
project: substack
date_published: 2024-02-18
status: 🟢
final title: The Dark History behind Radio Communication
url: https://www.viksnewsletter.com/p/how-a-superheterodyne-transceiver?r=222kot
---
Last week, I asked readers on Substack chat about what topics I should write about. There seemed to be considerable interest in transceiver architecture and design. But transceiver architecture is a vast topic and hardly possible to cover in any detail in a single newsletter edition. Instead, I will write it as an ongoing series that I will keep adding to. This way, each newsletter will still take only 5-10 minutes to read. 

In this article, you will learn:

1. Block Diagram of Superheterodyne Architecture
2. A brief, but sad story about it
3. Antenna Tuning
4. Front End Filtering
5. RF Switching
### Superheterodyne Architecture

Fig ? shows a simplistic block diagram of a superheterodyne (superhet) receiver and the function of each block.
- Band select filter: Filters received antenna signal for a frequency band of interest
- Low-noise amplifier: Increases the received signal level while adding minimal noise
- Image reject filter: Rejects "image" frequencies that can corrupt the signal during the mixing stage that will follow (more on this later)
- Mixer: Uses a local oscillator (LO) to convert a high frequency signal to an intermediate frequency (IF)
- Channel select filter: Selects the particular channel within the IF range
- IF amplifier: The communication channel of interest is amplified for digital conversion.

Instead of trying to explain how the system works all at once, our approach will be to go through it a little bit at a time. There are many considerations in the design of such a system such as noise, linearity, choice of frequencies, and implementation choices. 

The actual implementation of the system is much more complex due to the number of communication standards crammed into modern systems. The discussion of superheterodyne receivers here will be more involved and representative of actual implementation compared to textbook discussions of the topic.

But first...
### A Quick Story

For the last 100 years, the superheterodyne receiver has been one of the greatest inventions in the history of radio communication.

Superheterodyne architecture was the brainchild of Edwin Howard Armstrong, one of the most brilliant engineers of our time. While he was a student at Columbia, he discovered that an amplifier's gain can be enhanced by positive feedback. A term he called "Regeneration." With sufficient feedback, he could design an RF oscillator, which was the first source of RF energy from a vacuum tube.

To do this, he used a vacuum tube invented by a scientist named Lee DeForest, whose love for science was only trumped by his love for money. As soon as he learned of Armstrong's regeneration, he took him to court, claiming that he had discovered it two years prior. Litigations are common, yes, but this one continued for the next 20 years, reaching the supreme court. You will see why this is important in a bit.

Armstrong used the concept of regeneration to build a receiver. The single vacuum tube acted both as a detector and as an amplifier. He used inductive coils to generate feedback and immediately saw the difficulty implementing it like this. He had to precisely adjust the coils orientation to provide just the right feedback at a given frequency, to get the receiver to work.

Interestingly another scientist named Reginald Fessenden conceived of the term hetero-(different) dyning (mixing). He viewed it as a beat frequency that you observe in audio whose frequency is the difference of the two underlying frequencies. But he incorrectly "mixed-up" the phenomenon of interference with the multiplicative process of mixing two radio signals.

Armstrong eventually figured it out and put it to good use. Instead of trying to convert the modulated signal to audio frequencies, he converted it to an intermediate frequency range of about 10kHz. At these frequencies, vacuum tubes had enough gain that they did not need regeneration and its associated tuning headaches.

The superheterodyne receiver was born. His seminal 1924 paper on this explains everything that we identify as important today as radio engineers - oscillator stability and pulling, interstage interactions, need for filtering and impact of noise. It was way beyond its time to say the least.

Armstrong sold his superheterodyne patent to communications giant RCA, led by his longtime friend David Sarnoff. However, as radio communications became political, he found his FM broadcast system severely crippled and his unending patent battles against RCA broke his spirit. In 1954, Armstrong stepped out of the window of his New York Apartment. His body was found on a patio a few hours later by a custodian.

His wife eventually won all his lawsuits against RCA. The lawsuit he fought the hardest for, was his original one on regeneration which is no longer in use.  The superheterodyne receiver on the other hand has survived a century and shows no signs of being replaced.

Armstrong's invention makes modern communication possible, but humanity got it at a great price. With that appreciation, we can start looking at the system itself.
### Antenna Tuning

Early radio systems had a single antenna operating at a fixed frequency. A 5G smartphone operates over 50 bands ranging from 500 MHz to 6 GHz. While multiple antennas are required for dramatically different frequencies, it is only practical to reuse antennas for different frequencies by slightly tuning the existing antenna so that it works better. This is called Antenna tuning.

Antenna tuning involves the use of a bank of capacitors with switches that can be turned on or off with digital control. The digitally tunable capacitor bank is placed at the antenna input to provide a loading capacitance that can alter the performance of the antenna to make it more optimal.

By tuning the bank of capacitors, they usually perform two functions:

1. Antenna aperture tuning: the natural resonance of the antenna is shifted to the required band of operation. 
2. Antenna impedance tuning: optimizes the signal transmission to the antenna by providing the correct impedance environment between the antenna and the rest of the system.

Antenna tuners need to be low loss since they are directly connected to the antenna, and can drastically impact signal to noise ratio in the receive path, or overall system efficiency in the transmit path. 

The RF switches also need to have low capacitance so that the capacitance tuning range is only set by the discrete capacitors being switched. Otherwise, the tuning range (represented by C-max / C-min) becomes limited.

Since the antenna tuners appear after the power amplifier in the signal chain, they need to be able to handle high power while producing minimum distortion through nonlinearities.

A lot of such antenna tuner switches are implemented with Silicon-on-Insulator technology become of the low-loss and low-capacitance switches that can be implemented on it.
### Front End Filtering

Within each GHz frequency band in a communication standard, there are 20-320 MHz channels containing information that needs to be extracted. Ideally, we would like to filter out only the specific channel from the received signal. 

However, this would require a filter that has exceptional rejection to select only a few MHz around a center frequency of several GHz. Higher rejection levels in a filter can only come from increasing the filter order, which increases filter loss.

This is an unacceptable system penalty to pay especially for components that come between the antenna and LNA/PA. The generally accepted solution is to just filter the entire frequency band and not a specific channel, in order to remove unwanted interference. The bandwidth of the filter relative to its center frequency will be 5-10% which is much more reasonable to implement in practice.

Interference can be of two kinds:
1. Out-of-band interference: These are unwanted signals present in the radio spectrum that do not belong to the communication standard of interest. For example: A GPS signal around 1.5 GHz would be out of band interference to a WLAN signal at 2.4 GHz.
2. In-band interference: These are unwanted signals present *within* the frequency band of interest and usually present due to communication signals in neighboring closely spaced channels.

Only out-of-band interference can be rejected by filtering in the front end. The in-band interference will remain and it will be rejected after downconversion by the channel select filter.

Filtering in the front-end of the radio system is usually implemented with acoustic wave filters. They work by converting an electrical signal to an acoustic signal, which then travels across the filter, and is converted into an electrical signal again. These filters are several orders of magnitude smaller than electromagnetic wave filters and are ideal candidates for portable communication devices. They have low loss and exceptional rejection.

They are of two types: 
1. Surface Acoustic Wave (SAW) filters: Cheaper to implement and less complex but limited to about 2.5 GHz in center frequency.
2.  Bulk Acoustic Wave (BAW) filters: More complex 3D structure and costlier but can be implemented to even 10 GHz and beyond. They offer better performance metrics than SAW filters for applications below 2.5 GHz. 

Fig ? shows a comparison of insertion loss between SAW and BAW filters. The typical loss of these filters is 1-2 dB, and loss improvements of even tenths of a dB are significant for such filters. Such filters are used extensively in the RF front-end system to isolate various frequencies of operation and allow coexistence between the various communication standards.
### RF Switches

There are a various of RF switches used in a practical radio front end, that perform various functions. They are:

1. TR Switch: Switches between the transmit and receive paths in a time-domain-duplexed (TDD) system.
2. Antenna diversity or cross Switch: Used to switch between antennas so that the best one is selected for operation.
3. Band select switch: These are single-pole multi-throw switches that connect the signal to different narrowband amplifiers.

Depending on the use case and system design, there are a variety of switch designs that either emphasize on low loss, high isolation, high linearity and high power. Regardless of how it is optimized, they are still low loss components in the RF system because they are between the antenna and the amplifiers.

These switches are designed by stacking large sized silicon-on-insulator MOSFETs in series due to the low loss and high isolation capabilities of SOI technology. The number of transistors used in the stack determines the loss, isolation and power handling capabilities. 

As simple as the circuit topology sounds, the design of these switches are challenging and delicate. Multi-hundred million dollar companies are built on the back of components mentioned in this article alone!

In a future newsletter, we will continue down the superheterodyne chain!

https://www.qorvo.com/resources/d/qorvo-a-new-generation-of-5g-filter-technology-baw-white-paper (for picture of RF complexity in filtering)

https://www.qorvo.com/design-hub/blog/baw-vs-saw-rf-filters

[Front End Components and Limitations](https://transition.fcc.gov/bureaus/oet/tac/tacdocs/meeting71612/FilterDesignTutorial.pdf)

https://www.infineon.com/dgdl/Infineon-Wireless_Communication_AG_2023-ApplicationBrochure-v01_00-EN.pdf?fileId=5546d46277921c320177af53b9de548a



[[Excalidraw/superhet.excalidraw|superhet.excalidraw]]


