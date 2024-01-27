---
title: What's the big deal about Wifi 7 anyway?
tags:
  - communication
project: substack
date_published: 2024-01-14
status: 🟢
final title: What's cool about WiFi 7
---
## Preview

1. ﻿﻿﻿What is the most important point?
	1. to learn the advantages of wifi 7
2. ﻿﻿﻿Why is that the most important point? (what can you achieve with it)
	1. lots of devices will support wifi 7 in 2024
	2. better understand how the tech you buy works
3. ﻿﻿﻿Why should people care? (what's the benefit)
	1. wifi 7 has some advanced features that are interesting to learn about
	2. people who work on these products in the job will have better appreciation
4. ﻿﻿﻿What is the easiest way to understand the most important point?
	1. contrast wifi 7 to what came before it via pictures
	2. cite real world examples of improved performance
5. ﻿﻿﻿How do you want the reader to feel?
	1. excited that wifi 7 is something amazing
6. ﻿﻿﻿What should the reader do next?
	1. subscribe to my newsletter
	2. go learn more about wifi7 if interested

## Outline

- What is Wifi-7?
	- Next gen wifi standard
	- List phones and routers already having wifi7
	- List some chipsets from companies doing Wifi7 - Qualcomm, Broadcom, MSI
- What is new about it?
	- List all it's features with one line explanation
	- Use the truck analogy from Intel (use pictures)
	- show picture showing evolution of wifi
- What is the real world experience?
	- Faster, more reliable
	- Need in AR/VR, 8k wireless video, etc
- Include a fun trivia piece

What about OFDM? Is it recently introduced or something?
https://www.tp-link.com/en/wifi7/#products

Beamforming is essential to make 4K QAM possible

Multilink mesh video -- its meh
https://players.brightcove.net/1414329538001/BJv5wEFt_default/index.html?videoId=6321581441112
embed code
```
<iframe src='//players.brightcove.net/1414329538001/BJv5wEFt_default/index.html?videoId=6321581441112' allowfullscreen frameborder=0></iframe>
```


whitepaper https://d86o2zu8ugzlg.cloudfront.net/mediatek-craft/documents/Key-Advantages-of-Wi-Fi-7_MediaTek-White-Paper-WF70222.pdf

From linkedin
> Unrelated to PP, the 802.11n made Dynamic Frequency Selection (DFS) mandatory in the 5 GHz bands in various countries where some of the spectrum had other higher priority use. There are specific requirements from FCC and ETSI on how soon the AP’s should vacate the spectrum in favor of higher priority usage.  Static PP replaces DFS in Wi-Fi 7, and is the reasons it was made mandatory.

----------------

Wifi 7 is the latest iteration of Wifi technology labeled as IEEE 802.11be. Before we go into any technical details, it begs the question: Do we really care about better Wifi?

Well, here's the thing. It is not sufficient to have a Wifi 7 enabled router. All your client devices have to support it to make best use of all the advanced features Wifi 7 has to provide. At the time of this writing, there are not a whole lot of client devices with Wifi 7 support but phones and laptops with Wifi 7 support will eventually roll out.

For most applications, Wifi 4 or 5 is probably sufficient. We have access to both 2.4GHz and 5GHz bands and sufficient bandwidth to perform most day to day tasks in a home environment. 

The need for performant Wifi emerges in dense enterprise networks when a large number of clients are present. The features of Wifi 7 will provide improvements in lower latency, improved reliability and faster speeds.

There are some specific cases in which this will be useful.

- Wireless backhaul: In a mesh router system, the connections between the wireless mesh units are connected by a high speed data link called the backhaul. This typically requires to be a high speed, high reliability connection. The faster speeds offered by Wifi 7 will provide enhancements in backhaul capability.
- AR/VR headsets: With the rise of Augmented/Virtual Reality (AR/VR) headsets in the market, there is a need for very low latency in the wireless connection between the headset and its peripherals. Users have reported feeling nausea (*insert link*) while using AR/VR headsets if this delay is high, and nobody cares for an ethernet cable running to their headset.
- 4k/8k video: uncompressed data rate up to 20Gbps

Even when all the hardware support between router and client is available, the software still needs to support advanced protocols used by Wifi 7. We will need Microsoft, Apple and Google to make the necessary drivers available to use in their operating systems to make the best of Wifi 7.

Now that the consumer aspects are out of the way, we can dig in to the engineering.

**Frequency Bands and Data Rates**
- WiFi 7 allows for the use of three different frequency bands - 2.4 GHz, 5 GHz, and 6 GHz. The 6 GHz frequency band with 1200 MHz of spectrum was added on for WiFi 6E in April 2020 by the US Federal Communications Commission (FCC).
- WiFi 7 provides higher channel bandwidths that allow for faster data rates. Here are the channel bandwidth allocations in each of the three frequency bands. You can see the detailed channel allocations [here](https://en.wikipedia.org/wiki/List_of_WLAN_channels)
	- 2.4 GHz - 11 channels at 20 MHz each
	- 5 GHz - 45 channels of 20 MHz each. It also allows the aggregation of channels into 40 MHz and 80 MHz channels. 
	- 6 GHz - 60 channels with up to 160 MHz bandwidth in WiFi 6E, and up to 320 MHz in WiFi 7. Higher bandwidth channels are creating by aggregating multiple 40 MHz channels.
- With the addition of these higher frequency channels and wider bandwidths, WiFi 7 is expected to provide a theoretical maximum data rate of 46 Gbps. In comparison, WiFi 6 has a theoretical maximum of 9.6 Gbps. Such data rates are rarely achieved in practice due to software and hardware limitations.
- ![[projects/writing/long form/Pasted image 20240101052409.png]]
Source: Spectrum needs of Wifi 7, Intel white paper.

**Modulation Scheme**
- Modulation scheme used in a WiFi standard represents how many bits of information are packaged into a symbol that is then transmitted. Higher the number of bits bundled, the more the data rate. It is also correspondingly harder for the receiver to discern which bundle of bits or symbol was received if there are too many of them to distinguish between. If the received symbol is wrongly interpreted, then the error rate of the wireless connection increases.
- In WiFi 6, 10-bits of data were bundled together and a modulation scheme called Quadrature Amplitude Modulation was used. The result was the use of 1024-QAM. This means that the receiver needs to accurately distinguish between 1024 different received symbols to interpret the received data without error.
- In WiFi 7, 12 bits were packaged up together in a symbol resulting in the use of 4096-QAM. This 4X increase in the number of symbols received makes the it quite a work of engineering to correctly interpret the received symbols. The result of using higher number of bits is a 20% increase in data rate due to choice of modulation scheme. 
- The use of a high order modulation scheme poses a strict –38 dB requirement on the constellation error vector magnitude (EVM) at the transmitter. Due to its inherent complexity, the modulation scheme is most effective only in the 6 GHz band over short distances and requires the use of beamforming to mitigate path loss.

**Multi Link Operation**
- This is one of the most prominent features in WiFi 7. MultiLink Operation (MLO) allows for the use of multiple simultaneous connections between access points over different channels, and even different frequency bands.
- Earlier WiFi generations made connections only over a single channel at a single frequency band. Even a triband WiFi 6E router connects devices on a single band over a fixed channel. If the connection quality was poor, the router had to manually switch over to a more reliable one.
- With MLO, there is significant improvement in reliability of the connection due to multiple redundant links being made simultaneously in addition to speed and latency improvements.
*draw a picture for MLO*

**Preamable Puncturing**

In Wi-Fi communication, the preamble is a part of the data packet transmitted over the Wi-Fi channel. It helps in synchronizing the receiver by providing a pattern that tells the receiver what to expect in terms of data that will be transmitted over the channel.

Consider the following problem scenario. Let's say there is a 40 MHz subchannel being occupied in a 160 MHz bandwidth channel. In earlier WiFi generations, this renders the rest of the 120 MHz of bandwidth useless within that channel.

Since WiFi 7 implements even wider 320 MHz channels, there needs to be a way to avoid wasted spectrum when a smaller bandwidth signal occupies a wideband channel. This is essential to implement in countries where there is a crowded spectrum around 6 GHz, where it is almost guaranteed that there will be a signal present over a wide 320 MHz spectrum at all times.

This is what preamble puncturing implements. If a 40 MHz signal is occupying a 320 MHz channel, the rest of the 280 MHz is still usable. By puncturing, or selectively omitting parts of the preamble in certain subchannels where there is already a signal present, the receiver is effectively told via the preamble that the rest of the channel still contains usable data. This was optional in WiFi 6 but WiFi 7 makes it mandatory. 

Due greater spectrum utilization in WiFi 7, faster data rates can be expected.

*add a picture of preamble puncturing*

**Increased spatial streams and MIMO**

Multiple Input Multiple Output (MIMO) refers to the use of multiple transmit and receive antennas to increase the throughput of a wireless connection. Different antennas receive signals at different times depending on how the transmitted signal bounces around its environment. The final received signal is reconstructed from the inputs of each receive antenna using signal processing algorithms.

The multi-antenna system is also used to transmit data in parallel using a combination of transmit and receive antennas. The higher the data transmission in parallel, the more the data rate over the wireless link. Each parallel data stream is called a spatial stream.

Early WiFi generations only supported 2 or 4 spatial streams, while WiFi 6 supported 8 spatial streams. In WiFi 7, this limit has been increased to 16 spatial streams resulting in a doubling of data rate over WiFi 6. To realize the full benefit of 16 spatial streams, the client devices need to let the access point know what the state of the wireless channel is, at any given point in time because the state of the channel is always continuously varying. To do this, the client performs "Channel Sounding" which evaluates the state of the channel and provides the access point with Channel State Information (CSI). The overhead to do this is pretty high especially given the large channel bandwidths used in WiFi 7. The 802.11be standard however implements some fairly sophisticated channel sounding mechanisms to reduce this overhead which is too detailed to get into here.

**Current Challenges and WiFi 8**

1. Co-existence in the 6 GHz band: 


I _have_ to draw the multilane highway analogy from intel

Wifi 8 (https://ieeexplore.ieee.org/document/9864321)
An October 2022 [IEEE](https://ieeexplore.ieee.org/document/9864321) document anticipates the release of Wi-Fi 8 in 2027 or 2028. More recently, Wi-Fi 8 is referenced by the [IEEE](https://ieeexplore.ieee.org/document/10314514) as 802.11bn.

https://www.arista.com/assets/data/pdf/Whitepapers/Arista-Wi-Fi-7-White-Paper.pdf
Wifi strikes back --- tells you about the SNR requirement of 38 dBm https://ieeexplore.ieee.org/document/9433521

What is MLO? https://www.tp-link.com/us/blog/1067/what-is-wifi-7-s-multi-link-operation-mlo-/

MediaTek MLO whitepaper : https://d86o2zu8ugzlg.cloudfront.net/mediatek-craft/documents/Wi-Fi-7-MLO-White-Paper-WF7MLOWP0622.pdf

Toms guide - a consumer explanation of wifi 7 https://www.tomsguide.com/reference/wi-fi-7-explained

Detailed PPT about transition from Wifi 6- 7 https://www.intel.com/content/dam/www/central-libraries/us/en/documents/2022-06/wi-fi-tutorial-long.pdf

