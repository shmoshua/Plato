#Definition #Topology #Algebra 

> [!definition]
> Let $\mathbb{R}^d$ be a real Euclidean space and $2\leq r\leq d$. For a real algebraic set: $$V:=\{ (x_{1:d})\in \mathbb{R}^d : x_{1:r}=0 \}$$
> 1. The ***blow-up*** of $\mathbb{R}^d$ with center $V$ is defined as: $$B_{V}(\mathbb{R}^d):=\overline{\{ (x,(x_{1}:\dots:x_{r}))\in \mathbb{R}^d \times \mathbb{R}\mathbb{P}^{r-1} : x\in \mathbb{R}^d \backslash V\}}$$
- **Related definition**: The projection $\pi:B_{V}(\mathbb{R}^d)\to \mathbb{R}^d,(x,y)\mapsto x$ is the canonical projection.
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. $\pi : \{ (x,(x_{1}:\dots:x_{r}))\in \mathbb{R}^d \times \mathbb{R}\mathbb{P}^{r-1} : x\in \mathbb{R}^d \backslash V\}\to \mathbb{R}^d \backslash V$ is bijective.
> 2. $\pi ^{-1}(V)=\mathbb{R}\mathbb{P}^{r-1}$.

> [!proof]+
> We have that:
> 1. Surjectivity is clear by definition. If $\pi((x,(x_{1}:\dots:x_{r})))=\pi((y,(y_{1}:\dots:y_{r})))$, then $x=y$. Hence, it is injective.
> 2. Let $v=(0,\dots,0,v_{r+1},\dots,v_{d})\in V$ and let $p=(a_{1}:\dots:a_{r})\in \mathbb{R}\mathbb{P}^{r-1}$. Then, define: $x^{(n)}:=\left( \frac{a_{1}}{n},\dots, \frac{a_{r}}{n},v_{r+1},\dots,v_{d} \right)$. Then, $$(x^{(n)},p)\xrightarrow{n\to\infty}(v,p)$$Hence, $(v,p)\in B_{V}(\mathbb{R}^d)$ and we have the s