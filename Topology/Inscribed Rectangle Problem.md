#Definition #Topology 

> [!definition]
> Let $\gamma:S^1\to \mathbb{R}^{2}$ be an injective loop. The inscribed rectangle problem asks:
> > "Does any such $\gamma$ admit four points in $\gamma(S^1)$ that form the vertices of a rectangle?"
---
##### Properties
> [!lemma] Theorem 1 (Vaughan, 1977)
> For any injective loop $\gamma:S^1\to \mathbb{R}^{2}$, $\gamma$ admits an inscribed rectangle.

> [!proof]-
> Define: $M:=((S^1\times S^1) \backslash\Delta)/_{\sim}$ where $(s,t)\sim(t,s)$ and no other identification. Now, let $$\phi:M\to \mathbb{R}^{3},\quad\{ s,t \}\mapsto\left( \frac{\gamma(s)+\gamma(t)}{2},\left| \gamma(s)-\gamma(t) \right|  \right)$$which is well-defined as it is symmetric. Then, an inscribed rectangle exists if and only if $\phi$ is not injective.
> 
> Assume that $\phi$ is injective. Then, we observe that $\phi(M)\subseteq \{ (x,y,z):z>0 \}$. Now, if we define $M':=(S^1\times S^1) / \sim$, then $\phi(M' \backslash M)=\gamma(S^1)\times \{ 0 \}$. Now, define: $$K:=\phi(M)\cup (\gamma(S^1)\times \{ 0 \})\cup \{ (x,y,-z):(x,y,z)\in \phi(M) \}$$But $M$ is an open Möbius strip and so is $\phi(M)$ by the injectivity. Therefore, $K$ is a Klein bottle. Therefore, $\phi$ embeds $K$ into $\mathbb{R}^3$, which is a contradiction.
---
