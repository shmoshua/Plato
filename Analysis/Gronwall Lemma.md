#Definition #Theorem #Analysis 

> [!lemma]
> For piecewise continuous functions $u,k:\mathbb{R} \to \mathbb{R}_{+}$ and $c_{1}\geq 0$ and $t_{0}\in \mathbb{R}$. If for all $t\in \mathbb{R}$: $$u(t)\leq c_{1}+\left| \int_{t_{0}}^{t} k(\tau)u(\tau) \, d\tau  \right| $$then for all $t\in \mathbb{R}$:
> $$u(t)\leq c_{1}\exp \left| \int_{t_{0}}^{t} k(\tau) \, d\tau  \right| $$
---
##### Proof
Consider $t>t_{0}$ as the proof is analogous for $t_{0}<t$ (except for the absolute values). Let $$U(t):=c_{1}+\int_{t_{0}}^{t} k(\tau)u(\tau) \, d\tau $$Then, $u(t)\leq U(t)$ for all $t\in \mathbb{R}$. Therefore, for $t>t_{0}$, $$\begin{align} u(t)&\leq U(t)\\u(t)k(t)\exp \left(- \int_{t_{0}}^{t} k(\tau) \, d\tau \right) &\leq U(t)k(t)\exp \left(- \int_{t_{0}}^{t} k(\tau) \, d\tau \right)\\ \left( \frac{d}{dt} U(t) \right)\exp \left(- \int_{t_{0}}^{t} k(\tau) \, d\tau \right) &\leq- U(t) \left( \frac{d}{dt}\exp \left(- \int_{t_{0}}^{t} k(\tau) \, d\tau \right) \right) \\ \frac{d}{dt}\left( U(t)\exp\left(  -\int_{t_{0}}^{t} k(\tau) \, d\tau \right) \right) &\leq 0\\ U(t)\exp\left(  -\int_{t_{0}}^{t} k(\tau) \, d\tau \right)&\leq U(t_{0})\exp\left(  -\int_{t_{0}}^{t_{0}} k(\tau) \, d\tau \right)=U(t_{0})=c_{1}\\ U(t)&\leq c_{1} \exp \int_{t_{0}}^{t} k(\tau) \, d\tau 
\end{align}$$
Therefore, $u(t)\leq c_{1}\exp \int_{t_{0}}^{t} k(\tau) \, d\tau$ for all $t>t_{0}$.

---
