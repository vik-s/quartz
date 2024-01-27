---
title: Calibration vs Deembedding
tags:
  - atomic
style: XvsY
written: ✅
published: ✅
---
In my very first job interview, I was asked what the difference is between calibration and de-embedding in s-parameter measurements. 

I remember stumbling through it. Here's my attempt at answering it this time:

First, what is common between them:

🔹 They both remove unwanted artifacts from measurement
🔹 They both move the measurement plane from the instrument terminal, to some required reference plane like the device terminals

But...

👉 Calibration involves the use of "well-defined" standards with which one can derive a full 8-term or 12-term error model to correct VNA measurements. They are usually very accurate, make few assumptions about the artifact being removed, and are quite reliable over a wide range of frequency. SOLT, TRL, LRRM are commonly used methods and each has it's own advantages and limitations.

👉 De-embedding instead uses "unknown" standards and is often used in places where "well-defined" standards cannot be effectively created. Accurate 50ohm loads are hard to create for SOLT in on-wafer or PCB environments, or line lengths are too long to implement for TRL in on-wafer low-frequency environments.

Instead, an equivalent circuit for parasitics to be removed is assumed, like a transmission line, PI or Tee network. Dummy structures are then measured and the parasitics are accordingly removed from the device measurement.  Due to the nature of assumptions made and design of dummy structures, de-embedding can be error prone if not done right.




Follow me (🔔) for posts on RF engineering.
Subscribe to my newsletter: https://www.viksnewsletter.com