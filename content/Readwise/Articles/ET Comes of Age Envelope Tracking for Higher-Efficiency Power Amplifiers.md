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

The system involves the use of two amplifiers: The main Linear [[Power Amplifier]] and an [[Envelope Amplifier]]. The envelope amplitude signal is generated in the transceiver, along with the carrier modulated RF signal that needs to be amplified. The envelope signal is amplified to provide a dynamically varying power supply to the main RF PA.

![](https://readwise-assets.s3.amazonaws.com/media/reader/pub/587ee791be1ce7641e000fe98624dca5.png?t=1698794317831)

The figure in (a) shows a varying signal  being amplified by an amplifier with constant power supply voltage. At any time, the power dissipated is proportional to the product of the current value and the available voltage overhead. 

In figure (b), the ET amplifier controls the voltage overhead by adjusting the power supply voltage to track the signal envelope. As a result, the voltage overhead is much smaller, and the power dissipation is minimized.

The efficiency improvement using ET is substantial, and approaches class B amplifier efficiency of 78.5% but is usually lower in practice due to losses involved. The key difference here is that high efficiency is maintained even when output power is backed off. The design of the envelope amplifier is also challenging in terms of accuracy, efficiency and slew rate needed for amplification of a dynamically varying signal. This ends up limiting overall efficiency as well.

![](https://readwise-assets.s3.amazonaws.com/media/reader/pub/d692efaedde4a13aa1ad1652be9d7715.png?t=1698794110583)



## Highlights

-  ([View Highlight](https://read.readwise.io/read/01he409x4y6v82nr55yg7g69v8))
- efficiency—so that the battery does not drain too fast and the phone does not get too hot to hold! ([View Highlight](https://read.readwise.io/read/01he427rwj29cqhz7nskqxxx69))
- The efficiency gains from ET compared to class-AB operation are also of major importance for the overall base-station power budget and have led to substantial research for ET in highpower systems (10–40 W average power) at 1–2 GHz. ([View Highlight](https://read.readwise.io/read/01he429sbexerwvvfb42ftn09b))
- To handle the high PAPR values associated with the downlink signals, virtually every base station uses an advanced architecture for backoff efficiency improvement: the Doherty architecture, outphasing, or ET. ([View Highlight](https://read.readwise.io/read/01he42abfkhw7re9vta1nzvrjq))
- Early modulation techniques adopted in the AMPS (i.e., Advanced Mobile Phone System) and GSM (i.e., Global System for Mobile) wireless standards used constant envelope signals, so PAs were operated in their most efficient mode. But codedivision multiple-access (CDMA), wideband CDMA (WCDMA), and LTE standards used in 4G wireless communications have changed the picture. ([View Highlight](https://read.readwise.io/read/01he423rznqkm9wmq28vpcwe70))
- For simplicity and high performance, as well as to minimize changes from the earlier typical class-AB amplifiers, most base stations today use the Doherty transmitter architecture. ([View Highlight](https://read.readwise.io/read/01he42cbdr47r8hpaa7yawezzb))
- The prospects for ET in handsets became brighter when it was shown that the envelope amplifier could be integrated into a single complementary–metal-oxide-semiconductor (CMOS) integrated circuit (with an off-chip inductor) [11]. ([View Highlight](https://read.readwise.io/read/01he426bgj1z95cj0r0yysth58))
- More recently, with the introduction of LTE, PAPR values have shot up, in some instances to over 10 dB. ([View Highlight](https://read.readwise.io/read/01he4270k1zjvesfj8hn0gn0ep))
- For these heroic efficiency results, the basic RF PA op- ([View Highlight](https://read.readwise.io/read/01he5h9kt47w060md2hfd0dgj2))
- ET is now viewed as a preferred method for maintaining PA ([View Highlight](https://read.readwise.io/read/01he427fkq2g1q2v3phjsj4ypn))
- erates at above 80% ([View Highlight](https://read.readwise.io/read/01he5haaztwj4q0qcba6sgjnn3))
- efficiency (as shown in Figure 5) using gallium nitride (GaN) transistors in nearly switching-mode operation, ([View Highlight](https://read.readwise.io/read/01he5h9z9v8vqmw3n94e7hm794))
- But the efficiency of ET transmitters currently in development tends to drop off with wider bandwidths, and the margin over Doherty PAs gets eroded ([View Highlight](https://read.readwise.io/read/01he5hawka7t5nch080j938hzg))
- the choice of one architecture versus the other will be different if the same PA is required to work with a wide range of carrier frequencies. ([View Highlight](https://read.readwise.io/read/01he5hbb071xdctg01wcqprk3n))
- ET outperforms other architectures ([View Highlight](https://read.readwise.io/read/01he5hcn6nhbjse8gshn244r0c))
-  ([View Highlight](https://read.readwise.io/read/01he40g716dfwpzyhg01nhpsvz))
- if the output power must change over a large range­—for example, if the base station’s average power varies by 10 dB from daytime to nighttime, the power variation is outside the range over which a Doherty can comfortably operate, but it could be accommodated with an ET amplifier. ([View Highlight](https://read.readwise.io/read/01he5hd6rkcmzsmxd176nan4r4))
- most cell phones today use a simplified form of ET, called average power tracking, or APT. ([View Highlight](https://read.readwise.io/read/01he5heg3yz6wzagahvx1rhhs1))
- The power supply voltage is changed on a minute-to-minute, or even second-to-second, basis using a dc-dc converter chip in the cell phone. ([View Highlight](https://read.readwise.io/read/01he5hf0706qdsb28ntkqf3qd5))
- h ([View Highlight](https://read.readwise.io/read/01he5hksmhfa8drvrs15pdg3fd))
- ![](https://readwise-assets.s3.amazonaws.com/media/reader/pub/d4f3b6830a709e8ded473f014661ce96.png?t=1698845745845) ([View Highlight](https://read.readwise.io/read/01he5hhmkbrppy4rxgewepjzbk))
- The emerging situation, however, is for a change to full ET: the dynamic power supply voltage will be varied at the full bandwidth of the envelope signal. ([View Highlight](https://read.readwise.io/read/01he5hm5y9w139qv300b59rb63))
- t is now being introduced ([View Highlight](https://read.readwise.io/read/01he5hmd0ah3bb7y52g0yfqy3d))
- The dynamic supply waveform and the RF signals must arrive at the RF PA properly time-aligned with one another ([View Highlight](https://read.readwise.io/read/01he5hr8h5g4j5eea4ta95wh5m))
- if not, both output fidelity and efficiency suffer. ([View Highlight](https://read.readwise.io/read/01he5hrdmpggp6v2x4azr4sykk))
- ![](https://readwise-assets.s3.amazonaws.com/media/reader/pub/d7964a8eb57726c37251005b3c2eb259.png?t=1698846309105) ([View Highlight](https://read.readwise.io/read/01he5j2vrpqrz7q9xfevyhdmm3))
- today’s systems incorporate feedback control systems to adjust the timing. ([View Highlight](https://read.readwise.io/read/01he5hs7mdy1ybhbrqtphtq6r3))
- The control can be exercised with a closed-loop monitoring system, which feeds back a replica of the PA output, downconverts and digitizes it, and compares the result with the desired signal. Any differences are reduced by predistorting the signal in the baseband signal processor. ([View Highlight](https://read.readwise.io/read/01he5htcg1j1xare2jyxmcmnxp))
- The signal correction technique—referred to as adaptive digital predistortion (DPD)—is already used almost universally in base-station PAs, whether or not they use the ET technique. ([View Highlight](https://read.readwise.io/read/01he5hv38388d88yxqdc890ee9))
- ![](https://readwise-assets.s3.amazonaws.com/media/reader/pub/64b541454955ffda64404c3e4f56e925.png?t=1698846319542) ([View Highlight](https://read.readwise.io/read/01he5j35vjas80qsnp68d2mc79))
- into high-end handsets and smartphones, driven by the higher PAPR’s of LTE signals. ([View Highlight](https://read.readwise.io/read/01he5hmvn1tcxn4h1362cq6tq2))
- the cost of DPD is continuously dropping as a result of Moore’s law advances, so the extra burden on the system power budget from DPD is becoming less significant. ([View Highlight](https://read.readwise.io/read/01he5hx8hng3ss49cs0w4ah5jk))
- for ET an appropriate dynamic supply voltage signal must be delivered to the envelope amplifier. This signal can be generated from the RF signal envelope itself, but it is easier to leverage modern transmitter architectures and generate the dynamic supply signal in digital baseband. ([View Highlight](https://read.readwise.io/read/01he5hpadsb5hshk65t2avdg41))
