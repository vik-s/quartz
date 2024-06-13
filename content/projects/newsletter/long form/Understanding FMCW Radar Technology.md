---
title: Understanding FMCW Radar Technology
tags:
  - systems
project: substack
date_published: 
status: 🚧
final title:
---
In this article you will learn:
- Differences between pulsed and continuous-wave radar
- Use of doppler effect, beat frequency and frequency modulation in distance measurement.
- Design of frequency chirps for FMCW radar
- Radar range versus resolution trade-off

Read time: X mins
## Need for Automotive Safety 

According to the [2023 WHO report](https://iris.who.int/bitstream/handle/10665/375016/9789240086517-eng.pdf?sequence=1), there are over a million worldwide road traffic fatalities every year, with the highest fatalities occurring in the southeast asian region (28% of global). It remains the leading cause of death for children and people under 30, and worldwide initiatives have been taken to improve road safety. For example, [Vision Zero](https://visionzeronetwork.org/about/what-is-vision-zero/) is a project initiated in the 1990s whose focus is on achieving zero traffic fatalities and injuries through technology, policy, and design.

Today, the rise of electronics in automobiles has enabled safety features that allow the driver to actively avoid fatal mistakes increasing both driver and pedestrian safety. [Reports](https://finance.yahoo.com/news/automotive-safety-system-market-projected-072700837.html) place the total market for automotive safety systems at over 200 billion by 2030 with an annual growth rate of 9%.

Among these safety features are adaptive cruise control, blind spot detection, rear collision warning, lane departure warning, lane keep assist, and automatic emergency braking and steering. Advanced Driver-Assistance Systems (ADAS) are designed to help implement these technology features in automobiles.

An essential element of ADAS systems is RADAR, which stands for RAdio Detection And Ranging. Radar has been around for a good part of a century, but its use for automotive safety has been much more recent. For example, the 5th generation Waymo Driver had [6 radar sensors](https://www.sensortips.com/featured/what-sensors-make-the-latest-waymo-driver-smarter/), along with a variety of ultrasonic, camera and lidar sensors.

![[Newsletter_Images/022_FMCWRadar1/Renesas_radar-ADAS-pt1-why-need-radar-fig2.jpg]]
Source: https://www.renesas.com/us/en/blogs/why-do-we-need-radar

One of the key components of automotive radar is the Frequency Modulated Continuous Wave (FMCW) radar. FMCW is a continuous wave radar, which means that the RF signal is continuously present during the period of radar sensing. This is distinct from pulsed radar, which transmits short bursts of energy and waits for the reflected signal to arrive. The frequency modulation (FM) means that the frequency of the RF signal is not constant, but instead continuously changes for a fixed time interval. We'll dig into these ideas next.

## Pulsed vs Continuous-Wave Radar

There are two approaches to radar detection that we should define and discuss:
- **Pulsed Radar**: In this radar, a short burst of RF energy for a known time duration is transmitted. The signal travels to an object, bounces off it, and hits the receiver. The distance to the object is calculated from the round trip delay.
- **Continuous-Wave (CW) Radar**: In this radar, there is no distinct start and stop times to the RF energy. The signal is continuously transmitted and received at all times. Since there are no defined transmission intervals, round trip delay measurement is not possible. Thus, special methods are used to estimate distance as we will see shortly.

The downsides of pulsed radar are the following:
- The burst of RF energy needs to be sufficiently high powered so that the reflected signal reaches the receiver with good fidelity. This makes the design of transmit amplifiers expensive and challenging.
- It is difficult to measure short ranges because the pulse duration needs to be extremely short. As a result it is better for longer range applications. 
- The time taken to switch from transmit to receive mode presents a 'blind spot' where no radar tracking is available.

Pulsed radar does have its use cases when long range, high speed target tracking is needed, particularly for military applications. It is also useful when fine resolution is need between radar targets.

On the other hand, CW radar can utilize lower power transmit signals which makes the design of radio electronics much easier for automotive safety applications.  CW can be designed to have short, medium or long range capability depending on system design and since the RF signal is always on, CW radar does not have any blind spots. 
## The Doppler Effect

Round trip delay measurement is possible in pulsed radar to estimate distance. CW radar relies on doppler effect, beat frequencies and frequency modulation to estimate distance. We will see how.

The doppler effect is a phenomenon where the frequency of a signal source shifts if it is moving towards or away from an observer. Think of the sound of an approaching and receding train horn. When the signal source is moving towards the observer, the frequency shifts to higher values, and vice versa. **In CW radar, the velocity of an object can be measured from doppler shift of the RF frequency**. 

The doppler frequency shift in a CW radar due to an object moving at 100-200 mph is in the range of kilohertz for an RF signal in the 77-81 GHz range, a licensed frequency band for automotive radar. The detection of this shift is done by multiplying the received signal with the transmitted signal in a mixer, resulting in sum and difference frequencies. The sum frequency will be in the 150 GHz range and is easily filtered out by a low-pass filter that only allows the difference frequency (or beat frequency) in the kilohertz range through.

Due to the [image problem](https://www.viksnewsletter.com/p/the-image-problem-in-rf-receiver?r=222kot&utm_campaign=post&utm_medium=web) we discussed earlier in the context of radio receivers, the beat frequency is the same whether the received signal is above or below the transmitted signal. Hence, we cannot tell if the object is moving toward or away from the receiver. To resolve this we need another transmitted signal offset by 90 degrees in phase to generate in-phase and quadrature (IQ) components, mix them both down and examine their phase components. Just know that for now, and we'll maybe get into this at another time.

Range (a radar term for distance) measurement requires one more trick - the use of frequency modulation (FM).
## Linear Frequency Modulation

In both pulsed and CW radar, the RF signal used  linearly increases in frequency from one value to another in a fixed time period. It is sometimes called a *chirp*, whose frequency-time plot is shown below. The use of a chirp has quite a few advantages.

The linearly frequency modulated RF signal goes from a starting frequency F1 to an ending frequency F2 during a time period called the chirp duration Tc. The bandwidth of the chirp B (=F2-F1), and the frequency slope S (=B/Tc) are critical system parameters.

> Put *picture of a chirp signal* Compressed HI Resolution Pulse

But why go through the trouble of generating such a signal?
### Pulsed Radar Chirps

To understand why in the context of pulsed radar, we need to understand the concept of a matched filter. A matched filter is a signal processing idea used to extract a known signal from a noisy signal, like the one received by radar. The way this works is to find out how correlated the received signal is, to a known waveform known as a *template* signal. This is done by *convolving* these two signals together (a unique mathematical operation quite common in signal processing). 

> Put *picture of matched filter operating*

The transmitter sends out a RF pulse at a certain frequency for a duration Tc. It is reflected from a target and received along with noise. The received signal is convolved  with a constant frequency pulse as template signal. As long as the pulse does not overlap the template, the correlation is zero. As the pulse starts to overlap, there is some correlation, and it reaches a maximum when it is completely aligned.

The peak of the matched filter output tells us the delay between the transmitted and received waveforms and is useful for calculating the distance of the target object. Using a constant frequency pulse has two problems:

**SNR**: As the noise level rises, it quickly becomes difficult to tell where the peak is. We could increase the power level of the transmitted pulse, but it makes it hard to design linear transmit amplifiers that work well.

**Resolution**: If there are reflections from two targets, the received pulses might overlap making it difficult to detect any peaks. The ability of a radar to distinguish between distinct objects is called its *resolution*. To improve resolution, we could make the pulses shorter to minimize the overlap between signals. But shorter pulses are harder to distinguish from noise. There is always a trade-off between resolution and SNR.

The ability to resolve targets in the presence of noise dramatically improves when a chirp is used. When an RF signal with continuously increasing frequency is used, the output of the matched filter produces sharper peaks. To understand how, let's look at the correlations of a received chirp with its corresponding template signal.

> Put *pictures of FMCW matched filtering*.

As before, when the two signals do not overlap, the correlation is zero. When they start to overlap, the correlation is still low because the waveforms do not line up when they are of different frequencies. The correlation is maximum only when the two FMCW signals exactly line up. This results in a more detectable peak that is easy to identify even in the presence of noise. The sharper peaks will also be separate when two reflected signals overlap due to their different frequencies at any instant of time.

Put *pictures of how FMCW matched filter operation gives sharper peaks even in the presence of noise, and how overlapping signals produce distinct peaks.*

In summary, **the use of a chirp signal results in distinct peaks after matched filtering that are much more easier to detect compared to constant frequency signals.**
### FMCW Radar

The block diagram of an FMCW radar is shown below. A frequency synthesizer generates a series of chirps that resembles a saw tooth waveform in the frequency-time axes, that is amplified and sent out via the transmit antenna. The signal travels through the air, bounces off the object and is received by the RX antenna.  The received signal is mixed with the original synthesized signal to generate an intermediate frequency (IF), much like in a [superheterodyne receiver](https://www.viksnewsletter.com/p/how-a-superheterodyne-transceiver?r=222kot).

Put *picture of FMCW radar system*

If the target is stationary, then the received signal is a chirp delayed in time. The delay in the signal is the time taken by the signal to travel to the object located at a distance d, and back, divided by the speed of light. The mixing operation results in an intermediate frequency that is proportional to the distance of the object. If S is the frequency slope of the chirp signal, the IF is calculated as
$$ IF = S.\frac{2d}{c} $$
The IF signal is digitized by the analog-to-digital converter (ADC) only in the time window where both transmitted and received chirps are present. In practice, the delay between transmitted and received chirps is quite small, usually under 5% of the total chirp period. So both chirps are available for over 95% of the sensing period to generate an IF.

#### Range Resolution
If there are multiple targets in the radar sensing field, then multiple reflected chirps will be received by the radar, which will produce multiple IF. 

> The ability to resolve two nearby objects is called the range resolution of a radar. 

To be able to distinguish between two tones in a frequency versus distance plot (also called a range FFT), we need to have two separate peaks in the spectrum. The ability to distinguish between peaks depends on the duration of the chirp signal Tc. A higher time-window allows for better resolution of closely spaced objects. For the same frequency slope S, this means a higher frequency sweep bandwidth B.

Two IF signals spaced Δf apart can distinguished if Δf > 1/Tc. Using our earlier relationship mapping IF to distance, the range resolution of a radar is given by
$$ d_{res} = \frac{c}{2B} $$
**To improve resolution of two nearby objects, a higher frequency bandwidth is needed for the chirp signal.** An RF chirp from 77GHz - 81 GHz (B=4GHz) translates to a range resolution of 3.75 cm.
#### Maximum Range
How far an object can be and still be sensed by the radar depends mainly on the ADC bandwidth available to digitize the IF signal. For a far away object, the IF signal frequency will be higher and the ADC bandwidth should be sufficiently large to handle that. For an ADC sample rate Fs, the maximum range of the radar is given by
$$ d_{max}=\frac{F_s c}{2S} $$
This tells us that for a given ADC sampling rate, the maximum range can be improved by lowering the frequency slope of the chirp.
#### Resolution versus Range Trade-off
Consider two chirp signals with the same frequency sweep bandwidth B. Chirp X has a longer chirp duration, but lower frequency slope. Chirp Y has a shorter chirp duration but higher frequency slope.

Both chirps give the same range resolution because they have the same bandwidth. However, because chirp X has a lower slope, it generates lower IF frequencies. This means that the ADC bandwidth requirements are more relaxed for chirp X and therefore is capable of sensing greater distances. While chirp Y is capable of faster sensing due to smaller chirp duration, it places a higher specification on ADC performance and corresponding limitations in maximum range.


Some questions to be answered:
- How does the radar estimate range of the object in front of it?
- What if there are multiple objects?
- How can two closeby objects be resolved?
- How far can a radar sense an object?



- Companies doing Automotive safety stuff
	- https://inrix.com/industries/automotive/
	- https://www.perciv.ai
	- https://www.aptiv.com/en/solutions/advanced-safety
	- https://www.continental-automotive.com/en.html
	- https://www.magna.com/products/electrical-electronics/adas-automated-driving
	- https://www.autoliv.com/safety-solutions
	- https://www.bosch-mobility.com/en/solutions/driving-safety/integrated-safety-systems/
	- https://www.qualcomm.com/products/automotive/automated-driving

UWB Sensing: https://novelda.com/technology#

Market Research
- https://www.mordorintelligence.com/industry-reports/automotive-safety-systems-market

https://www.ti.com/video/series/mmwave-training-series.html

![[projects/newsletter/long form/Understanding FMCW Radar Technology 2024-06-09 10.33.39.excalidraw]]