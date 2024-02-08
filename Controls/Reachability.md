#Definition #LST 

##### Linear Time-Varying Systems
> [!definition]
> For a linear time-varying system $$\dot{x}(t)=A(t)x(t)+B(t)u(t)$$ or equivalently, the pair $(A(\cdot),B(\cdot))$, a state $x_{1}\in \mathbb{R}^n$ is ***reachable on $[t_{0},t_{1}]$***, if there exists $u(\cdot)\in L^2([t_{0},t_{1}],\mathbb{R}^m)$ that steers $(0,t_{0})$ to $(x_{1},t_{1})$. 
> 
> The ***reachability map on $[t_{0},t_{1}]$*** of $(A(\cdot),B(\cdot))$ is the function: $$\begin{array}{cccc} {\mathcal{L}_{r}:}&{L^2([t_{0},t_{1}],\mathbb{R}^m)}&\to&{\mathbb{R}^n}\\&{u(\cdot ) } &\mapsto & {\int_{t_{0}}^{t_{1}} \Phi(t_{1},\tau)B(\tau)u(\tau) \, d\tau } \end{array}{}$$
---
##### Properties
> [!lemma] Lemma 1
> $\mathcal{L}_{r}$ is a bounded linear map. Further, the set of reachable states is $\text{Im}(\mathcal{L}_{r})$.

> [!proof]-
> It is obvious to see that $\mathcal{L}_{r}$ is linear and the set of reachable states is $\text{Im}(\mathcal{L}_{r})$. To show that $\mathcal{L}_{r}$ is bounded, $$\left\| \mathcal{L}_{r}(u) \right\| ^{2}=\left\| \int_{t_{0}}^{t_{1}} \Phi(t_{1},\tau)B(\tau)u(\tau) \, d\tau  \right\|^{2} \leq \int_{t_{0}}^{t_{1}} \left\| \Phi(t_{1},\tau)B(\tau) \right\| ^{2}\left\| u(\tau) \right\| ^{2} \, d\tau $$As $\Phi(t_{1},\cdot)B(\cdot)$ is piecewise continuous, there exists $M>0$ s.t. $\left\| \Phi_{1}(t_{1},\tau)B(\tau) \right\|\leq M$ for all $\tau\in[t_{0},t_{1}]$. Therefore, $$\left\| \mathcal{L}_{r}(u) \right\| ^{2}\leq \int_{t_{0}}^{t_{1}} \left\| \Phi(t_{1},\tau)B(\tau) \right\| ^{2}\left\| u(\tau) \right\| ^{2} \, d\tau\leq M^{2}\int_{t_{0}}^{t_{1}} \left\| u(\tau) \right\| ^{2} \, d\tau=M^{2}\|u\|^2_{2}   $$This shows that $\mathcal{L}_{r}$ is bounded.
---