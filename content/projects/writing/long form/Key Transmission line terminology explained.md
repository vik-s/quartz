---
title: Key Transmission line terminology explained
tags:
  - passive
project: substack
date_published: 
status: 
final title:
---
Transmission lines are everywhere whether you realize or not.

They are used to transport electrical signals over long distances like those high voltage lines that transport electricity to your home. Or they can be designed to carry high frequency signals over microscopic distances like in an integrated circuit.

Either way, having some transmission line fundamentals under your belt will prove useful if you are an electrical engineer. After reading this, you will be able to answer the following regarding Transmission Lines:

1. What is it and what are the different kinds?
2. What are some key parameters and what do they mean?
3. How is it represented in a smith chart?
4. What are some simple applications in a microwave circuit?

Let's dive in!

--
### Transmission line fundamentals

A transmission line is defined as:

> [!definiton]
Two or more conducting wires that carry an alternating electrical signal and are physically much larger than the wavelength of the signal.

The relative physical size compared to wavelength (also called electrical size) is what prevents us from describing transmission lines with a simple circuit network. Due to electrical size, we need to represent transmission lines with a *distributed network* on a "per-unit-length" basis. 

We can associate a resistance, inductance, capacitance and conductance per-unit-length (R, L, G, C) for this transmission line. Now take a long transmission line and zoom in on a tiny slice of length \Deltaz of it and it's equivalent circuit representation is shown in Figure X. We will need this circuit in the next section to define some key parameters.

Before we get into it, here are some kinds of transmission lines you should know about (add a pic showing each and list out their key parameter calculations as cheat sheet):

1. Coaxial - It has a center core conductor and a metallic shield separated by insulator. It is widely used in CATV distribution, internet access and radio communication equipment.
2. Microstrip - A planar structure that has a signal line over a single ground plane separated by a substrate dielectric.
3. Stripline - A planar structure whose signal line is surround by ground planes on *both* top and bottom, separated by substrate dielectrics.
4. Coplanar waveguide - A planar structure whose signal line is surrounded by ground planes on either side of it, *at the same level*. Optionally, there can be a third ground plane below separated by a substrate dielectric.

### Key parameters defined

When you are dealing with transmission lines, you will need the terminology explained in this section to speak the language. My goal is to give you a short explanation of each key parameter of a transmission line with minimal math.

All of these parameters can be derived by solving Kirchoff's current and voltage equations for the circuit shown in figure X. The resulting equations are called **Telegrapher Equations** and I will just specify what it is below, since it is so fundamental to transmission lines.

$$
\frac{dV(z)}{dz} = -(R+j\omega L)I(z)
$$
$$
\frac{dI(z)}{dz} = -(G+j\omega C)V(z)
$$
If the $RLGC$ parameters are known for the transmission line being used through analytical calculations based on their physical structure, then several key properties can be calculated.
#### Characteristic Impedance

Let's say you are holding one end of a transmission line which is infinitely long. You use a special meter (because a Radioshack (RIP) ohmmeter just won't do) to measure the impedance of the end of the line you are holding. The reading you see is called the Characteristic Impedance, represented by $Z_0$ and the value depends on the physical construction of the transmission line. This is what makes it a fundamental property for any given type of transmission line.

To keep it simple, assume that the line has no losses so that $R=G=0$. The formula to calculate characteristic impedance is:

$$
Z_0 = \sqrt\frac{L}{C}
$$
This simple formula gives us an intuitive way to understand how to design the characteristic impedance of the transmission line. 

- Higher inductance per unit length, higher the $Z_0$
	- On a planar transmission line, make the signal line thinner, you will increase $L$ and $Z_0$
- Higher capacitance per unit length, lower the $Z_0$
	- On a planar transmission line, move the ground closer to the signal, you will increase $C$ and lower $Z_0$.

If there are losses in the line, it does affect the characteristic impedance, but more importantly the signal will attenuate as it travels along the line due to dissipative losses.

#### Propagation constant

Its interesting that telegrapher equations mentioned above can be wrangled into a wave propagation equation which we won't get into here (calculus is scary). Traveling electromagnetic waves in any medium have a quantity called *propagation constant* that describes how the wave travels in any given direction. It describes how fast the wave is and how it's amplitude varies as it travels.

Fortunately for us, the propagation constant represented by $\gamma$ is easily calculated from $RLGC$ parameters as follows,

$$
\gamma = \alpha + j\beta = \sqrt{(R+j\omega L)(G+j\omega C)}
$$
A few things of note:

1. Propagation constant is a function of frequency since $\omega = 2\pi f$, where $f$ is the frequency.
2. Propagation constant is a complex quantity where $\alpha$ is called the attenuation constant and $\beta$ is called the phase constant.









### Smith chart representation

### Basic applications


