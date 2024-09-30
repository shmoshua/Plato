#Definition #Algorithms 

> [!definition]
> For a given cost metric $c$ and an optimal solution $\text{OPT}$ and a parameter $\varepsilon$, a ***polynomial randomized approximation scheme (PRAS)*** for a minimization problem is a Monte Carlo algorithm $\mathcal{A}_{\varepsilon}$ s.t. for all input instance $I$, 
> 1. $P(\left| c(\mathcal{A}_{\varepsilon}(I))-c(\text{OPT}(I)) \right|\geq \varepsilon \cdot c(\text{OPT}(I)))\leq \frac{1}{3}$
> 2. $\mathcal{A}_{\varepsilon}$ runs in $\text{poly}(\left| I \right|)$ time.
---
##### Properties
> [!lemma] Proposition 1
> Let $\mathcal{A}_{\varepsilon}$ be a PRAS. Let $X:= c(\mathcal{A}_{\varepsilon}(I))$ be the random variable of the output and $x_{1},\dots,x_{k}$ be $k$ instances of $X$. Then, 
> 1. for the median $x_{\text{med}}$ of $x_{1},\dots,x_{k}$, $$P(x_{\text{med}}>(1+\varepsilon)\cdot c( \text{OPT}(I) ))<e^{-k / 36}$$

> [!proof]-
> We have that: $$\begin{align}P(x_{\text{med}}>(1+\varepsilon)\cdot c( \text{OPT}(I) ))&\leq P(\text{Bin}(k,1 / 3 )\geq k / 2)\leq e^{-(\delta^{2})k/9}=e^{-k / 36}\end{align}$$
---
##### Examples
> [!h] Example 1 (Sampling)
> Let $S$ be a set and $U\subseteq S$. We aim to find $f_{\text{OPT}}:=\left| U \right| / \left| S \right|$. 
> 1. We need $\Theta\left( \frac{1}{f_{\text{OPT}}}\cdot \frac{\log(1/\delta)}{\varepsilon^{2}} \right)$ samples to ensure that $P(\left| \mathcal{A}_{\varepsilon}-f_{\text{OPT}} \right|>\varepsilon f_{\text{OPT}})\leq\delta$.