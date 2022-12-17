20221103-0532
Status: #permanent 
Tags: #ee/analog 

![[images/bjt-current-source-modified-for-lowgain-bjt.jpeg|400]]

When the gain $\beta_f$ of transistors Q1 and Q2 is low, then a modification to the current source is made as shown.  The addition of transistor Q3 mitigates the low gain of the transistors and the output current is no longer sensitive to the gain of the transistors, and is given by

$$
I_{c2} = \frac{I_{ref}}{1+\frac{2}{\beta_f^2 + \beta_f}}
$$
which is obtained by summing the currents at the emitter of Q3 and the collector of Q1.

---
# References

- [[permanent/Working principle of a Current Mirror]]
- [[literature/B-Meyer-1976-Ch4]]
