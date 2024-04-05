---
title: Use of AI in Electromagnetic Design
tags:
  - excalidraw
project: substack
date_published: 
status: 🚧
final title:
---
## Use in Electromagnetics

Another time consuming aspect of RF design involves the creation of optimum passive structures using electromagnetic simulation. We often look at matching circuits in a classical sense - a series inductor with a shunt capacitor, for example to convert the impedances from source to load. But what if these predetermined metal shapes or matching topologies are not the optimal answer? 

As Prof. Kaushik Sengupta says in [a paper](https://ieeexplore.ieee.org/abstract/document/10136184/references#references) (IEEE paywall) published in the Journal of Solid State Circuits,

> In the space of all possible manufacturable EM structures, there is no reason to believe that these (and therefore, the co-designed circuits) will be close to being “globally” optimal.

Prof. Sengupta and his team show that you can use deep convolutional neural networks to synthesize an arbitrary metal shape that provides the appropriate transformation of impedances. In [this paper](https://www.researchgate.net/profile/Zheng-Liu-108/publication/360427205_Deep_Learning-Enabled_Inverse_Design_of_30-94_GHz_P_sat3_dB_SiGe_PA_Supporting_Concurrent_Multiband_Operation_at_Multi-Gbs/links/62758ee6973bbb29cc67bce5/Deep-Learning-Enabled-Inverse-Design-of-30-94-GHz-P-sat-3-dB-SiGe-PA-Supporting-Concurrent-Multiband-Operation-at-Multi-Gb-s.pdf), an arbitrary metal shape serves as the output matching network for a millimeter-wave PA, and works as intended.

The ultimate RF/analog dream would be to utilize generative AI to completely synthesize a design from just specifications to a fully working, optimal design whose performance is unmatched by human iteratively running design simulations. Maybe we will get there at some point.

## Use in device modeling

## Use in wireless communications


- Applications of ML and ANN in device modeling
- Learning to design circuits 
- Automating placement of circuits for floorplanning
- Automatic inductor model extraction with ANN
- Design of PA output matching network with inverse design

https://www.doe.carleton.ca/~qjz/announcement.html