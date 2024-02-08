#Definition #MeasureTheory 

> [!definition]
> A ***Vitali set*** $P\subseteq[0,1)$ is a known non-[[Lebesgue Measure|Lebesgue measurable]] set, constructed by [[Axiom of Choice]] from a family of equivalence classes. For the equivalence relation defined as $x\sim y\iff x-y\in \mathbb{Q}$ for $x,y\in[0,1)$ and the family: $$\mathcal{F}:=\{ [x]_{\sim} | x\in[0,1) \}$$
> the Vitali set $P$ contains exactly 1 element of each equivalence class $[x]$. 
---
##### Properties
> [!lemma] Theorem 1
> The Vitali set $P$ is not $\mathcal{L}^1$-measurable.

> [!proof]-
> Let $\{ r_{j} \}_{j=0}^\infty$ be the enumeration of $Q \cap [0,1)$ with $r_{0}=0$. We then define $P_{j}:=P \oplus r_{j}$ where $x \oplus y = x+y \mod 1$.Then,
> > [!lemma] Claim 1
> > We have the following claims:
> > 1. $P_{j_{1}}\cap P_{j_{2}}=\varnothing$ for $j_{1}\neq j_{2}$
> > 2. $\bigcup_{j=0}^{\infty}P_{j}=[0,1)$
> 
> > [!proof]-
> > We show that:
> > 1. Assume there exists $x\in P_{j_{1}}\cap P_{j_{2}}$. Then, we have $p_{1},p_{2}\in P$ s.t. $$x=p_{1} \oplus r_{j_{1}}=p_{2}\oplus r_{j_{2}}$$Then, it follows that $p_{1} \sim p_{2}$ and from construction of the Vitali sets, $p_{1}=p_{2}$ and $r_{j_{1}}=r_{j_{2}}$, which implies that $P_{j_{1}}=P_{j_{2}}$.
> > 2. $\subseteq$ is trivial. For $\supseteq$, for any $x\in[0,1)$, there exists by definition $p\in P$ s.t. $x-p\in \mathbb{Q}$. Then, 
> > 	1. if $x=p$, then $x\in\bigcup_{j=0}^{\infty}P_{j}$. 
> > 	2. If $x >p$, then $1 > x-p>0$ and $x=p+r_{j}$ for some $r_{j}$. Therefore, $x\in P_{j}$. 
> > 	3. Similarly, if $x<p$, then $0<x-p+1<1$ and $x=p \oplus r_{j}$. Therefore, $x\in P_{j}\subseteq \bigcup_{j=0}^{\infty}P_{j}$.
> 
> Assume by contradiction that $P$ is $\mathcal{L}^1$-measurable. Then, for $x\in[0,1)$, $P$ is a disjoint union of $P^1$ and $P^2$ where $P^1 :=P\cap[0,1-x)$ and $P^2:=P \cap[1-x,1)$. It follows that: $$P \oplus x=(P^1 \oplus x)\cup(P^2 \oplus x)=(P^1+x)\cup(P^2+x-1)$$Then, $$\mathcal{L}^1(P\oplus x)=\mathcal{L}^1(P^1+x)+\mathcal{L}^1(P^2+x-1)=\mathcal{L}^1(P^1)+\mathcal{L}^1(P^2)=\mathcal{L}^1(P)$$
> Therefore, $$1=\mathcal{L}^1[0,1)=\mathcal{L}^1\left( \bigcup_{j=0}^{\infty}P_{j} \right) =\sum_{j=0}^{\infty}\mathcal{L}^1(P_{j})=\sum_{j=0}^{\infty}\mathcal{L}^1(P)$$which is a contradiction.

- **Remark**: There exists $B\subseteq \mathbb{R}$ s.t. $\mathcal{L}^1(B) < \mathcal{L}^1(B \cap P)+\mathcal{L}^1(B \backslash P)$
- **Remark**: For every $A\subseteq \mathbb{R}$ with $\mathcal{L}^1(A)>0$, there exists $B\subseteq A$ s.t. $B$ is not $\mathcal{L}^1$-measurable.
- **Remark**: If $E \subseteq P$ be $\mathcal{L}^1$-measurable. Then, $\mathcal{L}^1(E)=0$. 
---
