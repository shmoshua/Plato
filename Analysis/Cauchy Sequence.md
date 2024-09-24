#Definition #Analysis 

> [!definition]
> For a [[Metric Space]] $(X,d)$, a sequence $\{ x_{n} \}_n\subseteq X$ is called a ***Cauchy sequence*** if for all $\varepsilon>0$ there exists $N\in \mathbb{N}$ s.t. $$d(x_{n},x_{N})<\varepsilon$$ for all $n \geq N$.
- **Equivalent definition**: for all $\varepsilon>0$, there exists $N\in \mathbb{N}$ s.t. $$d(x_{m},x_{n})<\varepsilon$$ for all $m,n\geq N$. (cf Theorem 1 for proof)

---
##### Properties
> [!lemma] Theorem 1
> A sequence $\{ x_{n} \}_{n}\subseteq X$ is Cauchy if and only if for all $\varepsilon>0$ there exists $N\in \mathbb{N}$ s.t. $$d(x_{m},x_{n})<\varepsilon,\quad \forall m,n\geq N$$

> [!proof]-
> (=>): Let $\varepsilon>0$. Then, there exists $N\in \mathbb{N}$ s.t. $\|x_{n}-x_{N}\|< \frac{\varepsilon}{2}$ for all $n\geq N$. Then, for all $n,m \geq N$, $$d(x_{m},x_{n})\leq d(x_{m},x_{N})+d(x_{N},x_{n})<\varepsilon$$ 
> (<=): Follows from the definition by setting $n=N$.
---
> [!lemma] Theorem 2
> If a sequence $\{ x_{n} \}_{n}\subseteq X$ [[Convergence of Sequences|converges]], it is Cauchy. (The converse is not always true)

> [!proof]-
> Let $x:=\lim_{ n \to \infty }x_{n}$ and $\varepsilon>0$. Then, there exists $N\in \mathbb{N}$ s.t. $d(x_{n},x)<\varepsilon /2$ for all $n\geq N$. Therefore, $$d(v_{m},v_{n})\leq d(v_{m},v)+d(v,v_{n})<\varepsilon,\quad\forall m,n\geq N$$

---

