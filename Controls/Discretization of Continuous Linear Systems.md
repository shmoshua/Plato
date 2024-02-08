#Example #LST 

##### [[Linear Time Varying System|Time-Varying Linear Systems]]
Consider the system: $$\begin{align}\dot{x}(t)&=A(t)x(t)+B(t)u(t)\\y(t)&=C(t)x(t)+D(t)u(t)\end{align}$$with initial condition $x(t_{0})=x_{0}\in \mathbb{R}^n$, $t\geq t_{0}$. Consider $\{ t_{k} \}_{{k\in \mathbb{N}}}$ s.t. $t_{k}<t_{k+1}$. Let:
- $u(t)=u_{k}$ for all $t\in [t_{k},t_{k+1})$ for all $k$.
- $\bar{x}_{k}=x(t_{k})$
- $\bar{y}_{k}=y(t_{k})$

Then, we can discretize the linear system as follows: 
$$\begin{align}\bar{x}_{k+1}&=x(t_{k+1})\\&=\Phi(t_{k+1},t_{0})x_{0}+\int_{t_{0}}^{t_{k+1}}\Phi(t_{k+1},\tau)B(\tau)u(\tau)  \, d\tau\\&=\Phi(t_{k+1},t_{k})\Phi(t_{k},t_{0})x_{0}+\Phi(t_{k+1},t_{k})\int_{t_{0}}^{t_{k+1}}\Phi(t_{k},\tau)B(\tau)u(\tau)  \, d\tau\\&=\underbrace{ \Phi(t_{k+1},t_{k}) }_{ =:\bar{A}_{k} }x(t_{k})+\underbrace{ \Phi(t_{k+1},t_{k})\int_{t_{k}}^{t_{k+1}}\Phi(t_{k},\tau)\bar{B}(\tau) \, d\tau  }_{ =:B_{k} }u_{k} \\&=\overline{A}_{k}\overline{x}_{k}+\overline{B}_{k}u_{k}  \end{align}$$
Similarly, $$\begin{align}\bar{y}_{k+1}=y(t_{k+1})&=C(t_{k+1})x(t_{k+1})+D(t_{k+1})u(t_{k+1})\\&=C(t_{k+1})(\overline{A}_{k}\overline{x}_{k}+\overline{B}_{k}u_{k})+D(t_{k+1})u(t_{k+1})\end{align}$$

---
##### [[Linear Time Invariant System|Time-Invariant Linear Systems]]
- $\overline{A}_{k}=\Phi(t_{k+1},t_{k})=\Phi(t_{k+1}-t_{k},0)=\Phi(T,0)$
- $\overline{B}_{k}=\Phi(T,0)\int_{t_{k}}^{t_{k+1}}\Phi(t_{k},\tau)B  \, d\tau$