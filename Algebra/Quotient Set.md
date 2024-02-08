#Definition #Algebra-I 

>[!Definition]
>For a [[group]] $G$ and a [[subgroup]] $H \leq G$, 
>1.  $G / H:=\{$[[Coset|$xH$]] $:  x\in G \}$ and
>2.  $H\backslash G:=\{ Hx: x\in G\}$
>
>are the ***left quotient set*** and the ***right quotient set*** of $H$.
- **Related definition**: for $H\leq G$, $|G / H|=|H\backslash G|$ is called the ***index*** of $H$ in $G$ and is denoted as $[G:H].$
---
##### Properties

> [!Lemma] Lemma 1
> Let $H \leq G$. then $G / H$ as well as $H\backslash G$ are partitions of $G$, where each part has the same order as $H$.

> [!proof]-
> From Lemma Cos.1 and Cos.2

---

> [!lemma] Proposition 2
> If $N\unlhd G$, then $G / N:=\{ xN:x \in G\}$ builds a group called ***quotient group*** with the binary operation defined as: $$(xN)(yN)=(xy)N$$

> [!proof]-
> We will show the followings:
> 1. First, we show that the binary operation is well-defined. Let $xN=\tilde{x}N$ and $yN=\tilde{ y}N$. We need to show that $xyN = \tilde{x}\tilde{ y}N$. Then, from [[Coset| Lemma 1.4]], $x^{-1}\tilde{x}\in N$ and $y^{-1}\tilde{ y}\in N$. As $N \unlhd G$, we have: $$(xy)^{-1}(\tilde{x}\tilde{y})=y^{-1}x^{-1}\tilde{ x}\tilde{y}\in y^{-1}N \tilde{y}=\underbrace{ y^{-1}Ny }_{ =:N }\underbrace{ y^{-1}\tilde{ y} }_{ \in N }=N$$
>     Therefore, $xyN=\tilde{x}\tilde{y}N$.
>  2. Now, we show the associativity: for $x,y,z\in G$: $$(xN)((yN)(zN))=(x(yz))N=((xy)z)N=((xN)(yN))(zN)$$
>  3. For all $x\in G$, it holds that:$$(eN)(xN)=(ex)N=xN$$ Therefore, $eN=N$ is the neutral element.
>  4. For all $x \in G$, it holds that: $$(x^{-1}N)(xN)=(x^{-1}x)N=eN=N$$ Therefore, $x^{-1}N$ is the inverse element of $xN$.

---