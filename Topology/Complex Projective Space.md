#Definition #AlgebraicTopology #Topology 

> [!definition]
> The ***complex projective space*** $\mathbb{C}\mathbb{P}^n$ is given by the [[Quotient Topology|quotient space]]:$$\mathbb{C}\mathbb{P}^n:=(\mathbb{C}^{n+1} \backslash \{ 0 \}) /\{(z,\lambda z):z\in \mathbb{C}^{n+1} \backslash \{ 0 \},\lambda \in \mathbb{C}^{\times} \}$$Alternatively, it can be written as orbits$$\mathbb{C}\mathbb{P}^n:=(\mathbb{C}^{n+1} \backslash \{ 0 \}) / \mathbb{C}^\times$$given by the [[group action]] $(\lambda,z)\mapsto \lambda z$.
- **Notation**: For the quotient map $\pi:\mathbb{C}^{n+1} \backslash \{ 0 \}\to \mathbb{C}\mathbb{P}^n$, we have that $[z_{0}:\dots :z_{n}]:=\pi(z_{0},\dots,z_{n})$.

---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. $\pi$ is an open map.
> 1. $\mathbb{C}\mathbb{P}^n$ is compact Hausdorff.

> [!proof]+
> We have that:
> 1. let $U\subseteq \mathbb{C}^{n+1} \backslash \{ 0 \}$ be open. Then, we claim that: $$\pi ^{-1}(\pi(U))=\{ \lambda x:\lambda\in \mathbb{C}^\times,x\in U \}=\bigcup_{\lambda\in \mathbb{C}^\times}^{}\lambda U$$where we have an open set on the right. Indeed, if $\pi(z)\in \pi(U)$, then $\pi(z)=\pi(x)$ for some $x\in U$ and $z=\lambda x$ for some $\lambda\in \mathbb{C}^\times$. Conversely, we have for $\lambda\in \mathbb{C}^\times$ and $x\in U$, $\pi(\lambda x)=\pi(x)$ and $\pi(\lambda x)\in \pi(U)$.
> 1. To show that it is compact, we show that $\pi(S^{2n+2})=\mathbb{C}\mathbb{P}^n$. For $[z_{0}:\dots:z_{n}]\in \mathbb{C}\mathbb{P}^n$, we have that: $$\left( \frac{z_{0}}{\|z\|} ,\dots,\frac{z_{n}}{\|z\|} \right)\in S^{2n+2}$$As $S^{2n+2}$ is compact, $\mathbb{C}\mathbb{P}^n$ is compact.
>   
> 	  To show that it is Hausdorff, let $[z_{0}:\dots:z_{n}]$ an $[y_{0}:\dots:y_{n}]$ be two disjoint points in $\mathbb{C}\mathbb{P}^n$. Then, there exist disjoint $U,V\subseteq \mathbb{C}^{n+1} \backslash \{ 0 \}$ s.t. $z:=(z_{0},\dots,z_{n})\in U$ and $y:=(y_{0},\dots,y_{n})\in V$. Then, $\pi(U)$ and $\pi(V)$ are open neighborhoods of $\pi(z),\pi(y)$. We are left to show that they are disjoint. Assume that $\pi(x)\in \pi(U)\cap \pi(V)$. Then, 