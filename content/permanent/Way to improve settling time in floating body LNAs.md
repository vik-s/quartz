---
title: "Way to improve settling time in floating body LNAs"
created: 2022-10-15 06:05
status: #permanent
tags: #ee/analog 
---

## Why does the [[LNA]] settle slowly?

There is no way for the charges in the body to be removed from a floating body device. They have to discharge slowly through the body-source and body-drain junctions through very slow recombination processes.

## What is the current solution?

Floating body device is made to have faster charge removal mechanisms from the body by increasing the rate of recombination in the body-source / body-drain junctions by engineering the interface to have higher trap states that can provide for extra recombination sites.

## What is the problem with this solution?

Recombination effects are very random and can take very long or very short times to complete. Which means that the LNA has great variablility in its settling time. The recombination rates change by about two orders of magnitude from measurements of a body contacted LNA device. This is causing product failures.

## What is the new solution?

Floating body and body-contacted devices are exactly the same, save for the presence of a body terminal. The reason we cannot use a body-contact LNA device in an LNA is due to linearity and noise issues (from shot noise in the body contact).

> [! Important]
> A body-contact device with it's body terminal floating, behaves like a floating body device.

Here is the main idea:

- During the switching event in a LNA from one gain state to another, keep the body-terminal at ground potential.
- After the settling time spec window (~1 $\mu$s), the body-terminal can be floated to mimic the performance of a floating body device.

This ensures that there is rapid charge removal from the body of the device during the switching event, enabling the device to settle quickly. After the switching event, the device should provide the performance of a floating-body device which is optimal for LNA use.

With this in place, there is no use to use special low-latency devices which have engineered traps in the device. Any regular floating body device will do, as long as it has an equivalent body-contacted device.

---
# References