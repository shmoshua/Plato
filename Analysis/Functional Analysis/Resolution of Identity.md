#Definition #FunctionalAnalysis 

> [!definition]
> Let $X$ be a [[locally compact Hausdorff space]], $\mathcal{B}_{X}$ the [[Borel Sigma-Algebra|Borel $\sigma$-algebra]]  and $\mathcal{H}$ a [[Hilbert space]]. A map $E:\mathcal{B}_{X}\to \mathcal{B}(\mathcal{H})$ is a ***resolution of identity*** if: 
> 1. $E(\varnothing)=0$, $E(X)=\text{id}_{\mathcal{H}}$.
> 2. $E(\omega)$ is a self-adjoint [[Hilbert Space Operator|projection]] for all $\omega\in \mathcal{B}_{X}$
> 3. $E(\omega_{1}\cap\omega_{2})=E(\omega_{1})E(\omega_{2})$ for all $\omega_{1},\omega_{2}\in \mathcal{B}_{X}$
> 4. $E(\omega_{1}\sqcup \omega_{2})=E(\omega_{1})+E(\omega_{2})$
> 5. for all $x,y\in \mathcal{H}$, the function: $$\begin{array}{cccc} {E_{x,y}:}&{\mathcal{B}_{X}}&\to&{\mathbb{C}}\\&{\omega} &\mapsto & {\braket{ E(\omega)x , y } } \end{array}{}$$is a regular [[complex measure]].

- **Remark**: In the applications, $X=$ [[Guelfand Spectrum|$\widehat{A}$]] where $A\subseteq \mathcal{B}(\mathcal{H})$ is an abelian sub-$C^{*}$-algebra.
- **Remark**: If $\omega_{1}\cap\omega_{2}=\varnothing$, then $\text{Im }E(\omega_{1}) {\ \bot\ }\text{Im } E(\omega_{2})$ (cf. [[Hilbert Space Operator|Proposition 3]])
- **Remark**: For any $x\in \mathcal{H}$, $E_{x,x}(\omega)=\braket{ E(\omega)x , x }=\left\| E(\omega)x \right\|^{2}$. Therefore, $0\leq E_{x,x}(\omega)\leq \|x\|^{2}$ and $E_{x,x}$ is a bounded positive measure.
---
##### Properties
> [!lemma] Proposition 1
> For every $x\in \mathcal{H}$, the map $\mathcal{B}_{X}\to \mathcal{H}:\omega\mapsto E(\omega)x$ is $\sigma$-additive, i.e. if $\omega=\bigsqcup_{n=1}^{\infty}\omega_{n}$ for $\omega_{n}\in \mathcal{B}_{X}$, then: $$E(\omega)x=\sum_{n=1}^{\infty}E(\omega_{n})x$$
- **Remark**: Note that $\omega\mapsto E(\omega)$ is not $\sigma$-additive. The sum does not converge in $\mathcal{B}(\mathcal{H})$ in general!
---
> [!lemma] Lemma 2
> Assume $\{ x_{n}: n\geq 1 \}$ is pairwise orthogonal. Then, the following are equivalent:
> 1. $\sum_{n=1}^{\infty}x_{n}$ converges.
> 2. $\sum_{n=1}^{\infty}\left\| x_{n} \right\|^{2}$ converges.
> 3. $\sum_{n=1}^{\infty}\braket{ x_{n} , y }$ converges for all $y\in \mathcal{H}$.

> [!proof]+
> 1 is equivalent to 2 by [[Hilbert Space|Pythagoras]]. (the partial sum is Cauchy in one iff it is in another).
> 1. (1=>3): We have; $$\left| \sum_{n=k}^{\ell}\braket{ x_{n} , y }  \right| =\left| \left\langle \sum_{n=k}^{\ell} x_{n},y  \right\rangle \right|\leq \left\| \sum_{n=k}^{\ell}x_{n} \right\| \left\| y \right\|  $$Therefore, 3 is Cauchy if 1 is Cauchy.
> 2. (3)
> 