---
title: MoM vs FEM for RFIC design
tags:
  - atomic
style: XvsY
written: ✅
published: ✅
---
Method of Moments vs Finite Element Method for RFIC design. When to use what? And why?

Method of Moments 
🔹 Calculates solution by computing currents on metal interconnects. No dielectrics need to be evaluated resulting in an efficient mesh for metals involving rectangles, triangles and quadrilateral elements. This makes it computationally efficient.
🔹 Limitation is that you can only accurately simulate "quasi-planar" structures, or structures that can be represented as multiple layers connected together
🔹 There should be no significant current distributions in the 3rd dimension
🔹 Since most RF designs on integrated circuits and PCBs tend to be planar, Method of Moments is usually sufficient to get a good EM solution quickly

FEM
🔹 FEM is a true 3-dimensional simulation method that places no restrictions on the geometries being simulated where electric and magnetic fields are the core unknowns
🔹 A "box" defines the simulation boundary and everything inside that box (conductors, semiconductors, dielectrics) are fully discretized using tetrahedral elements. Computational complexity can be high.
🔹 When wirebond packaging or full connector transitions need to be simulated, FEM simulations are needed to capture the fields properly. 
🔹 Even for quasi-planar structures, FEM solutions being general in nature can give excellent results, leading many people in industry to consider it the gold standard in Electromagnetics.

My upcoming (in 2024) newsletter: https://www.viksnewsletter.com
Follow me (🔔) for posts on EE, career, and growth.

