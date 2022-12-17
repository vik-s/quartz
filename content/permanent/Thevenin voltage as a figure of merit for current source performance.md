20221103-1850
Status: #permanent 
Tags: #ee/analog 

The open-circuit equivalent voltage given by the Thevenin equivalent representation is the figure of merit for a current source. The higher the open circuit voltage, the better. For the case of an ideal BJT current mirror, the thevenin voltage is the early voltage of the transistor. This makes sense because an infinite output resistance transistor would have infinite early voltage, and therefore results in the best current mirror performance.

If the output current of the current source is $I_0$ and the output resistance is $R_0$, then the thevenin voltage $V_{thev}$ is given by,

$$
V_{thev} = I_0 R_0
$$
When the output terminal of the current source is open circuited, an output voltage of $-V_{thev}$ will be observed. The thevenin representation is only valid for those regions of output voltage where the device operates in forward active region. Any higher voltages will cause the output transistor to go into saturation, and the simple thevenin representation is no longer valid.


---
# References

- [[permanent/Working principle of a Current Mirror]]