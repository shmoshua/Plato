#ProbabilityTheory 

#### 1. Law of Large Numbers
Convergence.
1. $X_{n} \to X$ a.s. if $\mathbb{P}(\lim_{ n \to \infty }X_{n}=X)=1$.
2. $X_{n}\to X$ $\mathbb{P}$ if $\lim_{ n \to \infty }\mathbb{P}(\left| X_{n}-X \right|>\varepsilon) = 0$ for all $\varepsilon> 0$.
3. $X_{n}\to X$ in distribution if $\lim_{ n \to \infty }F_{X_{n}}(x)=F_{X}(x)$ for all $x$.

But,
1. a.s. => P and P => d but converse isn't true. Ber(1/2).
2. WLLN, SLLN, CLT $\overline{X}_{n}\to \mathcal{N}(\mathbb{E}[X], \text{Var(X)} / n)$.

Let $(X_{n})_{n}$ be an i.i.d sequence where: $$f_{X_{n}}(x)=2x\cdot \mathbb{1}_{0\leq x \leq 1}$$
1. Compute $\mathbb{E}[X_{1}]$ and $\sigma^{2}_{X_{1}}$. 2/3, 1/18
2. Compute exp and variance of $T_{n}:= \frac{1}{\sqrt{ n }}\sum_{i=1}^{n}X_{i}$.
3. Show that $\mathbb{P}\left( T_{n}\geq \frac{5\sqrt{ n }}{4} \right)< \frac{3}{5}$.
4. Compute the limit $\lim_{ n \to \infty } T_{n} / \sqrt{ n }$ in probability. 