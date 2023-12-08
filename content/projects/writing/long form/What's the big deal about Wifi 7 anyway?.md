---
title: What's the big deal about Wifi 7 anyway?
tags:
  - communication
project: substack
date_published: 
status: wip
final title:
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

Well, here's the thing. It is not sufficient to have a Wifi 7 enabled router. All your client devices have to support it too, to make best use of all the advanced features Wifi 7 has to provide. At the time of this writing, there are not a whole lot of client devices with Wifi 7 support but phones and laptops with Wifi 7 support will eventually roll out.

For most applications, Wifi 4 or 5 is probably sufficient. We have access to both 2.4GHz and 5GHz bands and sufficient bandwidth to perform most day to day tasks in a home environment. 

The need for performant Wifi emerges in dense enterprise networks when a large number of clients are present. The features of Wifi 7 will provide improvements in lower latency, improved reliability and faster speeds.

There are some specific cases in which this will be useful.

- Wireless backhaul: In a mesh router system, the connections between the wireless mesh units are connected by a high speed data link called the backhaul. This typically requires to be a high speed, high reliability connection. The faster speeds offered by Wifi 7 will provide enhancements in backhaul capability.
- AR/VR headsets: With the rise of Augmented/Virtual Reality (AR/VR) headsets in the market, there is a need for very low latency in the wireless connection between the headset and its peripherals. Users have reported feeling nausea while using AR/VR headsets if this delay is high, and nobody cares for an ethernet cable running to their headset.
- 4k/8k video: uncompressed data rate up to 20Gbps

Even when all the hardware support between router and client is available, the software will still need to support the advanced protocols used by Wifi 7. We will need Microsoft, Apple and Google to make the necessary drivers available to use in their operating systems to make the best of Wifi 7.

Now that the consumer aspects are out of the way, we can dig in to the engineering.

**Frequency Bands and Data Rates**
- 2.4GHz, 5GHz, 6GHz
- Up to 320 MHz channel bandwidth
- Provide at least 30 Gbps data rate

**Modulation Scheme**
- Wifi 6E had 1024 QAM but Wifi 7 has 4096 QAM
- Improve peak data rate by 20%

**Multi Link Operation**
- Multi-link operation (MLO) also debuts in Wi-Fi 7. Despite past Wi-Fi standards specifying many channels spread over several frequency bands, devices always made a link over a single channel at any one time. Wi-Fi 7 opens up the possibility of running multiple channels at once, even across multiple frequency bands. Using multiple channels and multiple frequency bands in a single aggregated connection should offer better speeds, significantly lower latency, as well as improved reliability, versus older Wi-Fi standards that had to manually switch between bands one at a time.

**Preamable Puncturing**
Wifi 7 implements something called preamble puncturing. Fancy name but the idea is simple. 👇🏼

First know this: The maximum channel bandwidth in Wifi 7 is 320 MHz around 6 GHz. Super wide bandwidths for super speeds. Contrast this to 20 MHz channels in 2.4 GHz Wifi in earlier generations.

Here's the kicker. In most countries, the entire 320 MHz spectrum around 6 GHz is not entirely free. Other signals are present around these frequencies, and appear as wifi interference.

Say that the first 100 MHz is free, and then there's a 40 MHz interfering channel. The entire 320 MHz channel will be reduced to a 100 MHz channel. At least this is what used to happen in earlier wifi generations (with lower bandwidths of course.)

Wifi 7 allows Puncturing. This allows the rest of the channel to still be used for communications. In this example a 40 MHz wide interferer will still allow 280 MHz to be used.

As a result, users get much better speeds. WIfi 6 made puncturing optional, but wifi 7 makes it mandatory.

Seems like an obvious solution to the problem, doesn't it? I'm sure the details of implementation are much more complex.

**Increased spatial streams and MIMO**
- From 8 spatial streams to 16
- 

I _have_ to draw the multilane highway analogy from intel




