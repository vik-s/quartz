---
title: Basic design considerations in a superheterodyne radio receiver
tags:
  - systems
project: substack
date_published: 
status: 🚧
final title:
---
Last week, I asked readers on Substack chat about what topics I should write about. There seemed to be considerable interest in transceiver architecture and design. But transceiver architecture is a vast topic and hardly possible to cover in any detail in a single newsletter edition. Instead, I will write it as an ongoing series that I will keep adding to. This way, each newsletter will still take only 5-10 minutes to read. 

In this article, you will learn:

1. What is Superheterodyne Architecture
2. A brief, but sad story about it
3. Band selection and filtering
### Superheterodyne Architecture

Fig ? shows the overall block diagram of a superheterodyne (superhet) receiver. Here is a top-level overview of what each block does. We will get into details in due time.
- Band select filter: Filters received antenna signal for a frequency band of interest
- Low-noise amplifier: Increases the received signal level while adding minimal noise
- Image reject filter: Rejects "image" frequencies that can corrupt the signal during the mixing stage that will follow (more on this later)
- Mixer: Uses a local oscillator (LO) to convert a high frequency signal to an intermediate frequency (IF)
- Channel select filter: Selects the particular channel within the IF range
- IF amplifier: The communication channel of interest is amplified for digital conversion.

The magic of this system essentially lies in the conversion of RF signals to IF. Some textbooks explain that this was necessary because good channel selection filters cannot be implemented at RF frequencies, and hence the need to convert to IF. Well, this is true, but history shows that conversion to IF is the very reason the system even works. Amplification at IF is much easier, and the filtering being simpler to IF is just an added bonus.

We also won't differentiate between heterodyne and superheterodyne here. The distinction does not add much value to the system's operation itself.

Instead of trying to explain how the system works all at once, our approach will be to go through it a little bit at a time. There are many considerations in the design of such a system such as noise, linearity, choice of frequencies, and implementation choices. Where possible, I will provide approximate ranges of numbers for gain, loss, noise and linearity of various blocks in the system so that you can get an "engineering-sense" of what is involved.

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
### RF Band Selection Filtering

Modern 5G technology has enormous RF complexity with multiple frequency bands, complex modulation schemes, and high number of antennas. Fig ? shows the increasing complexity of the system for different communication standards. For all of this to work together, RF filtering is of utmost importance to minimize interference. 

For simplicity, let's consider an antenna receiving signals in a certain frequency band, say 2.4 GHz, a wireless LAN frequency. Depending on the standard, the frequency band is split into separate channels say 20 MHz in bandwidth. Our purpose is to extract the information present in the particular channel.

Ideally, we would like to filter out only the specific channel from the received signal. This would require a filter that has exceptional rejection to select only a few MHz around a center frequency of several GHz. Even if the construction of such filters were possible, high selectivity often comes at the price of high insertion loss. Higher rejection levels in a filter can only come from increasing the filter order, which increases filter loss.

This is an unacceptable system penalty to pay. The signal received by the antenna is already weak due to path loss, and excessive losses from filtering will degrade the signal further. The generally accepted solution is to just filter the entire frequency band, and not a specific channel, in order to remove unwanted interference.

We need to make in important distinction in terminology about interference. They can be of two kinds:

1. Out-of-band interference: These are unwanted signals present in the radio spectrum that do not belong to the communication standard of interest. For example: A GPS signal around 1.5 GHz would be out of band interference to a WLAN signal at 2.4 GHz.
2. In-band interference: These are unwanted signals present *within* the frequency band of interest and usually present due to communication signals in neighboring closely spaced channels.

The band select filter is filtering applied directly after the antenna, is usually implemented with acoustic wave filters. They work by converting an electrical signal to an acoustic signal, which then travels across the filter, and converted into an electrical signal again. These filters are several orders of magnitude smaller than electromagnetic wave filters and are ideal candidates for portable communication devices. They have low loss and exceptional rejection.

They are of two types: 
1. Surface Acoustic Wave (SAW) filters: Cheaper to implement and less complex but limited to about 2.5 GHz in center frequency.
2.  Bulk Acoustic Wave (BAW) filters: More complex 3D structure, costlier but can be implemented to even 10 GHz and beyond. They offer better performance metrics than SAW filters for applications below 2.5 GHz. 

Fig ? shows a comparison between SAW and BAW filters. The typical loss of these filters is 1-2 dB, and loss improvements of even tenths of a dB are significant for such filters. 

After the band select filter is usually a band select switch as shown in the block diagram of a 5G smartphone below. For example, in 5G, the n77 band spans 3300-4200 MHz while the n79 band spans 4400-5000 MHz. The purpose of this switch is to deliver the signal to the correct LNA depending on the frequency band of operation. 

Since band-select switches are before the LNA, they are designed to have low loss (<1 dB). When used in the transmit path of the system, these switches also need to have high linearity (IIP3 > 80 dBm) and high power handling (>40 dBm) so that they can support high power levels while not producing unwanted spectral components.

### Low Noise Amplifier



https://www.qorvo.com/resources/d/qorvo-a-new-generation-of-5g-filter-technology-baw-white-paper (for picture of RF complexity in filtering)

https://www.qorvo.com/design-hub/blog/baw-vs-saw-rf-filters

[Front End Components and Limitations](https://transition.fcc.gov/bureaus/oet/tac/tacdocs/meeting71612/FilterDesignTutorial.pdf)




