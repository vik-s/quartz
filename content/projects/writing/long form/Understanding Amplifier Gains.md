---
title: Understanding Amplifier Gains
tags:
  - fundamentals
project: substack
date_published: 
status: 
final title: No more pain with amplifier gain
---
1. ﻿﻿﻿What is the most important point?
	1. To understand the various kinds of gain, when and where to use them.
2. ﻿﻿﻿Why is that the most important point? (what can you achieve with it)
	1. To fully understand what kind of performance an active device can provide
3. ﻿﻿﻿Why should people care? (what's the benefit)
	1. People can choose the correct technology if they understand it well
	2. Be more precise in understanding vendor datasheets
4. ﻿﻿﻿What is the easiest way to understand the most important point?
	1. Provide a visual that someone can pin up in their cubicle that tells you what gain is what
5. ﻿﻿﻿How do you want the reader to feel?
	1. Like they now clearly understand amplifier gains
	2. Happy they got a resource they can use at work
6. ﻿﻿﻿What should the reader do next?
	1. Share my visual and post on social media
	2. see if you can leave them with a small puzzle / homework problem?

*Section 4.6 from Rohde*
- 50ohm transducer gain is the smallest gain when no matching circuits are used (?)
- Masons gain is the highest gain obtainable from the device by lossless feedback and matching
	- People rarely design for unilateral gain because
		- It is narrow band
		- very sensitive to s-parameter accuracy, esp S12, which is very small.
		- hard to achieve stability at all frequencies in unilateral amplifier
		- it is only a figure of merit quoted by the manufacturer
- Table 4.5 shows 9 power gains with their equations
- Fig 4.10 shows various power gains vs freq, and what is higher and lower that what
- Otherwise this section of the book provides very little insight into what all this means

*Section 8.2.1 from Rohde*
- If k>1, both ports of the transistor can be conjugately matched to achieved G_ma, the maximum available gain.
- If k<1, carefully extract G_ms, max stable gain and stability across all frequencies
- A common misconception is that if k<1, then the max gain is G_ms. That is not true. The correct answer is infinity since the transistor may oscillate and deliver RF output power with only noise as input.
- A better way to interpret G_ms is to consider loading the transistor resistively till k=1, then match the two-port simultaneously. Then the gain in G_ms.
- This is not the recommended way to design amplifier because adding resistors usually degrades amplifier performance.
- The preferred way is to design the reflection coefficients looking into the source and load to be in the stable regions without adding resistors.

*Section 8.2.2 from Rohde*
- Gma is the gain, when k>1, and input and output are conjugately matched. The S11 and S22 values are zero. Gma_reverse can be used to specify the gain in reverse, and is related to S12.
- To push the gain beyond Gma, you need to unilateralize the 2-port with lossless feedback. The S11, S12, and S22 for this amplifier are zero. This gives Masons Unilateral gain and is the highest achievable *stable* gain at this frequency.
- The gain formulas usually only give the magnitude. The phase of the S21 will depend on the implementation on matching circuits, and there is no unique answer for phase S21 in the calculation of Gma.
- Fmax is the frequency where Masons gain is unity. Beyond fmax, the transistor is a passive component. It is also called maximum frequency of oscillation (probably because you need the device to still be active to create an oscillator)