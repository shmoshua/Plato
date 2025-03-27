#Definition #GraphTheory 

> [!definition]
> Let $G=(V,E,w)$ be a weighted [[graph|simple graph]].
> 1. A ***random walk*** on $G$ is a [[Markov chain]] $(v_{n})_{n\geq 0}\subseteq V$ with initial distribution $p_{0}$ and transition matrix: $$W_{vu}:=\begin{cases}w(u,v) / d(u)&uv\in E\\0&\text{otherwise}\end{cases}$$
> 2. A ***lazy random walk*** on $G$ is a Markov chain $(v_{n})_{n\geq 0}\subseteq V$ with initial distribution $p_{0}$ and transition matrix $\tilde{W}:= \frac{1}{2}(I+W)$
- **Remark**: $d$ is the weighted degree, i.e. $d(v):=\sum_{u\in N(v)}^{}w(u,v)$.
- **Remark**: As the Markov chain is finite state, it has a stationary distribution, e.g. $\pi:=\frac{d}{1^\top d}$. 
---
##### Properties
> [!lemma] Lemma 1 (Basic Properties of Random Walks)
> For a graph $G$ we have that: 
> 1. $W=AD^{-1}$.
> 2. a stationary distribution for $W$ is also a stationary distribution for $\tilde{W}$.
> 3. $\tilde{W}=I-\frac{1}{2}D^{1/2}ND^{-1/2}$ where $N:= D^{-1/2}LD^{-1/2}$ is the normalized Laplacian.
> 4. $\tilde{W}$ admits $1-\frac{1}{2}\lambda_{i}(N)$ as an eigenvalue with eigenvector $D^{1/2}\psi_{i}$ where $\psi_{i}$ is the orthogonal eigenvector w.r.t. $\lambda_{i}(N)$.
> 5. $\text{Spec}(\tilde{W})\subseteq [0,1]$

> [!proof]-
> We have:
> 1. Notice that: $$(AD^{-1})_{vu}=\sum_{w\in V}^{}A_{vw}D^{-1}_{wu}=A_{vu}D_{uu}^{-1}\mathbb{1}_{u\in N(v)}=\frac{w(u,v)}{d(u)}\cdot \mathbb{1}_{u\in N(v)}$$
> 2. Let $\pi$ be a stationary distribution for $W$. Then, $$\tilde{W}\pi=\frac{1}{2}(\pi+W\pi)=\frac{1}{2}(2\pi)=\pi$$
> 3. We have that $N=D^{-1/2}LD^{-1/2}=I-D^{-1/2}AD^{-1/2}$. Hence, $$\tilde{W}=\frac{1}{2}I+\frac{1}{2}AD^{-1}=\frac{1}{2}I+\frac{1}{2}D^{1/2}D^{-1/2}AD^{-1/2}D^{-1/2}=\frac{1}{2}I+\frac{1}{2}D^{1/2}(I-N)D^{-1/2}$$This shows the statement.
> 4. We have: $$\tilde{W}D^{1/2}\psi_{i}=\left( D^{1/2}-\frac{1}{2}D^{1/2}N \right)\psi_{i}=\left( D^{1/2}-\frac{1}{2}\lambda_{i}(N)D^{1/2} \right)\psi_{i}=\left( 1-\frac{1}{2}\lambda_{i}(N)\right)D^{1/2}\psi_{i}$$
> 5. As $L\preceq 2D$ we have $N\preceq 2I$. Hence, $\text{Spec}(N)\subseteq[0,2]$. The rest follows from 4. 

---
> [!lemma] Proposition 2 (Eigendecomposition of Lazy Random Walk Matrix)
> Let $p\in\Delta(V)$. TFAE:
> 1. $p=\sum_{i=1}^{n}\alpha_{i}D^{1/2}\psi_{i}$
> 2. $\psi_{i}^\top D^{-1/2}p=\alpha_{i}$ for all $i\in[n]$.


> [!proof]-
> We have that:
> 1. Observe that: $$p=\sum_{i=1}^{n}\alpha_{i}D^{1/2}\psi_{i}\iff D^{-1/2}p=\sum_{i=1}^{n}\alpha_{i}\psi_{i}$$Now, for any $i\in[n]$, $\psi_{i}^\top D^{-1/2}p=\alpha_{i}\psi_{i}^\top \psi_{i}=\alpha_{i}$. Conversely, $$\sum_{i=1}^{n}\alpha_{i}\psi_{i}=\sum_{i=1}^{n}\psi_{i}^\top D^{-1/2}p \psi_{i}=\sum_{i=1}^{n}\braket{ D^{-1/2}p , \psi_{i} } \psi_{i}=D^{-1/2}p$$

- **Corollary**: $p_{t}=\sum_{i=1}^{n}\alpha_{i}\left( 1-\frac{\lambda_{i}(N)}{2} \right)^t D^{1/2}\psi_{i}$ where $p_{0}=\sum_{i=1}^{n}\alpha_{i}D^{1/2}\psi_{i}$.
---
> [!lemma] Theorem 3 (Rate of Convergence of Lazy Random Walk)
> Let $G=(V,E,w)$ be a connected graph. For any $u,v\in V$ and initial distribution $1_{u}$, we have:$$\left| p_{t}(v)-\pi(v) \right| \leq e^{-\lambda_{2}(N)t / 2}\cdot \sqrt{ \frac{d(v)}{d(u)} }$$where $p_{t}:=\tilde{W}^t 1_{u}$

> [!proof]-
> We have that: $$ p_{t}(v)-\pi(v) =1_{v}^\top \left( \sum_{i=2}^{n}\alpha_{i}\left( 1-\frac{\lambda_{i}(N)}{2} \right)^t D^{1/2}\psi_{i} \right) \leq \left( 1-\frac{\lambda_{2}(N)}{2} \right) ^t \sum_{i=2}^{n}\alpha_{i}1_{v}^\top D^{1/2} \psi_{i}$$Hence, by Cauchy-Schwarz, $$\left| p_{t}(v)-\pi(v) \right| \leq\left( 1-\frac{\lambda_{2}(N)}{2} \right)^t \sqrt{ \left( \sum_{i=2}^{n}\alpha_{i}^{2} \right)\left( \sum_{i=2}^{n}(1_{v}^\top D^{1/2}\psi_{i})^{2} \right)  }$$where: $$\sum_{i=2}^{n}\alpha_{i}^{2}=\sum_{i=2}^{n}(\psi_{i}^\top D^{-1/2}1_{u})^{2}\leq \left\| D^{-1/2}1_{u} \right\|^{2}_{2} =1 / d(u)$$and $$\sum_{i=2}^{n}(1_{v}^\top D^{1/2}\psi_{i})^{2}\leq \sum_{i=1}^{n}(\psi_{i}^\top D^{1/2}1_{v})^{2}=\left\| D^{1/2}1_{v} \right\| ^{2}_{2}=d(v)$$This proves the statement.
- **Corollary**: If $G$ is unweighted, i.e. $w\equiv 1$, $\left\| p_{t}-\pi \right\|_{\infty}\leq e^{-\lambda_{2}(N)t /2}\sqrt{ n }$
---