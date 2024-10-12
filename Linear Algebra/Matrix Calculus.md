#LinearAlgebra 

#### 1. Matrix Inversion

> [!lemma] Theorem (Woodbury Matrix Identity)
> We have for conformable matrices $A,C,U,V$, 
> 1. $(I+UV)^{-1}=I-UV(I+UV)^{-1}$
> 1. $(I+UV)^{-1}=I-U(I+VU)^{-1}V$
> 2. $(A+UCV)^{-1}=A^{-1}-A^{-1}U(C^{-1}+ VA^{-1}U)^{-1}VA^{-1}$

> [!proof]-
> We have that:
> 1. $(I-UV(I+UV)^{-1})(I+UV)=I+UV-UV=I$.
> 2. As $V(I+UV)=(I+VU)V$, we have that: $$(I+VU)^{-1}V=V(I+UV)^{-1}$$Hence, from 1, we have the formula.
> 3. By 2 with $A^{-1}U$ and $CV$, we have: $$\begin{align}(I+A^{-1} UCV)^{-1}&=I-A^{-1}U(I+CV A ^{-1}U)^{-1}CV\\(A+ UCV)^{-1}A&=I-A^{-1}U(C^{-1}+V A ^{-1}U)^{-1}V\\(A+ UCV)^{-1}&=A^{-1}-A^{-1}U(C^{-1}+V A ^{-1}U)^{-1}VA^{-1}\end{align}$$
---
