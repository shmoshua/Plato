#Definition #Topology 

> [!definition]
> A [[topological space]] $X$ is ***contractible*** if $f_{0}:=\text{id}_{X}$ is [[Homotopy|homotopic]] to a constant map. 
---
##### Examples 
> [!h] Example 1 (Rn)
> $\mathbb{R}^n$ is contractible for $n\geq 0$. For $y\in \mathbb{R}^n$, we have the homotopy, $$\begin{array}{cccc} {h:}&{\mathbb{R}^n\times \mathbb{I}}&\to&{\mathbb{R}^n}\\&{(x,t)} &\mapsto & {(1-t)x+ty} \end{array}{}$$So is any non-empty star-shaped subset of $\mathbb{R}^n$. 
---
> [!h] Example 2
> $S^1$ is not contractible.

> [!proof]-
> Assume that $S^1$ is contractible and $h$ is a homotopy with $h(x,0)=x$ and $h(x,1)=x_{0}\in S^1$ for all $x\in S^1$. By composing it with a rotation, we may assume that $x_{0}=-1$. 
> 
> Then, the map: $$\begin{array}{cccc} {\varphi:}&{S^1 \backslash\{ -1 \}}&\to&{(-\pi,\pi)}\\&{z} &\mapsto & {\text{arg}(z)}\\&{e^{it}} &\gets & {t} \end{array}{}$$is a homeomorphism.
> 
> We claim that there exists a continuous function $\tilde{f_{0}}:S^1\to \mathbb{R}$ s.t. $\text{id}_{S^1}=\exp(i\tilde{f_{0}})$. Let $$\begin{array}{cccc} {f_{t}:}&{S^1}&\to&{S^1}\\&{x} &\mapsto & {h(x,t)} \end{array}{}$$As $S^1\times \mathbb{I}$ is compact, $h$ is uniformly continuous and for $\delta>0$ if $\left| s-t \right|<\delta$ then for all $x\in S^1$: $$\left| f_{t}(x)-f_{s}(x) \right| =\left| h(x,t)-h(x,s) \right| <\varepsilon$$In particular, there exists $k\geq 1$ s.t. for $\left| s-t \right|\leq \frac{1}{k}$, $\left| \frac{f_{t}(x)}{f_{s}(x)}-1 \right|<2$. Therefore, $f_{t} / f_{s}:S^1\to S^1 \backslash \{ -1 \}$.
> Now we show the claim via induction on $j$ for $0\leq j\leq k$. Assume $f_{j /k}$ has a lifting $\tilde{f}_{j/k}$ s.t. $f_{j / k}=\exp(i \tilde{f}_{j / k})$. Indeed, $$f_{(j-1) / k}= f_{j / k}\cdot  \frac{f_{(j-1) /k}}{f_{j /k}}=\exp(i\tilde{f}_{j /k})\cdot \left( \varphi ^{-1} \circ \varphi\circ  \frac{f_{(j-1) /k}}{f_{j /k}} \right)=\exp(i\tilde{f}_{j /k})\cdot \exp\left(i\left( \varphi\circ  \frac{f_{(j-1) /k}}{f_{j /k}}  \right)\right)$$Therefore, $\tilde{f}_{(j-1) / k}=\tilde{f}_{j/k}+\varphi \circ\frac{f_{(j-1) /k}}{f_{j /k}}$ is continuous and from the induction $f_{0}$ also has such lifting. 
> 
> Then, define: $$g(z):=\frac{ \tilde{f_{0}}(z)-\tilde{f_{0}}(-z)}{\left| \tilde{f_{0}}(z)-\tilde{f_{0}}(-z) \right| }$$where $\tilde{f_{0}}(z)-\tilde{f_{0}}(-z)\neq 0$ as $\tilde{f_{0}}$ is injective. Then, $g:S^1\to \{ \pm 1 \}$ is surjective and continuous, but $S^1$ is connected, which is a contradiction.
---
> [!h] Example 3
> $L^2([0,1]) \backslash \{ 0 \}$ is contractible. 