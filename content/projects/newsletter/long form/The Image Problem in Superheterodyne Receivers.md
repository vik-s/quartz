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

To many, including myself until I actually looked into it, the concept of negative frequency seems almost... unreal. After all, when we measure a sinusoidal tone, we only see one line on the spectrum analyzer screen. But, we are looking at only half the story.

To see the whole picture, we need to look at complex sinusoids. In its polar form, it is represented as,
$$
x(t) = e^{j2\pi f_0t} = e^{j\omega_0 t}
$$
Thanks to Swiss mathematician Leonhard Euler, we can represent this quantity in rectangular axes (x=real, y=imaginary), using
$$
e^{j\omega_0 t} = \cos(\omega_0 t) + j\sin(\omega_0 t)
$$
This immediately tells us how to create a complex sinusoid in the lab, and transmit it to your buddy in the neighboring office. This is what you do:
- Take two sinusoidal signal generators set to the same frequency f0.
- Phase shift one of the signals by 90 degrees.
- Connect cables to both the original and 90 degree shifted signals.
- At the other end, connect them to the horizontal and vertical channels of an oscilloscope, respectively.
- You will see a spot rotating anti-clockwise on the screen as shown below.

*put animation of a rotating spot on the screen*

If you look at this in three dimensions, with time as the third axis, what you see is a helix that is propagating forward with time. Thus, the complex sinusoidal signal can be broken down into what are called its *in-phase* and *quadrature* components. This is a concept you will keep running into when you learn about RF systems.

*put animation of helix propagating*

Back to the case of a single cosine signal. Using Euler's identity, a cosine signal can be represented as
$$
\cos(\omega_0 t) = \frac{e^{j\omega_0 t}}{2} + \frac{e^{-j\omega_0 t}}{2}
$$
There it is. The negative frequency. Here is how you interpret it.

Your distracted office buddy accidentally swapped the sine and cosine signals. As a result, the spot on the oscilloscope now goes clockwise, instead of anticlockwise. In three dimensions, this would appear as a helix spiraling backward in time. That's pretty much all there is to it - a reversal of direction.

In polar form, a cosine wave has a positive frequency sinusoid rotating anticlockwise, with a negative frequency sinusoid rotating clockwise, such that **their imaginary parts always perfectly cancel**.

*put a picture of complex components of cosine*

How about a sinusoidal signal? Euler's identity tells us,
$$

\sin(\omega_0 t) = -j\frac{e^{j\omega_0 t}}{2} + j\frac{e^{-j\omega_0 t}}{2}
$$
The j-operator means you need a 90 degree shift, and the negative sign implies an additional 180 degrees. In the complex plane, you have the positive frequency at 270 degrees and negative frequency at 90 degrees, and they rotate in a way that the imaginary parts still perfectly cancel, giving you a pure sine wave.

*put a picture of complex components of sine*

We can now think of how this is all represented in the frequency domain. The components of a sine and cosine signal are shown in the figure below. The cosine just has two components with the same sign on the real axis. The sine has two components with opposite signs on the real axis. 

*put a picture of frequency domain representation of sine and cosine*

Now you can see why almost all technical analyses start with cosines - they are just easier without the j-operator and negative sign.

With the idea of negative frequency firmly planted in our minds, we can proceed with drawing more spectral diagrams for the mixing process.

### High- and Low-side Injection, and Image Problem












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