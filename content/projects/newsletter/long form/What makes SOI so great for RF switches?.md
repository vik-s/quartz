---
title: What makes SOI so great for RF switches?
tags:
  - technology
project: substack
date_published: 
status: 🚧
final title:
---
## What is Silicon on Insulator?

Before we discuss SOI, we need to understand the physical structure of a silicon transistor.  The starting material is a p-type silicon substrate, a semiconductor that has an impurity such as boron injected into it. Specific regions of this substrate are then heavily doped with impurities such as phosphorus or arsenic to make it an n-type material. These *implanted* n-type regions form the source and drain of the transistor. Metal connections are made to these regions to interface with the outside world. 

*Draw picture of a tarnsistor*

The space between the source and drain is called the *channel*.  Above this region, a layer of thin oxide is deposited called the *gate oxide*, and then a layer of polycrystalline silicon is deposited on top of the gate oxide to form the transistor gate terminal. By adjusting the voltage on the gate, the current flow between source and drain is controlled. Check out this video for a nice animated explanation of transistor operation.

https://youtu.be/rkbjHNEKcRw?si=BjOqYDPQe4mDu6Bo

In SOI, the source and drain regions are not implanted directly on the p-type substrate. Instead, a thin layer of silicon dioxide, several tenths of a micrometer thick, is deposited on top of the p-type substrate. Then, on top of that, deposit another thin layer of semiconducting p-type silicon where the source, drain and channel regions will be formed. The thickness of this silicon layer is important to transistor operation but we'll revisit that shortly.

*draw pictiure of soi transistor*

https://youtu.be/uvV7jcpQ7UY?si=ay_8HfvUzVKsEW_8

The fact that there is an insulating material between the transistor and the substrate has massive implications.

1. **Lower Parasitic Capacitance**: In a traditional bulk transistor, there is an unwanted capacitance between the source / drain and the bulk substrate. The presence of an insulating layer  between the transistor and the substrate greatly lowers this parasitic capacitance. This allows the design of high speed, high frequency circuits on this technology, and is a key feature that enables RF front end devices such as switches to be implemented in this technology. *Put picture of parasitic capacitance*
2. **Lower Leakage Currents**:  Due to the presence of an insulator, the leakage of currents through the bulk semiconductor is completed cut off enabling the design of low power circuits on SOI.
3. **No Latch up**: Latch-up is a phenomenon



- Physical structure of SOI transistor
- PDSOI and FDSOI
	- Floating body effect
	- FDSOI can give really good subthreshold slopes (close to the theoretical value of 60mV/dec)

## Where is SOI used?
- Memory and early CPU
- RF electronics
- Photonics

## A brief history of SOI
## What makes it good for RF?

- Lower parasitic capacitance
- Resistance to latchup
- No body or well taps needed
- Lower leakage currents
- Enhanced radiation hardness
- 

## References

- https://anysilicon.com/fdsoi/
- https://anysilicon.com/globalfoundries-unveils-12nm-fd-soi-process-node/
- https://finance.yahoo.com/news/stmicroelectronics-breaks-20nm-barrier-cost-110000772.html
- https://semiwiki.com/semiconductor-manufacturers/soitec/336744-fd-soi-the-technology-shaping-the-future-of-automotive-radars/
- 


