#Definition #FormalLanguageTheory 

> [!definition]
> A ***non-deterministic finite state automaton (FSA)*** over an [[Language|alphabet]] $\mathcal{A}$ is defined as $M:=(Q,i,F,E)$ where:
> 1. $Q$ is a finite set of ***states***. 
> 2. $i\in Q$ is the ***initial state***.
> 3. $F\subseteq Q$ is the set of ***final states***.
> 4. $E\subseteq Q\times \mathcal{A}\times Q$ is a set of ***edges***.
- **Related definition**: An FSA $M$ is ***deterministic*** if for all $(q_{1},a_{1},p_{1}),(q_{2},a_{2},p_{2})\in E$ if $q_{1}=q_{2}$ and $a_{1}=a_{2}$, then $p_{1}=p_{2}$.
- **Related definition**: A language is ***regular*** if it is accepted by some FSA.
---
##### Properties
> [!lemma] Theorem 1 
> Let $M$ be an FSA. Then, there exists a deterministic FSA $M'$ s.t. $\mathcal{L}(M)=\mathcal{L}(M')$.

> [!proof]-
> Let $M':=(2^Q,i, F,E')$ where: $$E':=\{ (S,a,T):T=\{ t: \exists s\in S, (s,a,t)\in E \} \}$$Then, by definition this is a deterministic FSA.
---
> [!lemma] Theorem 1 (Kleene)
> FSA = RegEx


---
##### Examples
> [!h] Example 1
> $\mathcal{L}:=\{ a^nb ^n : n\geq 0 \}$ is non-regular.

> [!proof]+
> We have that:
> 1. Suppose $\mathcal{L}$ is regular, i.e. there exists FSA $M$ s.t. $\mathcal{L}= \mathcal{L}(M)$. However, as $M$ have a finite number of states, there exists $n,m$ with $n\neq m$ s.t. $a^n$ and $a^m$ lead us to the same state. This is a