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
	1. the ***state value function*** $V^\pi:\mathcal{X}\to \mathbb{R}$ where: $$V^\pi(x):=\mathbb{E}_{\pi}\left[ \left. \sum_{t=0}^{\infty}\gamma^tr(X_{t},A_{t}))  \right| X_{0}=x\right] =\underset{ \begin{array}{c}A_{t}\sim \pi(\cdot |X_{t})\\X_{t+1}\sim P(\cdot |X_{t},A_{t})\end{array} }{ \mathbb{E} }\left[ \left. \sum_{t=0}^{\infty}\gamma^tr(X_{t},A_{t}))  \right| X_{0}=x\right] $$
	2. the ***state-action value function*** $Q^\pi:\mathcal{X}\times \mathcal{A}\to \mathbb{R}$ where: $$Q^\pi(x,a):=\mathbb{E}_{\pi}\left[ \left. \sum_{t=0}^{\infty}\gamma^tr(X_{t},A_{t}))  \right| X_{0}=x,A_{0}=a\right]  $$
- **Related definition**: A deterministic policy $\pi$ is ***greedy*** w.r.t a value function $V$ if: $$\pi(x):=\underset{ a\in \mathcal{A} }{ \arg\max }\ r(x,a)+\gamma \sum_{x'\in \mathcal{X}}^{}P(x'|x,a)\cdot V(x')$$
---
##### Properties
> [!lemma] Proposition 1 
> Let $M$ be an MDP and $\pi:\mathcal{X}\to M^1(\mathcal{A})$ a policy. Let $X_{t+1}\sim P(\cdot|X_{t},A_{t})$ where $A_{t}\sim \pi(\cdot|X_{t})$.
> Then, 
> 1. $(X_{t})_{t\geq 0}$ is a [[Markov chain]] with $P(x'|x)=\sum_{a\in \mathcal{A}}^{}\pi(a|x)P(x'|x,a)$.
> 2. for any $x\in \mathcal{X}$, $$V^\pi(x)=\sum_{a\in \mathcal{A}}^{}\left( r(x,a)+\gamma \sum_{x'\in \mathcal{X}}^{}V^\pi(x')P(x'|x,a) \right) \pi(a|x)$$
> 3. 

> [!proof]-
> We have that: 
> 1. Notice that: $$\begin{align}P(x'|x)&=\sum_{a\in \mathcal{A}}^{}\mathbb{P}(A_{t}=a|X_{t}=x)\mathbb{P}(X_{t+1}=x'|A_{t}=a,X_{t}=x)\\&=\sum_{a\in \mathcal{A}}^{}\pi(a|x)P(x'|x,a)\end{align}$$Further, $$\sum_{x'\in \mathcal{X}}^{}P(x'|x)=\sum_{x'\in \mathcal{X}}^{}\sum_{a\in \mathcal{A}}^{}\pi(a|x)P(x'|x,a)=\sum_{a\in \mathcal{A}}^{}\pi(a|x)=1$$
> 2. We have that: $$\begin{align}V^\pi(x)&=\mathbb{E}_{\mu}[r(X_{0},A_{0})|X_{0}=x ]+\mathbb{E}_{\mu}\left[\left. \sum_{t=1}^{\infty}\gamma^tr(X_{t},A_{t}))  \right| |X_{0}=x \right]\\&=\sum_{a\in \mathcal{A}}^{}r(x,a)\pi(a|x)+\gamma\mathbb{E}_{\mu}\left[\left. \sum_{t=0}^{\infty}\gamma^{t}r(X_{t+1},A_{t+1}))  \right| X_{0}=x \right]\\&=\sum_{a\in \mathcal{A}}^{}r(x,a)\pi(a|x)+\gamma \mathbb{E}_{\mu}\left[\left.  \mathbb{E}_{\mu}\left[\left. \sum_{t=0}^{\infty}\gamma^{t}r(X_{t+1},A_{t+1}))  \right| X_{1}=x' \right]  \right| X_{0}=x\right]\\&=\sum_{a\in \mathcal{A}}^{}r(x,a)\pi(a|x)+\gamma \mathbb{E}_{\mu}\left[\left. V^\pi(x')\right| X_{0}=x\right]\\&=\sum_{a\in \mathcal{A}}^{}r(x,a)\pi(a|x)+\gamma \sum_{a\in \mathcal{A}}^{}\sum_{x'\in \mathcal{X}}^{}V^\pi(x')P(x'|x,a)\pi(a|x)\\&=\sum_{a\in \mathcal{A}}^{}\left( r(x,a)+\gamma \sum_{x'\in \mathcal{X}}^{}V^\pi(x')P(x'|x,a) \right) \pi(a|x)\end{align}$$

