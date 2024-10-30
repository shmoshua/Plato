#Definition #InformationTheory 

> [!definition]
> Let $\mathcal{X}$ and $\mathcal{Y}$ be finite sets. For $X\sim \mathcal{X}$ and $Y\sim \mathcal{Y}$, a ***discrete time channel (DMC)*** from $\mathcal{X}$ to $\mathcal{Y}$ is 
---
##### Properties
> [!lemma] Theorem 1 (Data Processing Inequality for Relative Entropy)
> We have that:
> $$D(p\|q)$$
> 

---
##### Examples
> [!h] Example 1 (Binary Symmetric Channel)
> The ***binary symmetric channel*** for $\varepsilon$ is given as: $$P_{Y_{1:n}|X_{1:n}}(y_{1:n}|x_{1:n})=\prod_{i=1}^{n}P_{Y|X}(y_{i}|x_{i})$$where $y_{i}:=x_{i}\oplus n_{i}$ given by $n_{i} \sim \text{Ber}(\varepsilon)$.