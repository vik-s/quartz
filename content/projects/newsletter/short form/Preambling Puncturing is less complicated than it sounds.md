---
title: Preambling Puncturing is more complicated than it sounds
tags:
  - atomic
style: educational
written: ✅
published: ✅
---
Wifi 7 implements something called preamble puncturing. Fancy name but the idea is simple. 👇🏼

First know this: The maximum channel bandwidth in Wifi 7 is 320 MHz around 6 GHz. Super wide bandwidths for super speeds. Contrast this to 20 MHz channels in 2.4 GHz Wifi in earlier generations.

Here's the kicker. In most countries, the entire 320 MHz spectrum around 6 GHz is not entirely free. Other signals are present around these frequencies, and appear as wifi interference.

Say that the first 100 MHz is free, and then there's a 40 MHz interfering channel. The entire 320 MHz channel will be reduced to a 100 MHz channel. At least this is what used to happen in earlier wifi generations (with lower bandwidths of course.)

Wifi 7 allows Puncturing. This allows the rest of the channel to still be used for communications. In this example a 40 MHz wide interferer will still allow 280 MHz to be used.

As a result, users get much better speeds. WIfi 6 made puncturing optional, but wifi 7 makes it mandatory.

Seems like an obvious solution to the problem, doesn't it? I'm sure the details of implementation are much more complex.

My upcoming (in 2024) newsletter: https://www.viksnewsletter.com
Follow me (🔔) for posts on EE, career, and growth.







