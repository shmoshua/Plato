#Definition #FunctionalAnalysis 
> [!definition]
> Let $A$ be a commutative [[ring]]. The ***Jacobson radical*** of $A$ is the intersection of all maximal ideals, i.e.
> $$\text{Rad }A:= \bigcap_{M\in \text{Max } A}^{}M$$
> where $\text{Max}(A)$ denotes the set of all maximal regular ideals. If $\text{Max}(A)= \varnothing$, then $\text{Rad }A=A$.
- **Related definition**: $A$ is **semisimple** if $\text{Rad}(A)=(0)$. 
---
##### Properties
> [!lemma] Proposition 1
> Let $A$ be a commutative Banach algebra. Then, 
> 1. $\text{Rad}(A)=\bigcap_{\varphi\in \widehat{A}}^{}\text{ker }\varphi$
> 2. $A$ is semisimple if and only if for all $0\neq a\in A$, there exists $\varphi\in \widehat{A}$ s.t. $\varphi(a)\neq 0$.
> 3. $\text{Rad}(A)=\text{ker }\Delta$ where $\Delta:A\to C_{0}(\widehat{A}),x\mapsto \widehat{x}$ is the Guelfand transform.

> [!proof]-
> We have:
> 1. Follows from [[Guelfand Spectrum|Theorem 3]].
> 2. Obvious.
> 3. We have that: $$\text{ker }\Delta=\{ x\in A:\widehat{x}(\varphi)=0,\forall\varphi\in \widehat{A} \}=\bigcap_{\varphi\in \widehat{A}}^{}\{ x\in A :\varphi(x)=0\}=\bigcap_{\varphi\in \widehat{A}}^{}\text{ker }\varphi=\text{Rad}(A)$$
- **Corollary**: A $C^{*}$-algebra is always semisimple as $\text{Rad}(A)=\text{ker }\Delta=(0)$ by [[Guelfand Transform|Theorem 2]].
---
> [!lemma] Corollary 2
> Let $A,B$ be commutative [[Banach Algebra|Banach algebras]] with $B$ semi-simple. Then, 
> 1. every $\mathbb{C}$-algebra homomorphism $\varphi:A\to B$ is continuous.

> [!proof]-
> Let $x_{n}\to {0}$ in $A$ and assume $\varphi(x_{n})\to b\in B$. Let $\chi\in \hat{B}$, then $\chi \circ\varphi:A\to \mathbb{C}$ is a $\mathbb{C}$-algebra homomorphism so either $\chi \circ\varphi=0$ or $\chi \circ\varphi\in \hat{A}$. From [[Guelfand Spectrum|Proposition 2]], we know that $\chi \circ\varphi$ is continuous.
> 
> Then, $$\chi(b)=\lim_{ n \to \infty } \chi(\varphi(x_{n}))=\lim_{ n \to \infty } (\chi \circ \varphi)(x_{n})=(\chi \circ \varphi)(0)=0$$Therefore, $\chi(b)=0$ for all $\chi\in \hat{B}$ and $B$ is semi-simple, i.e. $\bigcap_{\chi\in \hat{B}}^{}\text{ker }\chi=(0)$ and $b=0$. Now, from the [[Bounded Linear Map|Closed graph theorem]], $\varphi$ is continuous.
- **Corollary**: Any $\mathbb{C}$-algebra homomorphism to a $C^{*}$-algebra is continuous.
---
##### Example
> [!h] Example 1
> There is no Banach algebra norm on $C^\infty([0,1])$. Assume $\|\cdot\|$ is such a norm and consider: $C^\infty([0,1])\hookrightarrow C([0,1])$. Then, 
> 1. $C([0,1])$ is semisimple.
> 2. The injection is continuous and there exists $c>0$ s.t. $\left\| f \right\|_{b}\leq c\left\| f \right\|$ for all $f\in C^\infty([0,1])$.
> Let $$\begin{array}{cccc} {D:}&{C^\infty([0,1])}&\to&{C^\infty([0,1])}\\&{f} &\mapsto & {f'} \end{array}{}$$
> 3. $D$ is continuous for $(C^\infty[0,1],\|\cdot\|)$. Let $f_{n}\to {0}$ and $f'_{n}\to g$. Then, $f_{n}\to {0}$ uniformly, $f_{n}' \to g$ uniformly. Therefore, $g=0$ as a derivative of $0$ and $D$ is continuous.
>    
> 4. However, $D$ cannot be bounded: consider $t\mapsto e^{\alpha t}$
---
> [!h] Example 2
> Let $\Gamma$ be a (countable) [[abelian group]] and $$\ell^!(\Gamma):=\left\{  f:\Gamma\to \mathbb{C} :\|f\|_{1}:=\sum_{\gamma\in \Gamma}^{}\left| f(\gamma) \right|<+\infty  \right\}$$
> 1. $\ell^1(\Gamma)$ is semisimple. (but why?)
---
