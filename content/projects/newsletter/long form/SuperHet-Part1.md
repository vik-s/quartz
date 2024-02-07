---
title: Basic design considerations in a superheterodyne radio receiver
tags:
  - systems
project: substack
date_published: 
status: 🚧
final title:
---
Transceiver architectures are a vast topic and hardly possible to cover in any detail in a single newsletter edition. Instead, I will write it as an ongoing series that I will keep adding to. This way, each newsletter will still take only 5-10 minutes to read. To keep it interesting, I'll write about other things too in the weeks that follow.

 
 http://www.hammondmuseumofradio.org/Fess_voice_trans.AIFF
### A Brief History

For the last 100 years, the Superheterodyne receiver has been one of the greatest inventions in the history of radio communication. Before we get into the details of its construction and design, its time for a little story.

Superheterodyne architecture was the brainchild of Edwin Howard Armstrong, one of the most brilliant engineers of our time. While he was a student at Columbia, he discovered that an amplifier's gain can be enhanced by positive feedback. A term he called "Regeneration." With sufficient feedback, he could design an RF oscillator, which was the first source of RF energy from a vacuum tube.

To do this, he used a vacuum tube invented by a scientist named Lee DeForest, whose love for science was only trumped by his love for money. As soon as he learned of Armstrong's regeneration, he took him to court, claiming that he had discovered it two years prior. Litigations are common, yes, but this one continued for the next 20 years, reaching the supreme court. You will see why this is important in a bit.

Armstrong used the concept of regeneration to build a receiver. The single vacuum tube acted both as a detector and as an amplifier. He used inductive coils to generate feedback and immediately saw the difficulty implementing it like this. He had to precisely adjust the coils orientation to provide just the right feedback at a given frequency, to get the receiver to work.

Interestingly another scientist named Reginald Fessenden conceived of the term hetero-(different) dyning (mixing). He viewed it as a beat frequency that you observe in audio whose frequency is the different of the two underlying frequencies. But he incorrectly "mixed-up" the phenomenon of interference with the multiplicative process of mixing two radio signals.

Armstrong eventually figured it out and put it to good use. Instead of trying to convert the modulated signal to audio frequencies, he converted it to an intermediate frequency range of about 10kHz. At these frequencies, vacuum tubes had enough gain that they did not need regeneration and its associated tuning headaches.

The superheterodyne receiver was born. His seminal 1924 paper on this explains everything that we identify as important today as radio engineers - oscillator stability and pulling, interstage interactions, need for filtering and impact of noise. It was way beyond its time to say the least.

Armstrong sold his superheterodyne patent to communications giant RCA, led by his longtime friend David Sarnoff. However, as radio communications became political, he found his FM broadcast system severely crippled and his unending patent battles against RCA broke his spirit. In 1954, Armstrong stepped out of the window of his New York Apartment. His body was found on a patio a few hours later by a custodian.

His wife eventually won all his lawsuits against RCA. The lawsuit he fought the hardest for, was his original one on regeneration which is no longer in use.  The superheterodyne receiver on the other hand has survived a century and shows no signs of being replaced.

Let's get into some engineering details.

### Superheterodyne Architecture
Instead of laying out the whole block diagram of the system and explaining how it works, I'd like to approach it differently in this series. We will build out each component of the superheterodyne receiver as the need arises and look at the design considerations of each block. I'll also use some real numbers for frequencies instead of just symbols to make it relatable.


### RF Front End Filtering
Let's consider an antenna receiving signals in a certain frequency band, say 2.4 GHz, a wireless LAN frequency. Depending on the standard, the frequency band is split into separate channels say 20 MHz in bandwidth. Our purpose is to extract the information present in the particular channel.

Ideally, we would like to filter out only the specific channel from the received signal. This would require a filter that has exceptional rejection to select only a few MHz around a center frequency of several GHz. Even if the construction of such filters were possible, high selectivity often comes at the price of high insertion loss. Higher rejection levels in a filter can only come from increasing the filter order, which increases filter loss.

This is an unacceptable system penalty to pay. The signal received by the antenna is already weak due to path loss, and excessive losses from filtering will degrade the signal further. The generally accepted solution is to just filter the entire frequency band, and not a specific channel, in order to remove unwanted interference.

We need to make in important distinction in terminology about interference. They can be of two kinds:

1. Out-of-band interference: These are unwanted signals present in the radio spectrum that do not belong to the communication standard of interest. For example: A GPS signal around 1.5 GHz would be out of band interference to a WLAN signal at 2.4 GHz.
2. In-band interference: These are unwanted signals present *within* the frequency band of interest and usually present due to communication signals in neighboring closely spaced channels.

The band select filter is filtering applied directly after the antenna, is usually implemented with acoustic wave filters. These filters are several orders of magnitude smaller than electromagnetic wave filters and are ideal candidates for portable communication devices. They have low loss and exceptional rejection.

They are of two types: 
1. Surface Acoustic Wave (SAW) filters: Cheaper to implement and less complex but limited to about 2.5 GHz in center frequency.
2.  Bulk Acoustic Wave (BAW) filters: More complex 3D structure, costlier but can be implemented to even 10 GHz and beyond. They offer better performance metrics than SAW filters for applications below 2.5 GHz. 

Fig? shows a comparison between SAW and BAW filters. The typical loss of these filters is 1-2 dB, and loss improvements even tenths of a dB are significant for such filters. 

that have good rejection and low loss to be used right after the antenna. Such a filter removes out-of-band interference from hitting the front of the LNA, and makes the LNA design simpler.

Our communication devices need to support many standards spanning over a range of frequencies. So in addition to a filter, most systems also use a band-select switch. These switches have to be very low loss, and handle sufficient power (while operating in transmit mode). 

These so-called RF Front End switches are an entire world of their own and entire companies exist just to make these switches as low-loss as possible.

#### Low Noise Amplifier


- Explain the superhet by building the system one component at a time
	- Antenna receives multiple channels in a radio band
	- Channels cannot be filtered, so a band select filter is used
	- It is amplified with LNA
	- Fed into mixer with a LO
		- Explain how mixing happens and what spectral components are made
		- Explain the problem of image
		- Somehow describe the problem of how many channels coexist and create a crazy number of mixing products
		- Low side and high side injection
		- Need for an image reject filter
		- Need for a channel select filter
		- Trade offs between image and channel select filter