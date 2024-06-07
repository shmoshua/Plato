#Definition #LieGroups 

> [!definition]
> A $\mathbb{K}$-[[Lie algebra]] $\mathfrak{g}$ is ***semisimple*** if there are [[Simple Lie Algebra|simple]] [[Ideal (Lie Algebra)|ideals]] $\mathfrak{h}_{1},\dots,\mathfrak{h}_{r}\unlhd \mathfrak{g}$ s.t. 
> 1. $\mathfrak{g}=\mathfrak{h}_{1}\oplus\dots \oplus \mathfrak{h}_{r}$ and 
> 2. $\left[ \sum_{i=1}^{r}X_{i},\sum_{i=1}^{r}Y_{i} \right]_{\mathfrak{g}}=\sum_{i=1}^{r}[X_{i},Y_{i}]_{\mathfrak{h_{i}}}$
- **Related definition**: A connected [[Lie group]] is ***semisimple*** if $\mathfrak{g}$ is semisimple.
---
##### Properties
> [!lemma] Theorem 1
> For a Lie algebra $\mathfrak{g}$, the following are equivalent:
> 1. $\mathfrak{g}$ is semisimple.
> 2. $K_{\mathfrak{g}}$ is non-degenerate, i.e. $\text{rad}(K_{\mathfrak{g}}):=\{ v\in \mathfrak{g}:K_{\mathfrak{g}}(v,w)=0, \forall w\in \mathfrak{g} \}=(0)$

> [!proof]+
> 