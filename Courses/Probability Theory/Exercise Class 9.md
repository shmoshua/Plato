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
5. Find $\sigma^{2}$ s.t. $\frac{\frac{3}{2}T_{n}- \sqrt{ n }}{\sigma} \overset{ d }{ \to }\mathcal{N}(0,1)$.

---
Let $(X_{n})_{n}$ with $X_{n}\sim \mathcal{U}\left( 0,1+\frac{1}{n} \right)$ independent. Let $X\sim \mathcal{U}(0,1)$. Then, 
1. in distribution? 
2. in probability?

---
Let $(X_{n})_{n}$ be iid with discrete with: $$\mathbb{P}(X_{1}=-1)=\mathbb{P}(X_{1}=0)=\frac{1}{4},\quad \mathbb{P}(X_{1}=1)=\frac{1}{2}$$
1. show that $\mathbb{E}[X_{1}]=\frac{1}{4}$ and compute $\sigma^{2}_{X_{1}} = \frac{11}{16}$
2. show that $\mathbb{P}(S_{n}\geq n /2)\to 0$
3. find the probability $\mathbb{P}\left( \lim_{ n \to \infty }S_{n} / n = \frac{1}{4} \right)$
4. show that for every $\varepsilon>0$ there exists $A$ large enough s.t. $$\lim_{ n \to \infty } \mathbb{P}\left( S_{n}\geq \frac{n}{4}+A\sqrt{ \sigma^{2}\cdot n } \right)\leq \varepsilon$$

---
A random variable is called $\chi^{2}$ with degree $\nu\in \mathbb{N}$ distributed if $Y=\sum_{k=1}^{\nu}Z^{2}_{k}$ where $Z_{1},\dots,Z_{\nu}\sim \mathcal{N}(0,1)$ iid.
1. Find $\mathbb{E}[Y]$ and $\text{Var}(Y)$. ($\nu$ and $2\nu$).
2. Give a lower bound for $\mathbb{P}\left( \left| Y / \nu-1 \right|\leq  \frac{3}{4} \right)$ using Chebysehv. Give a concrete bound for $\nu=12$.
3. Use CLT to find an approximation for above. 