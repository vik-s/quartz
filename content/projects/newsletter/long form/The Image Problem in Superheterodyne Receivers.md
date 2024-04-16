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

Stuff to write about
- Function of the mixer
- What negative frequency really means? Not much consider cosine func
	- https://dsp.stackexchange.com/a/449
	- https://www.researchgate.net/publication/261779218_Understanding_Digital_Signal_Processing's_Frequency_Domain
- What about an N-channel band?
	- Fixed LO and different IF, or <-- requires tunable filters
	- Variable LO and fixed IF <-- this is more common (use freq synthesizer)
- Describe the image problem
- Choice of IF and related filtering concerns
- High side versus low side injection; which is better? why?
- How multiple IF receivers can help?
- What metrics are used to quantify image rejection?