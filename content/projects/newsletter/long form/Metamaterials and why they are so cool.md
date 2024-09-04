---
title: Metamaterials and why they are so cool
tags: 
project: substack
date_published: 
status: 🚧
final title:
---
Metamaterials are artificially engineered structures that allow wave propagation in ways that do not occur in nature. For a propagating electromagnetic wave to seemingly defy the laws of nature has far reaching and fantastic consequences - invisibility cloaks, stealth aircraft, perfect lenses, doppler reversal and a whole lot more we are still learning.

In this article, we will ... what.
- thing1
- thing2
- thing3

Read time: X mins

~~

### To Ether or Not?

Before we dive into metamaterials, we need to set the historical stage regarding the nature of wave propagation in homogenous media. Put simply, it's story time.

Scientists in the 19th century believed that there should be an invisible "elastic, compressible, non gravitational solid" called luminiferous (means light-bearing) ether that is ubiquitous in our universe through which an electromagnetic wave can propagate. The idea of an invisible medium makes common sense if you think of a rock thrown into still water. You see waves propagating outwards from the point of disturbance. Even sound waves travel through air vibrations. A good part of the century was spent on studying "ether mechanics" and the most prominent proponent of the idea was William Thomson/Lord Kelvin who dedicated his entire life to the properties of ether, [and wrote](https://online.ucpress.edu/hsns/article-abstract/doi/10.2307/27757305/47770/In-Defense-of-Ether-The-British-Response-to?redirectedFrom=fulltext):

> Ether of Space has been my life study. ... I always meant some day to write a scientific treatise about the Ether of Space; but when in my old age I came to write this book, I found that the Ether pervaded all my ideas, both of this world and the next. I could no longer keep my treatise within the proposed scientific confines; it escaped in every direction and now I find has grown into a comprehensive statement of my philosophy."

To detect the presence of ether, in 1887, two scientists named Albert Michelson and Edward Morley devised an experiment. They built a device that split a beam of light in two, bounced off a mirror and arrived at a detector. If ether existed, then the speed of light would change depending on whether the light was moving in the direction of earth's motion or at right angles to it. They expected to see the beams of light arrive at different times at the detector. To their dismay, the beams of light arrived at exactly the same time proving that ether did not exist.

In 1905, the [annus mirabilis](https://en.wikipedia.org/wiki/Annus_mirabilis_papers) "miracle year", in the paper titled "[On the Electrodynamics of Moving Bodies](https://archive.org/details/einstein-1905-relativity/page/n3/mode/2up)", Albert Einstein wrote:

> The introduction of a “luminiferous ether” will prove to be superfluous inasmuch as the view here to be developed will not require an “absolutely stationary space” provided with special properties...

thereby effectively dispelling the need for ether to describe the propagation of electromagnetic waves. If you thought the whole world immediately went, "Wow! How come I didn't think of that!", you'd be wrong. Einstein's work on relativity largely went unnoticed except in Germany. The widely accepted concept of ether was simply the status quo and most physicists ridiculed Einstein's theory as impractical and absurd.

Einstein himself went back to the concept of ether in 1920 in an attempt to integrate gravity into special relativity. Without the concept of ether, he found gravity's "action-at-a-distance" mechanically inconsistent. In 1693, Newton himself foresaw the need for a "medium" in which gravity can act, and that the ability of gravity to simply cause mechanical movement through vacuum is absurd. He [wrote](https://www.jstor.org/stable/27900530):

> That gravity should be innate, inherent, and essential to matter, so that one body may act upon another at a distance through a vacuum, without the mediation of anything else, and by and through which their action and force may be conveyed from one to another, is to me so great an absurdity that I believe no man who has in philosophical matters a competent faculty of thinking can ever fall into it.

Today's widely accepted view is that ether does not exist, the propagation of electromagnetic waves can occur in free space, and that gravity does indeed occur at a distance. While wave can propagate in a material medium, it is not required to be present for waves to travel.

In spite of this understanding, we "confusingly" assign **constitutive parameters** such as permittivity and permeability to free space. If there is no material present, how is that we can assign material parameters to it? As it turns out, vacuum gets polarized due to fleeting formations of electron-positron pairs, and according to quantum field theory, [assigning permittivity to a vacuum](https://link.springer.com/article/10.1007/s10701-020-00339-3) is actually a reasonable thing to do.
### Properties of a homogenous medium

Let us understand a bit more about what permittivity and permeability actually mean. They are *macroscopic properties* of a material, which means that the fundamental units (atom, molecule, or something artificial) are spaced much closer than the wavelength of the wave propagating through it.

**Permittivity** describes the response of the medium to an external **electric field**. When an electric field is applied, the ease with which these dipoles line up with the field is a measure of its permittivity and is commonly denoted by the greek letter ε (epsilon) whose value in vacuum is ε0=8.854 x 10^-12 Farad/meter. The permittivity of a material is usually expressed as a multiple of ε0 represented by εr, or relative permittivity. For example, glass has a relative permittivity of about 4, or four times that of free space.

**Permeability** describes the response of the medium to an external **magnetic field** and is a measure of how much magnetism is induced in a material. It is denoted by the greek letter μ (mu) and μ0 = 4π x 10^-7 Henry/meter in vacuum. The permeability of a material is also expressed as a multiple of that of free space by μr. For example, the permeability of carbon steel is about 100.

The product of the relative permittivity and permeability gives the square of the **refractive index** of the material.
*add equation for refractive index*

The figure below shows the possible space of values for permittivity and permeability.

*add picture of 4 quadrants*

- Positive values of permittivity and permeability encompasses most naturally occurring dielectric materials (upper right quadrant I)
- Plasma and doped semiconductors at certain frequencies exhibit negative permittivity and positive permeability (upper left quadrant III)
- Some ferrites especially at low frequencies show negative permeability but positive permeability (lower right quadrant IV)
- **No known naturally occurring materials exist** with both negative permittivity and permeability (lower left quadrant III)

### The Amazing Properties of Double Negative Materials

In 1968, [Victor Veselago](https://en.wikipedia.org/wiki/Victor_Veselago), a Soviet Russian physicist published [a theoretical analysis](https://iopscience.iop.org/article/10.1070/PU1968v010n04ABEH003699) of the properties of these "unnatural" materials with both negative permittivity and permeability, called double negative materials in more recent literature.

Since the refractive index remains unaffected whether ε and μ are simultaneously positive or negative, Veselago interprets it in three ways:
1. Nothing really happens when the signs of ε and μ are reversed.
2. There is some fundamental law that is violated when ε and μ are negative, which is why they don't naturally occur.
3. There are some interesting properties of double negative materials that is worth looking at.

Luckily, he went with the third option.

#### Left-handed Materials

Veselago started by looking at cases where ε and μ occur separately - like in Maxwell's equations. Maxwell's equations when solved in regular materials with positive ε and μ establishes the direction of wave propagation according to the right hand rule.

Make mutual right angles with your thumb, index and middle finger. If the electric field is pointing in the direction of the thumb, magnetic field is pointing in the direction of the index finger, then the middle finger points in the direction of wave propagation.

*add picture of right and left handed rules in materials*

If both ε and μ are negative, then wave propagation in such materials follow the left hand rule, with each of the fingers representing the same quantities. Such materials, were they to exist, would be "left-handed" as opposed to naturally occurring "right-handed materials" and wave propagation would appear backwards compared to the normal case.

#### Reversal of Physical Phenomena

##### Doppler Effect

##### Vavilov-Cerenkov Effect

##### Snell's Law


#### Perfect/Super Lenses












