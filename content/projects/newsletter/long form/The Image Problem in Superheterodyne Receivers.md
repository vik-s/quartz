---
title: The Image Problem in Superheterodyne Receivers
tags:
  - systems
project: substack
date_published: 
status: 🚧
final title:
---
In a previous article, we looked at the superheterodyne receiver architecture and the story of Armstrong, Sarnoff and RCA. What we did not cover in detail is the problem of image frequencies and the problems they pose in an RF receiver.

In this article, you will learn:
- topic 1
- topic 2
- topic 3

Let's dive in!

### The Mixing Operation

The heart of the superheterodyne receiver lies in the conversion of the amplified RF modulated signal into a lower "intermediate" frequency (IF) by the mixer. At lower frequencies, amplifiers are easier to design and filters have more selectivity. This is why the superheterodyne works so well.

The mixing operation in the time domain is simply an analog multiplication of two signals: the RF modulated signal and a local oscillator (LO) signal. In the frequency domain, this is a convolution of the two signals.

Let's say that the RF and LO signals are both cosines with angular frequencies wRF and wLO. There is a good reason we use cosines, we will see why later. The multiplication of these cosines results in four distinct frequency products. The sum and difference between the two signals in the positive and negative frequency domains. This is the result of simple trigonometry when multiplying two cosines.

The concept of negative frequency is confusing, and we will get to that in the next section. For now, just know that a real signal needs to have a positive and negative frequency component which are equal. In real life measurement, we just deal with positive frequencies and things are just fine.

The modulated RF signal is not a pure cosine, and has some bandwidth associated with it. The process of mixing moves the whole spectrum of the RF signal to the new sum and difference frequencies. In practice, the frequency translation looks something like the figure below.

Fig1.

In reality, we want to convert a particular RF channel of fixed bandwidth to IF. We have two options:
1. Have a fixed LO signal, which results in different IF.
2. Have a variable LO signal, which results in fixed IF.

Of these choices, option two is the better one. It is much more challenging to design low loss, high rejection IF filters that are also tunable. A variable LO is much easier to generate using a frequency synthesizer circuit, which can be designed to be highly accurate and stable.

Let's make a short detour to understand negative frequencies before we proceed with  superheterodyne mixing.
### The Need for Negative Frequencies



Stuff to write about
- Function of the mixer
- What negative frequency really means? Not much consider cosine func
	- https://dsp.stackexchange.com/a/449
	- https://www.researchgate.net/publication/261779218_Understanding_Digital_Signal_Processing's_Frequency_Domain
	- https://www.mathworks.com/matlabcentral/fileexchange/53410-complex-sinusoids-interactive-demo
	- https://www.youtube.com/watch?v=_3-qntJ12q4
- What about an N-channel band?
	- Fixed LO and different IF, or <-- requires tunable filters
	- Variable LO and fixed IF <-- this is more common (use freq synthesizer)
- Describe the image problem
- Choice of IF and related filtering concerns
- High side versus low side injection; which is better? why?
- How multiple IF receivers can help?
- What metrics are used to quantify image rejection?