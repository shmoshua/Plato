#Definition #RL 

> [!definition]
> A ***Markov decision process (MDP)*** is a tuple $(\mathcal{X},\mathcal{A},P,r,\mu)$ where:
> 1. An at most countable set $\mathcal{X}$ of **states**.
> 2. An at most countable set $\mathcal{A}$ of **actions**.
> 3. the ***transition probabilities*** $P:\mathcal{X}\times \mathcal{A}\to M^1(\mathcal{X})$ where $M^1(X)$ denotes the [[Space of Probability Measures|space of all probability measures]] on $X$. 
> 	1. For $s\in \mathcal{X}$ and $a\in \mathcal{A}$, we have that $P(s,a)$ is denoted with $P(\cdot|s,a)$. 
> 4. the ***reward*** $r:\mathcal{X}\times \mathcal{A}\to \mathbb{R}$
> 5. the ***initial state*** $\mu\in M^1(\mathcal{X})$. 
- **Related definition**: An MDP $M$ is:
	1. ***finite*** if $\mathcal{X}$ and $\mathcal{A}$ are finite.
- **Related definition**: For an MDP $M$, 
	1. $M$ is in ***finite horizon setting*** with $T\in \mathbb{N}$, if we aim to find $\max\mathbb{E}\left[ \sum_{t=0}^{T-1}r(X_{t},A_{t}) \right]$
	2. $M$ is in ***infinite horizon setting*** with ***discount*** $0\leq \gamma<1$, if we aim to find $\max\mathbb{E}\left[ \sum_{t=0}^{\infty}\gamma^tr(X_{t},A_{t}) \right]$
- **Related definition**: For an MDP $M$,
	1. A ***deterministic policy*** is a function $\pi:\mathcal{X}\to \mathcal{A}$.
	2. A ***randomized policy*** is a function $\pi:\mathcal{X}\to M^1(\mathcal{A})$. We denote $\pi(x):=\pi(\cdot|x)$ for all $x\in \mathcal{X}$.
- **Related definition**: For an MDP $M$ and a policy $\pi$,
	1. the ***state value function*** $V^\pi:\mathcal{X}\to \mathbb{R}$ where: $$V^\pi(x):=\mathbb{E}\left[ \sum_{t=0}^{\infty}\gamma^tr(X_{t},\pi) \right] $$
---
##### Properties
> [!lemma] Proposition 1 (MDP is a Markov Chain)
> Let $M$ be an MDP and $\pi:\mathcal{X}\to M^1(\mathcal{A})$ a policy. Let $X_{t+1}\sim P(\cdot|X_{t},A_{t})$ where $A_{t}\sim \pi(\cdot|X_{t})$.
> Then, 
> 1. $(X_{t})_{t\geq 0}$ is a [[Markov chain]] with $P(x'|x)=\sum_{a\in \mathcal{A}}^{}\pi(a|x)P(x'|x,a)$.

> [!proof]+
> We have that: 
> 1. Notice that: $$\begin{align}P(x'|x)&=\sum_{a\in \mathcal{A}}^{}\mathbb{P}(A_{t}=a|X_{t}=x)\mathbb{P}(X_{t+1}=x'|A_{t}=a,X_{t}=x)\\&=\sum_{a\in \mathcal{A}}^{}\pi(a|x)P(x'|x,a)\end{align}$$Further, $$\sum_{x'\in \mathcal{X}}^{}P(x'|x)=\sum_{x'\in \mathcal{X}}^{}\sum_{a\in \mathcal{A}}^{}\pi(a|x)P(x'|x,a)=\sum_{a\in \mathcal{A}}^{}\pi(a|x)=1$$