#Definition #LST #Analysis 

> [!definition]
> For a metric space $(X,d)$, a sequence $\{ x_{n} \}_n\subseteq X$ is called a ***Cauchy sequence*** if for all $\varepsilon>0$ there exists $N\in \mathbb{N}$ s.t. $$d(x_{n},x_{N})<\varepsilon$$ for all $n \geq N$.
- **Equivalent definition**: for all $\varepsilon>0$, there exists $N\in \mathbb{N}$ s.t. $$d(x_{m},x_{n})<\varepsilon$$ for all $m,n\geq N$. (cf Theorem 1 for proof)

---
##### Properties
> [!lemma] Theorem 1
> A sequence $\{ v_{i} \}_{i\geq 0}$ is Cauchy if and only if for all $\varepsilon >0$ there exists $N \in \mathbb{N}$ s.t. $$\left\| v_{m}-v_{n} \right\| <\varepsilon$$ for all $m,n \geq N$.

> [!proof]-
> (=>): Fix an arbitrary $\varepsilon>0$. Then, we have $N\in \mathbb{N}$ s.t. $\|v_{n}-v_{N}\|< \frac{\varepsilon}{2}$ for all $n\geq N$. Then, for all $n,m \geq N$, $$\|v_{m}-v_{n}\|=\|v_{m}-v_{N}+v_{N}-v_{n}\|\leq\|v_{m}-v_{N}\|+\|v_{n}-v_{N}\|<2\cdot \frac{\varepsilon}{2}=\varepsilon$$
> (<=): Follows from the definition by setting $n=N$.
---
> [!lemma] Theorem CauchySeq.2
> If a sequence $\{ v_{i} \}_{i\geq 0}$ [[Convergence of Sequences|converges]], it is Cauchy. (The converse is not always true)

> [!proof]-
> Let $v:=\lim_{ n \to \infty }v_{n}$. Fix an arbitrary $\varepsilon>0$. Then, we have $N\in \mathbb{N}$ s.t. $\|v_{m}-v\|< \frac{\varepsilon}{2}$ for all $m\geq N$. Then, for all $n,m \geq N$:
> $$\left\| v_{m}-v_{n} \right\| =\|v_{m}-v+v-v_{n}\|\leq\|v_{m}-v\|+\|v_{n}-v\|<2\cdot \frac{\varepsilon}{2}=\varepsilon$$
> Therefore, $\{ v_{i} \}_{{i\geq 0}}$ is Cauchy.

---

