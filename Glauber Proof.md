#proof 

Consider the SK Hamiltonian on $\Omega :=\{ \pm  1\}^N$ where:
$$H_{N}(x):=\frac{1}{2}x^\top Jx,\qquad J_{ij}=J_{ji}\sim \mathcal{N}(0,1/N),\quad J_{ii}=0$$
We write that: $$\mu_{\beta}(x) \propto \exp(\beta H_{N}(x))$$and $M_{N}:= \max_{x}H_{N}(x)$. Then, it is known that $M_{N} / N \to P_{*}$ where $P_{*}$ is the Parisi constant. We show the following:

> [!lemma] Theorem 
> For every $0<\varepsilon$, there is a finite constant $B:=B(\varepsilon)<+\infty$ and a deterministic annealing schedule $\beta(t)\subseteq [\beta_{0},B]$ s.t. the continuous time Glauber dynamics initialized from $X_{0}\sim \text{Unif}(\Omega)$ runs for polynomially many sweeps in $N$ and satisfies: $$\liminf_{ N \to \infty } \frac{1}{N}\mathbb{E}[H_{N}(X_{T})]\ge P_{*}-\varepsilon$$