#Definition #InformationTheory 

> [!definition]
> Let $\mathcal{X}$ be a finite set and $p\in \Delta(\mathcal{X})$. For $\xi\in \mathcal{X}^n$, 
> 1. $\xi$ is ***of type*** $p$ if $p=\frac{1}{n}\sum_{i=1}^{n}\delta_{\xi_{i}}$.
> 2. $\xi$ is ***$\varepsilon$-strongly typical*** w.r.t. $p$ for $\varepsilon>0$ if: $$\left| \frac{1}{n}\sum_{i=1}^{n}\delta_{\xi_{i}}-p \right| \leq \varepsilon \cdot p$$
> 	The set of $\varepsilon$-strongly typical $n$-length sequences is denoted as $T^{(n)}_{\varepsilon}(p)\subseteq \mathcal{X}^n$.
> 3. $\xi$ is ***$\varepsilon$-weakly typical*** w.r.t. $p$ for $\varepsilon>0$ if: $$2^{-n(H(p)+\varepsilon)}\leq \prod_{i=1}^{n}p(\xi_{i})\leq 2^{-n(H(p)-\varepsilon)}$$