#Definition #FunctionalAnalysis 

> [!lemma] Lemma 1
> Let $S$ be an infinitely countable set. Then, there exists $\mathcal{A}\subseteq \mathcal{P}(S)$ s.t.:
> 1. for all $U\in\mathcal{A}$, $U$ is infinite.
> 2. for all $U,V\in \mathcal{A}$ with $U\neq V$, $U\cap V$ is finite.
> 3. $\mathcal{A}$ is uncountable.

> [!proof]-
> We have that $S=\mathbb{Q}\cap(0,1)$. Then, let $W=(0,1)\backslash \mathbb{Q}$. Then, for any $a\in W$, there exists $(x_{n})_{n\geq 1}$ s.t. $\lim_{ n \to \infty }x_{n}=a$. Hence, we define $$U_{a}=\{ x_{n} \}_{n\geq 1}$$and $$\mathcal{A}=\{ U_{a}:a\in W\}$$It holds that: 
> 1. $U_{a}$ is infinite as otherwise $a\in \mathbb{Q}$. 
> 2. $U_{a}\cap U_{b}$ is finite for $a\neq b$ as otherwise there exists two infinite sequences converging to different values.
> 3. $\mathcal{A}$ is obviously uncountable.
---