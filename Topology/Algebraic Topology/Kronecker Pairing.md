#Definition #AlgebraicTopology 

> [!definition]
> Let $X$ be a [[topological space]] and $G$ an [[abelian group]].
> 1. the ***Kronecker pairing*** is a bilinear map: $$\braket{ \cdot  , \cdot  } :H^p(X;G)\times H_{p}(X)\to G,\quad ([\varphi],[c])\mapsto \varphi(c)$$

^995fc2

---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. the Kronecker pairing is well-defined.
> 2. $\braket{ \cdot , \cdot }$ induces a linear map $H^p(X;G)\otimes H_{p}(X)\to G$

^b1ea26

> [!proof]-
> We have:
> 1. Let $\varphi'-\varphi\in B^p$ and $c'-c\in B_{p}$. Then, $\varphi'-\varphi=\delta(\psi)$ and $c'-c=\partial(b)$. Therefore, $$\begin{aligned}\varphi'(c')-\varphi(c)&=\varphi'(c'-c)+(\varphi'-\varphi)(c)=\varphi'(\partial b)+\delta \psi(c)\\&=\underbrace{ \varphi'(\partial b) }_{ =0 }+(-1)^p \psi(\underbrace{ \partial c }_{ =0 })=0\end{aligned}$$ 
> 2. By universal property of [[tensor product]].

^917623

---
![[Cap Product#^804bda]]
![[Cap Product#^9fad4a|p]]

---