---
> [!lemma] Proposition 2 (Computing Value Function)
> Let $M$ be an MDP, $\pi$ a policy. We further define: $$r^\pi_{x}:=\sum_{a\in \mathcal{A}}^{}r(x,a)\pi(a|x),\quad T^\pi_{x,x'}:=\sum_{a\in \mathcal{A}}^{}P(x'|x,a)\pi(a|x)$$Then, 
> 1. $V^\pi=r^\pi+\gamma T^\pi V^\pi$.
> 2. $B:\mathbb{R}^{\left| \mathcal{X} \right|}\to\mathbb{R}^{\left| \mathcal{X} \right|},v\mapsto r^\pi+\gamma T^\pi v$ is a contractible iteration function. In particular, it admits a unique fixed point $V^\pi$.

> [!proof]-
> We have that: 
> 1. Obvious.
> 2. We have that: $$\begin{align}\left\| B(u)-B(v) \right\|_{\infty} &=\left\| \gamma T^\pi u-\gamma T^\pi v \right\| _{\infty}\\&=\gamma\|T^\pi(u-v)\|_{\infty}\\&=\gamma \cdot \max_{x'}\left| \sum_{x'\in \mathcal{X}}^{} \sum_{a\in \mathcal{A}}^{}P(x'|x,a)\pi(a|x)(u-v)_{x'} \right|\\&\leq\gamma \cdot \max_{x'}\left| \sum_{a\in \mathcal{A}}^{}\pi(a|x) \right|\cdot \|u-v\|_{\infty}\\&=\gamma\|u-v\|_{\infty} \end{align}$$The rest follows from Banach's fixed point theorem.

- **Remark**: If $M$ is finite, by noting $r^\pi=(I-\gamma T^\pi)V^\pi$, we can compute $V^\pi$ exactly by solving the linear systems of equation directly in $O(\left| \mathcal{X} \right|^3)$.
---
> [!lemma] Theorem 3 (Bellman)
> Let $\pi ^{*}$ be a deterministic policy. TFAE:
> 1. $\pi ^{*}=\underset{ \pi }{ \arg\max }\ \mathbb{E}_{X_{0} \sim \mu}[V^\pi(X_{0})]$, i.e. $\pi ^{*}$ is an optimal policy.
> 2. $\pi ^{*}$ is greedy w.r.t. $V^{\pi ^{*}}$.
---
> [!lemma] Theorem 4 (Policy Iteration)
> ```pseudo
> \begin{algorithm} \caption{PolicyIteration($M,\varepsilon$)}
> \begin{algorithmic} 
> \State initialize policy $\pi$ arbitrarily
> \For{$t\geq 1$}
> \State $\pi\gets \pi_{V^\pi}$, the greedy policy associated with $V^\pi$
\EndFor
> \Return $\pi$
\end{algorithmic}
\end{algorithm}
> ```
> Then, let $\pi_{t}$ be the policy $\pi$ at timestep $t$. It holds that:
> 1. $V^{\pi_{t+1}}\geq V^{\pi_{t}}$. In particular, if $V^{\pi_{t+1}}\neq V^{\pi_{t}}$, then there exists $x\in \mathcal{X}$ with $V^{\pi_{t+1}}(x)> V^{{\pi}_{t}}(x)$
> 2. If $M$ is a finite MDP, the algorithm converges to an optimal policy. 
---
> [!lemma] Theorem 5 (Value Iteration)
> ```pseudo
> \begin{algorithm} \caption{ValueIteration($M,\varepsilon$)}
> \begin{algorithmic} 
> \State initialize $V(x)\gets \max_{a\in \mathcal{A}}r(x,a)$ for all $x\in \mathcal{X}$.
> \For{$t\geq 1$}
> \State $V(x)\gets\max_{a\in \mathcal{A}}Q(x,a)$ where $Q$ is the $Q$-function associated with $V$.
> \State stop if $\|V_{\text{old}}-V_{\text{new}}\|_{\infty}\leq \varepsilon$
\EndFor
> \Return $\pi_{V}$, i.e. the greedy policy associated with $V$.
\end{algorithmic}
\end{algorithm}
> ```
> 
> Then, 
> 1. the algorithm converges to an optimal policy.

> [!proof]-
> Let $B:\mathbb{R}^n\to \mathbb{R}^n$ where: $$(Bu)_{x}:=\max_{a\in \mathcal{A}}Q(x,a)$$where $Q$ is associated with $u$. Then, we first show that $B$ is a contraction: $$\begin{align} \|Bu-Bv\|_{\infty}&=\max_{x}\left| (Bu)_{x}-(Bv)_{x} \right|\\&\leq\max_{x}\max_{a}\left| Q_{u}(x,a)-Q_{v}(x,a) \right| \\&\leq\gamma\max_{x}\max_{a}\sum_{x'}^{}p(x'|x,a)\left| u(x')-v(x') \right| \\&\leq\gamma \cdot \|u-v\|_{\infty}\end{align}$$Hence, $B$ converges to a unique fixed point $V$ which is given by the algorithm. The rest holds by Bellman's theorem.
- **Remark**: Value iteration doesn't converge to an exact solution in general but a $\varepsilon$-optimal one. 
---

