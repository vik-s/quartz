---
title: "Operation and Modeling of the MOS Transistor"
author: Yannis Tsividis
year: 1987
status: 
- #literature/book 
- #inbox/to-process 
tags: 
- #ee/device
---

![tsividis](https://m.media-amazon.com/images/I/41wL-KP1sNL._SX218_BO1,204,203,200_QL40_ML2_.jpg)


## 1.2 Semiconductors

We will deal with silicon as semiconductor, and assume that it is in thermal equilibrium without any external influences.

### Properties of semiconductors

- A silicon crystal has a lattice of atoms held together in a three-dimensional structure called a [[crystal lattice]].
- Atoms are held together using a [[valence bond]] associated with the electron of the atom. In absolute zero, these electrons exactly counteract the positive charge in the electron's nucleus
- With thermal energy, the electron is knocked loose from the atom and becomes a [[free electron]] which can now freely move throught the lattice, and can cause electric current to flow
- The resulting positive charge is called a [[hole]] and can also move through the lattice by electrons from neighboring atoms filling the hole and becoming positive themselves.




## 1.5 The PN junction

### Without external bias

![[images/pn-junction-no-external-bias.png]]

- N-type and P-type semiconductors are brought together to make a PN junction. When the doping changes from one type to another abruptly it is called a *step* junction.
- There are metallic contacts on either extreme of materials where connection to the external world is made.
- Due to the concentration difference across the interface of these two regions:
	- Electrons will diffuse from the n-region to the p-region, leaving behing positivitly charged donor atoms
	- Holes will diffuse from the p-region to the n-region leaving behind negatively charged acceptor atoms
- An electric field builds up internal to the PN junction due to the ionized impurities in either region, and the direction of the field goes from the n- to p-region.
	- Any further holes diffusing from p- to n-type, will be repelled by this field
	- Any further electron diffucing from n- to p-type will be repelled by this field
- The potential difference across this region is called the ==built-in potential== of the junction, and is denoted by $\phi_{bi}$.
	$$\phi_{bi} = \phi_{Fp}-\phi_{Fn}$$
	where, $\phi_{Fp}$ and $\phi_{Fn}$ are the Fermi potentials of the p-side and n-side respectively.
- This will result in a region in each doped semiconductor which is devoid of any free charges. This is called the ==depletion region==.
* If n-type is more heavily doped (as shown in figure), then the depletion width $d_1$ in the n-type region is lesser than $d_2$ in the p-type region, because there are more carriers per unit area, which means more charge can be uncovered in relatively short depth. 
* If n-type is heavily doped so that $N_D >> N_A$,  then most of the potential is dropped across the p-type region, and $\phi_2 \approx \phi_{bi}$
* The depletion width $d_1$ will be very small and $d_2$ can be calculated as :
$$
d_2=\sqrt{\frac{2\epsilon_s}{qN_A}}\sqrt{\phi_{bi}}
$$
- The charge per unit area on the p-side is given by
$$
Q'_2=-\sqrt{2q\epsilon_sN_A}\sqrt{\phi_{bi}}
$$

### With forward bias

![[images/pn-junction-forward-bias.png]]

- If a positive voltage V is applied to the p-side, the junction is forward biased
- The external voltage will lower the builtin potential to $\phi_{bi}-V$
- The electrons supplied from the negative terminal of the battery will "cover" some of the charges in the depletion region on the n-side, and the holes supplied from the positive terminal of the battery will "cover" some charges in the depletion region on the p-side
- The overall depth of the depletion regions on each side will decrease
- Electrons and holes do not face as much as a potential barrier and will cross over from one side to the other in the pn junction resulting in the flow of current which is
$$
I = I_0(e^{V/\phi_t}- 1)
$$
where $I_0$ depends on the pn junction doping and geometry, and $\phi_t$ is the thermal voltage.

### With reverse bias
![[images/pn-junction-reverse-bias.png]]



---
# References