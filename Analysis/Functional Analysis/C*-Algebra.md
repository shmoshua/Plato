#Definition #FunctionalAnalysis 

> [!definition]
> An ***involutive Banach algebra*** is a [[Banach algebra]] $B$ with a map $x\mapsto x^{*}$ s.t. 
> 1. $(x^{*})^{*}=x$ for all $x\in B$,
> 2. $(\alpha x+\beta y)^{*}=\overline{\alpha} x^{*}+\overline{\beta} y^{*}$ for all $\alpha,\beta\in \mathbb{C}$, $x,y\in B$,
> 3. $(xy)^{*}=y^{*}x^{*}$ for all $x,y\in B$,
> 4. $\left\| x^{*} \right\|=\|x\|$ for $x\in B$.
>
> An involutive Banach algebra is a ***C\*-algebra***, if $\left\| xx^{*} \right\|=\|x\|\|x^{*}\|$ for all $x\in B$.
---
##### Examples
> [!lemma] Example 1
> For a [[locally compact Hausdorff space]] $X$, Then, 
> 1. $C_{b}(X)$ is a Banach algebra
> 2. $C_{b}(X)$ is involutive with $f^{*}=\overline{f}$.
> 3. $C_{b}(X)$ is a C*-algebra.

> [!proof]- Proof (Incomplete)
> We have: 
> 1. $$\left\| ff^{*} \right\|_{b}=\sup_{x\in X}\left| \overline{f(x)}f(x) \right| =\sup_{x\in X}\left| f(x) \right| ^{2}=\left\| f \right\| ^2_{b}=\left\| f^{*} \right\|_{b}\left\| f \right\|_{b} $$
---
> [!lemma] Example 2
> For a [[locally compact Hausdorff space]] $X$, Then, 
> 1. $C_{0}(X)$ is a C*-algebra.
> 2. $C_{0}(X)$ is [[C-Algebra|unital]], if and only if $X$ is compact.
---
