---
author: Peter Asbeck, Zoya Popovic
title: "ET Comes of Age: Envelope Tracking for Higher-Efficiency Power Amplifiers"
tags:
  - articles
  - amplifier
URL: https://www.colorado.edu/faculty/popovic-zoya/sites/default/files/attached-files/Asbeck2016.pdf
---
In typical class A, B, and AB amplifiers, the efficiency degrades when the amplifier is not operating in compression. When the power is in "back-off", the efficiency drops. This happens because energy not used to amplify a signal is still being used by the power supply, and dissipated as heat.

Envelope tracking is a way to minimize DC power usage when all of it is not necessary to amplify the signal. To do this, the power supply of the amplifier is continuously varied in sync with the *envelope* of the carrier modulated signal. The power supply *tracks* the envelope waveform, and hence the name "envelope tracking".

![](https://readwise-assets.s3.amazonaws.com/media/reader/pub/3c0ecb8d01abfabee02ff22c2c5f6000.png?t=1698794132803)

The system involves the use of two amplifiers: The main Linear [[Power Amplifier]] and an [[Envelope Amplifier]]. The envelope amplitude signal is generated in the transceiver as a digital baseband signal, along with the carrier modulated RF signal that needs to be amplified. The envelope signal is amplified to provide a dynamically varying power supply to the main RF PA.

![](https://readwise-assets.s3.amazonaws.com/media/reader/pub/587ee791be1ce7641e000fe98624dca5.png?t=1698794317831)

The figure in (a) shows a varying signal  being amplified by an amplifier with constant power supply voltage. At any time, the power dissipated is proportional to the product of the current value and the available voltage overhead. 

In figure (b), the ET amplifier controls the voltage overhead by adjusting the power supply voltage to track the signal envelope. As a result, the voltage overhead is much smaller, and the power dissipation is minimized.

The efficiency improvement using ET is substantial, and approaches class B amplifier efficiency of 78.5% but is usually lower in practice due to losses involved. The key difference here is that high efficiency is maintained even when output power is backed off. The design of the envelope amplifier is also challenging in terms of accuracy, efficiency and slew rate needed for amplification of a dynamically varying signal. This ends up limiting overall efficiency as well.

![](https://readwise-assets.s3.amazonaws.com/media/reader/pub/d692efaedde4a13aa1ad1652be9d7715.png?t=1698794110583)

Early modulation schemes used in Advanced Mobile Phone Systems (AMPS) and Global System for Mobile (GSM) used constant envelope signals. So the PA could be used in compression where it is most efficient. In modern communications like WCDMA and LTE, the high Peak-to-Average-Power-Ratio (PAPR), which is an indication of how high the amplitude peaks are compared to average, require the use of advanced PA design methods to maintain high efficiency.

In wireless base-stations, there has always been a need for advanced PA architectures to make sure they have high efficiency even when the power is backed off. They have always used either Doherty, outphasing or ET architectures. Efficiency improvements due to ET have led to significant research in high power (10-40W) ET architectures at 1-2 GHz. For legacy reasons, most base stations use Doherty amplifiers.

ET became a reality in handsets when the envelope amplifier could be implemented in CMOS with off-chip inductors. Most cell phones today use a simplified form of ET called Average Power Tracking (APT). The power supply voltage is changed on a minute-to-minute, or even second-to-second, basis using a dc-dc converter chip in the cell phone. 

One of the biggest challenges in implementation of ET is the envelope amplifier design for high signal bandwidths, where the efficiency improvement over Doherty PAs gets eroded. Another key requirement is that the envelope waveform and RF signal that arrive at the RF PA must be time-aligned. If not, PA linearity and efficiency suffer.

To ensure time alignment, you can implement a closed loop system that samples the output, downconverts and then digitizes it to compare with the desired signal. If adjustments are needed, they are made by pre-distorting the signal in the digital baseband. This technique is called adaptive digital predistortion (DPD) and is already used in PA systems whether ET is used or not.

![](https://readwise-assets.s3.amazonaws.com/media/reader/pub/d7964a8eb57726c37251005b3c2eb259.png?t=1698846309105)

![](https://readwise-assets.s3.amazonaws.com/media/reader/pub/64b541454955ffda64404c3e4f56e925.png?t=1698846319542)

As technology scales, the power burden of having a DPD system is becoming less significant, and the cost of DPD is also dropping.
