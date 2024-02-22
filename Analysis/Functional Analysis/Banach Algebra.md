#Definition #FunctionalAnalysis 

> [!definition] 
> A ***Banach algebra*** is a [[C-Algebra|$\mathbb{C}$-algebra]] $B$ endowed with a norm $\|\cdot\|$ s.t. 
> 1. $(B,\|\cdot\|)$ is a [[Banach space]] and
> 2. $\left\| xy \right\|\leq\|x\|\|y\|$ for all $x,y\in B$
---
##### Properties
> [!lemma] Proposition 1 
> Let $B$ be a non-unital Banach algebra. Then, 
> 1. $B_{I}:=B\times \mathbb{C}$ per [[C-Algebra|this construction]] with $\left\| (x,\lambda) \right\|=\|x\|+\left| \lambda \right|$ is a unital Banach algebra. 
> 2. The map: $$\begin{array}{cccc} &{B}&\to&{B_{I}}\\&{x} &\mapsto & {(x,0)} \end{array}{}$$is isometric.

> [!proof]-
> $B_{I}$ is a $\mathbb{C}$-algebra from [[C-Algebra|Proposition 1]]. Then, $B_{I}$ is Banach with the norm given and: $$\begin{align}\left\| (x,\lambda)(y,\mu) \right\|&=\left\| (xy+x\mu+\lambda y,\lambda \mu) \right\| \\&=\left\| xy+x\mu+\lambda y \right\| +\left| \lambda \mu \right| \\&\leq \left\| xy \right\| +\left| \mu \right| \|x\|+\left| \lambda \right| \|y\|+\left| \lambda \right|\left| \mu \right| \\&\leq \|x\| \|y\| +\left| \mu \right| \|x\|+\left| \lambda \right| \|y\|+\left| \lambda \right|\left| \mu \right|  \\&=\|(x,\lambda)\|\cdot \|(y,\lambda)\|\end{align} $$
> Further, $\left\| (x,0) \right\|=\|x\|$. Therefore, it is an isometric homomorphism.
---
> [!lemma] Proposition 2
> Let $A$ be a [[C-Algebra|unital algebra]] with a norm $\|\cdot\|$ s.t.
> 1. $(A,\|\cdot\|)$ is a [[Banach space]] and
> 2. $A\times A \to A, (x,y)\mapsto xy$ is continuous in each variable. 
> 
> Then, there exists an [[Equivalence of Norms|equivalent norm]] $\|\cdot\|_{\text{new}}$ on $A$ that makes it a Banach algebra.

> [!proof]-
> For any $x\in A$, consider $M_{x}:A\to A,y\mapsto xy$. Then, $M_{x}\in \mathcal{B}(A)$ and: $$\left\| xy \right\| \leq \left\| M_{x} \right\| \left\| y \right\| $$ for all $x,y\in A$. Now consider, $$\begin{array}{cccc} {T:}&{A}&\to&{\mathcal{B}(A)}\\&{x} &\mapsto & {M_{x}} \end{array}{}$$Then, for $(x,M)\in \overline{\text{graph}(T)}$, there exists $(x_{n})_{n} \subseteq A$ s.t. $x_{n}\to x$ and $M_{x_{n}}\to M$. Therefore, for all $y\in A$: $x_{n}y\to M(y)$. However, as $x\mapsto xy$ is continuous for all $y\in A$, $x_{n}y\to xy$. It follows that $M(y)=xy$ for all $y\in A$ and $(x,M=M_{x})\in \text{graph}(T)$, i.e. the graph is closed.
> 
> By the [[Bounded Linear Map|Closed graph theorem]], $T$ is bounded and, there exists $K>0$ s.t. $$\left\| xy \right\| \leq \left\| M_{x} \right\| \left\| y \right\| \leq K\|x\|\|y\|$$Now, let $\|x\|_{\text{new}}=K\|x\|$. Then, $$\left\| xy \right\| _{\text{new}}=K\left\| xy \right\| \leq K^{2}\|x\|\|y\|=\|x\|_{\text{new}}\|y\|_{\text{new}}$$and $(A,\|\cdot\|_{\text{new}})$ is Banach as the norms are equivalent. 
----
##### Examples
**3 Families of Banach Algebras**
1. Function space with multiplication
2. Space of bounded operators
3. Group algebras with convolution.
---
> [!h] Example 1
> Let $-\infty<a<b<+\infty$. Then, for $n<+\infty$, 
> 1. $C^n([a,b])$ with pointwise multiplication is a Banach algebra with $\left\| f \right\|:=\sum_{k=0}^{n} \frac{1}{k!}\left\| f^{(k)} \right\|_{b}$
> 2. $C^n([a,b])$ is not a [[C*-algebra]] with $f\mapsto \overline{f}$
> 3. $C^\infty([a,b])$ with pointwise multiplication does not admit any Banach algebra norm.

> [!proof]-
> We have: 
> 1. **Showing $C^n([a,b])$ is a Banach algebra**:
> 	$$\begin{align}\left\| fg \right\| &=\sum_{k=0}^{n} \frac{1}{k!}\left\| (fg)^{(k)} \right\|_{b} \\&=\sum_{k=0}^{n} \frac{1}{k!}\left\| \sum_{i=0}^{k} {k\choose i} f^{(k-i)}g^{(i)}\right\|_{b}\\&\leq\sum_{k=0}^{n} \sum_{i=0}^{k} \frac{1}{i!(k-i)!}\left\|f^{(k-i)}\right\|_{b}\left\|g^{(i)}\right\|_{b} \\&\leq \left( \sum_{k=0}^{n} \frac{1}{k!}\left\| f^{(k)} \right\| _{b} \right) \left( \sum_{k=0}^{n} \frac{1}{k!}\left\| g^{(k)} \right\| _{b} \right)\\&=\left\| f \right\| \cdot \left\| g \right\|  \end{align}$$
> 2. Obvious.
> 3. TODO
---
> [!h] Example 2
> For a [[Banach space]] $(B,\|\cdot\|)$, $\mathcal{B}(B)$ is a Banach algebra.

> [!proof]-
> $\mathcal{B}(B)$ is a Banach space from [[Bounded Linear Map|Proposition 1]] and $\left\| TS \right\|\leq \left\| T \right\|\left\| S \right\|$ from [[Linear Map|Theorem 4]].
---