#Definition #FunctionalAnalysis 

> [!definition]
> Let $G$ be a countable [[group]] and $X$ a compact [[Hausdorff Space]] s.t. there exists a [[Group Action|group action]] $G\to \text{Homeo}(X)$ by homeomorphisms. Then, firstly, let $$M^1(X)^G:=\{ \mu\in M^1(X):\mu \text{ is }G\text{-invariant} \}$$Then, $\mu\in M^1(X)^G$ is called ***ergodic*** if for any $G$-invariant measurable subset $S\subseteq X$, $$\mu(S)=0\lor \mu(X\backslash S)=0$$
- **Remark**: Notice that $M^1(X)^G$ is convex and weak\*-closed, therefore, compact.
---
##### Properties
> [!lemma] Lemma 1
> $\mu\in M^1(X)^G$ is ergodic if and only if $\mu$ is an [[Extreme Points and Sets|extreme point]] in $M^1(X)^G$.

> [!proof]-
> <=: If $\mu$ is not ergodic, then there exists a $G$-invariant measurable subset $S\subseteq X$ s.t. $0<\mu(S)<1$. We then define: 
> $$\mu_{1}:=\frac{\mu|_{S}}{\mu(S)},\quad \mu_{1}(A)=\frac{\mu(A\cap S)}{\mu(S)} ,\quad \mu_{2}:=\frac{\mu|_{X \backslash S}}{\mu(X \backslash S)}$$ Then, $\mu_{1},\mu_{2}\in M^1(X)^G$ and $$\mu=\mu(S)\mu_{1}+\mu(X \backslash S)\mu_{2}$$Since $\mu\neq \mu_{1}$ and $\mu\neq \mu_{2}$, $\mu$ is not an extreme point. 
---
> [!lemma] Corollary 2
> If there exists a $G$-invariant probability measure on $X$, there exists an ergodic measure. Further, every $G$-invariant probability measure is a weak\*-limit of the convex combination of the ergodic measures.

> [!proof]-
> Follows from Lemma 1 and [[Extreme Points and Sets|Krein-Milman]].
---
