#Definition #AlgebraicTopology #Topology 

> [!definition]
> The ***complex projective space*** $\mathbb{C}\mathbb{P}^n$ is given by the [[Quotient Topology|quotient space]]:$$\mathbb{C}\mathbb{P}^n:=(\mathbb{C}^{n+1} \backslash \{ 0 \}) /\{(z,\lambda z):z\in \mathbb{C}^{n+1} \backslash \{ 0 \},0\neq\lambda \in \mathbb{C} \}$$
- **Notation**: For the quotient map $\pi:\mathbb{C}^{n+1} \backslash \{ 0 \}\to \mathbb{C}\mathbb{P}^n$, we have that $[z_{0}:\dots :z_{n}]:=\pi(z_{0},\dots,z_{n})$.
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. $\mathbb{C}\mathbb{P}^n$ is compact Hausdorff.

> [!proof]+
> We have that:
> 1. To show that $\mathbb{C}\mathbb{P}^n$ is Hausdorff, we first show that $\pi$ is open. Let $U\subseteq \mathbb{C}^{n+1} \backslash \{ 0 \}$ be open. Then, $$\pi ^{-1}(\pi(U))=\{ \lambda z:\lambda\in \mathbb{C} \backslash \{ 0 \},z\in U \}$$Indeed, if $w\in \pi ^{-1}(\pi(U))$, then $\pi(w)\in\pi(U)$ and there exists $z\in U$ with $\pi(w)=\pi(z)$, i.e. $w\sim z$. Conversely, for $\lambda z$, we have that $\pi(\lambda z)=\pi(z)\in \pi(U)$. Hence, $\pi ^{-1}(\pi(U))$ is open and so is $\pi(U)$. 
>    
>    Further, we show that the graph $\Gamma:=\{ (z,\lambda z):z\in \mathbb{C}^{n+1} \backslash \{ 0 \},0\neq\lambda\in \mathbb{C}\}$ is closed. 