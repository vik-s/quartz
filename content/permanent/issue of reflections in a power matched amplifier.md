---
title: "issue of reflections in a power matched amplifier"
created: 2023-05-02 11:49
status: #permanent
tags: #ee/amplifiers
---

When using a [[permanent/Loadline match can deliver more output power|loadline match]] (or [[permanent/power match versus conjugate match|power match]] in an RF sense), there is a concern that the load impedance used to extract maximum output power from the power transistor will result in reflections or VSWR issues that will affect the operation of the transistor. This is not entirely true. The PA will operate correctly regardless of what load is connected to it, as long as it is presented the optimum impedance at its output.

The real issue is concerning the circuit block that the PA will connect into, in the RF system. That system component may not be designed to handle the PA output impedance, as its input impedance.

These practical problems are often circumvented by the use of circulators or isolators at the output of the PA.