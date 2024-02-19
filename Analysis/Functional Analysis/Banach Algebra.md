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
---
> [!lemma] Proposition 2
> Let $A$ be a [[C-Algebra|unital algebra]] with a norm $\|\cdot\|$ s.t.
> 1. $(A,\|\cdot\|)$ is a [[Banach space]] and
> 2. $A\times A \to A, (x,y)\mapsto xy$ is continuous in each variable. 
> 
> Then, there exists an [[Equivalence of Norms|equivalent norm]] $\|\cdot\|_{\text{new}}$ on $A$ that makes it a Banach algebra.
----
##### Examples
3 Families of Banach Algebras
1. Function space with multiplication
2. Space of bounded operators
3. Group algebras with convolution.
---
> [!lemma] Example 1
> Let $-\infty<a<b<+\infty$. Then, for $n<+\infty$, 
> 1. $C^n([a,b])$ with pointwise multiplication is a Banach algebra with $\left\| f \right\|:=\sum_{k=0}^{n} \frac{1}{k!}\left\| f^{(k)} \right\|_{b}$
> 2. $C^n([a,b])$ is not a [[C*-algebra]].
> 3. $C^\infty([a,b])$ with pointwise multiplication does not admit any Banach algebra norm.

> [!proof]+ 
> We have: 
> 1. **Showing $C^n([a,b])$ is a Banach algebra**
> 	$$\begin{align}\left\| fg \right\| &=\sum_{k=0}^{n} \frac{1}{k!}\left\| (fg)^{(k)} \right\|_{b} \\&=\sum_{k=0}^{n} \frac{1}{k!}\left\| \sum_{i=0}^{k} {k\choose i} f^{(k-i)}g^{(i)}\right\|_{b}\\&\leq\sum_{k=0}^{n} \sum_{i=0}^{k} \frac{1}{i!(k-i)!}\left\|f^{(k-i)}\right\|_{b}\left\|g^{(i)}\right\|_{b} \\&=\end{align}$$

---
> [!lemma] Example 2
> For a [[Banach space]] $(B,\|\cdot\|)$, 
> 1. $\mathcal{B}(B)$ is a Banach algebra.
> 2. If $B=\mathcal{H}$, then $\mathcal{B}(\mathcal{H})$ is a [[C*-Algebra]] with the adjoint.

> [!proof]-
> We have: 
> 1. $\left\| TS \right\|\leq \left\| T \right\|\left\| S \right\|$
> 2. We have: $$\left\| Tx \right\| ^{2}=\braket{ Tx , Tx } =\braket{ x , T^{*}Tx } \leq \left\| T^{*}T x\right\| \|x\|$$Therefore, $\left\| T \right\|^{2}\leq \left\| T^{*}T \right\|$. The other direction holds from the Banach algebra property.
