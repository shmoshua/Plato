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
> 2. $K_{\mathfrak{g}}$ is non-degenerate, i.e. $\text{rad}(K_{\mathfrak{g}}):=\{ v\in \mathfrak{g}:K_{\mathfrak{g}}(v,w)=0, \forall w\in \mathfrak{g} \}=(0)$ or $\mathfrak{g}^{\bot}=(0)$.

> [!proof]+
> We have:
> 1. (1=>2): Assume $\mathfrak{g}=\mathfrak{g}_{1}\oplus\dots \oplus \mathfrak{g}_{r}$ with $\mathfrak{g}_{i}$ simple. Then, for all $X=\sum_{i=1}^{r}X_{i}\in \mathfrak{g}$, $$\text{ad}_{\mathfrak{g}}(X)=\begin{bmatrix}\text{ad}_{\mathfrak{g}_{1}}(X_{1})&\\&\ddots\\&&\text{ad}_{\mathfrak{g}_{r}}(X_{r})\end{bmatrix}$$Therefore, $K_{\mathfrak{g}}(X,Y)=\text{tr}(\text{ad}_{\mathfrak{g}}(X)\text{ad}_{\mathfrak{g}}(Y))=\sum_{i=1}^{r}\text{tr}(\text{ad}_{\mathfrak{g}_{i}}(X_{i})\text{ad}_{\mathfrak{g}_{i}}(Y_{i}))=\sum_{i=1}^{r}K_{\mathfrak{g}_{i}}(X_{i},Y_{i})$.
>    
>    Let $X\in \mathfrak{g}^{\bot}$. Then, $X_{i}\in (\mathfrak{g}_{i})^{\bot}_{\mathfrak{g}_{i}}:=\{ X\in \mathfrak{g}_{i}:K_{\mathfrak{g}_{i}}(X,Y)=0,\forall Y\in \mathfrak{g}_{i} \}$. Then, by [[Ideal (Lie Algebra)|Example 1]], $(\mathfrak{g}_{i})^{\bot}_{\mathfrak{g}_{i}}\unlhd \mathfrak{g}_{i}$ and by simpleness, $(\mathfrak{g}_{i})^{\bot}_{\mathfrak{g}_{i}}=(0)$ or $(\mathfrak{g}_{i})^{\bot}_{\mathfrak{g}_{i}}=\mathfrak{g}_{i}$. If $(\mathfrak{g}_{i})^{\bot}_{\mathfrak{g}_{i}}=\mathfrak{g}_{i}$, then $K_{\mathfrak{g}_{i}}=0$ and by [[Killing Form|Cartan's criterion]], $\mathfrak{g}_{i}$ is solvable. Therefore, $\mathfrak{g}_{i}^{(1)}\neq \mathfrak{g}_{i}$ and as $\mathfrak{g}_{i}$ is simple, we have that $\mathfrak{g}_{i}^{(1)}=(0)$. Hence, $\mathfrak{g}_{i}$ is abelian, which is a contradiction. 
>    
>    This implies that $(\mathfrak{g}_{i})^{\bot}_{\mathfrak{g}_{i}}=(0)$ for all $i$, which means $\mathfrak{g}^{\bot}=(0)$ and $K_{\mathfrak{g}}$ is non-degenerate. 
> 2. (2=>1): Assume that $K_{\mathfrak{g}}$ is non-degenerate. Then, 
> 	- **Claim 1: $\mathfrak{g}$ has no non-zero abelian ideal**: 
> 	  Let $\mathfrak{a}\unlhd \mathfrak{g}$ be an abelian ideal and $\mathfrak{g}=W\oplus \mathfrak{a}$. Then, for all $X\in \mathfrak{a}$, $$\text{ad}(X)=\begin{bmatrix}0&0\\ *&0\end{bmatrix}$$and for all $Y\in \mathfrak{g}$, $$\text{ad}(Y)=\begin{bmatrix}*&0\\ *&*\end{bmatrix}$$Therefore, $K_{\mathfrak{g}}(X,Y)=0$. Hence, $\mathfrak{a}\subseteq \mathfrak{g}^{\bot}=(0)$.
> 	- **Claim 2: If $\mathfrak{h}\unlhd \mathfrak{g}$ then $\mathfrak{h}\cap \mathfrak{h}^{\bot}=(0)$**:
> 	  Since $K_{\mathfrak{g}}$ is non-degenerate, we have $[X,Y]=0$ for all $X,Y\in \mathfrak{h}\cap \mathfrak{h}^{\bot}$. Therefore, $\mathfrak{h}\cap \mathfrak{h}^{\bot}$ is an abelian ideal of $\mathfrak{g}$ and by Claim 1, $\mathfrak{h}\cap \mathfrak{h}^{\bot}=(0)$.
> 	
> 	Since $K_{\mathfrak{g}}$ is non-degenerate, $\text{dim }\mathfrak{h}^{\bot}=\text{dim }\mathfrak{g}-\text{dim }\mathfrak{h}$ and hence as a vector space, $$
