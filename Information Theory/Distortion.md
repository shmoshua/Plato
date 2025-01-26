#Definition #InformationTheory 

> [!definition]
> Let $\mathcal{X},\mathcal{Y}$ be a finite set and $p\in \Delta(\mathcal{X})$. 
> 1. A ***distortion*** is a map $d:\mathcal{X}\times \mathcal{Y}\to \mathbb{R}_{\geq 0}$.

- **Remark**: A distortion $d:\mathcal{X}\times \mathcal{Y}\to \mathbb{R}_{\geq 0}$ can be extended to $$d:\mathcal{X}^n\times \mathcal{Y}^n\to \mathbb{R}_{\geq 0}, \quad (x,y)\mapsto \frac{1}{n}\sum_{i=1}^{n}d(x_{i},y_{i})$$
- **Related definition**: A ***description of rate $R$*** is $(f_{n},\phi_{n})_{n}$ where $f_{n}:\mathcal{X}^n\to [2^{nR}]$ and $\phi_{n}:[2^{nR}]\to \mathcal{Y}^n$.
	1. For $R\geq 0$ and $D\geq 0$, $(R,D)$ is ***achievable*** if for all $\delta>0$, there exists $n$ large enough and a description $(f_{n},\phi_{n})$ of rate $R$ s.t. $$\mathbb{E}[d(X,\phi_{n}(f_{n}(X)))]\leq D+\delta$$
- **Related definition**: We have that:
	1. $R(D):=\inf_{R}\{ R\geq 0 :(R,D)\text{ is achievable} \}$.
	2. $D(R):=\inf_{D}\{ D\geq 0 :(R,D)\text{ is achievable} \}$.
---
##### Properties
> [!lemma] Theorem 1 (Shannon)
> For $\mathcal{X},\mathcal{Y}$ finite,  
> 1. $R(D)=\min_{p}$
> 