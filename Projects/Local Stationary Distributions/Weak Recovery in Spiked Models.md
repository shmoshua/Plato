> [!outlook] Setup
> Let $M:= W+\lambda vv^\top$ where $\left\| W \right\|\leq 1$ and $v\in \left\{  \pm \frac{1}{\sqrt{ n }}  \right\}^n$. 
---
> [!lemma] Theorem
> Consider the following setting for $M:= W + \lambda vv^\top$ where
> 1. $\kappa I \leq W \leq (1-\kappa)I$
> 2. $v\in \{ \pm 1 / \sqrt{ n } \}^n$. 
> 3. $P$ is the Glauber dynamics for $\mu_{M}\in \Delta(\{ \pm 1 \}^n)$ where: $$\mu_{M}(x)\propto \exp \left( \frac{1}{2}x^\top M x \right) $$
> 4. $x_{0}\in \{ \pm 1 \}^n$.
> 
> Then, there exists a large enough constant $\lambda > 0$ s.t. for $T:= \tilde{ \Theta}(n^5)$ and $t\sim[0,T]$: $$\mathbb{E}_{x \sim P^t \delta_{x_{0}}}[\left| \braket{ x , v }  \right| ]\geq \left( \kappa \exp \left( -\frac{1}{\kappa} \right)  -o(1)\right)\sqrt{ n } $$

---
##### 1. Restricted Gaussian Dynamics (RGD)
> [!definition]
> In the above setting, 
> 1. ***RGD*** is a [[Markov chain]] on $\{ \pm 1 \}^n$ where the transition is given by:
> 	1. sample $g\sim \mathcal{N}(0,1)$ and let $z:=(\lambda \braket{ v , x }+\sqrt{ \lambda }g)v$
> 	2. sample $y$ from the Gibbs distribution $\mu_{W,z}$. 
---
> [!lemma] Proposition 1
> We have that: 
> 1. $\mu_{M}$ admits a measure decomposition $\mu_{M}=\mathbb{E}_{z\sim \rho}\mu_{W,z}$ and
> 2. RGD is the associated Markov chain to the decomposition.

> [!proof]-
> We have that:
> 1. Let $\rho:= \mathcal{N}(z;0,\lambda v v^\top)$. Then, we can write $z=tv$ where $t\sim \mathcal{N}(0,\lambda)$. Hence,$$\begin{aligned}\int_{\Omega}\mu_{W,z}(x)  \, d\rho(z)&\propto\int_{\Omega}\exp \left( \frac{1}{2}x^\top Wx +\braket{ z , x }  \right)   d\rho(z) \\&\propto \exp \left( \frac{1}{2}x^\top Wx \right) \int_{\mathbb{R}}\exp \left(t\braket{ v, x }  \right)\exp \left( -\frac{t^{2}}{2\lambda} \right)   dt\\&\propto \exp \left( \frac{1}{2}x^\top Wx \right) \int_{\mathbb{R}}\exp \left( -\frac{t^{2}}{2\lambda}+t \braket{ v , x } \right)   dt \\&\propto \exp \left( \frac{1}{2}x^\top Wx \right) \int_{\mathbb{R}}\exp \left( -\frac{(t-\lambda\braket{ v , x } )^{2}}{2\lambda}+ \frac{\lambda\braket{ v , x } ^{2}}{2}\right)   dt\\&\propto \exp \left( \frac{1}{2}x^\top Mx  \right) \int_{\mathbb{R}}\exp \left( -\frac{(t-\lambda\braket{ v , x } )^{2}}{2\lambda}\right)dt \\&\propto \exp \left( \frac{1}{2}x^\top Mx  \right) \end{aligned}$$
> 2. Then, we have: $$\begin{aligned}p(z,x)&=p(x|z)\rho(z)\\&\propto \exp \left( \frac{1}{2}x^\top W x+t\braket{ v , x }  \right)\exp \left( -\frac{t^{2}}{2\lambda} \right)  \end{aligned}$$Hence, $$\begin{aligned}p(t|x)&\propto \exp \left( -\frac{t^{2}}{2\lambda}+t\braket{ v , x }  \right)\\&\propto\exp \left( -\frac{(t-\lambda\braket{ v , x } ) ^{2}}{2\lambda}\right)  \end{aligned}$$and $t|x\sim \mathcal{N}(\lambda \braket{ v , x },\lambda)$. Hence, $z|x\sim \mathcal{N}(\lambda \braket{ v , x }v,\lambda v v^\top)$
---
##### 2. Entropic Stability and Variance Conservation
> [!definition] 
> A measure decomposition $\pi=(\rho,\pi_{z})$ has ***conservation of variance*** with $C_{\text{var}}\in[0,1]$, 
> 1. if for any $f:\Omega\to \mathbb{R}$, $$\mathbb{E}_{z\sim\rho}\text{Var}_{\pi_{z}}(f)\geq C_{\text{var}}\cdot  \text{Var}_{\pi}(f)$$
- **Remark**: By law of total variance,$$\text{Var}_{\pi}(f)=\mathbb{E}_{z\sim \rho}\text{Var}_{\pi_{z}}(f)+\text{Var}_{z \sim \rho}\mathbb{E}_{\pi_{z}}[f]\geq \mathbb{E}_{z\sim \rho}\text{Var}_{\pi_{z}}(f) $$
---
> [!definition]
> For a measure $\pi$ on $\Omega \subseteq \mathbb{R}^n$ and vector $v\in \mathbb{R}^n$, 
> 1. the ***tilted measure*** $\mathcal{T}_{v}\pi$ on $\Omega$ is defined s.t. $$\frac{d\mathcal{T}_{v}\pi(x)}{d\pi(x)}\propto \exp(\braket{ v , x } )$$
---
> [!h] Example 1
> We have that:
> 1. For $\pi=\mathcal{N}(\mu,\Sigma)$, $\mathcal{T}_{v}\pi=\mathcal{N}(\mu+\Sigma v,\Sigma)$.

> [!proof]-
> We have that:
> 1. $$\begin{aligned}d(\mathcal{T}_{v}\pi)(x)&\propto \exp(\braket{ v , x } )\exp \left( -\frac{x^\top x}{2} \right)\\&=\exp \left(-\frac{x^\top x}{2}+\braket{ v , x }  \right)\\&\propto\exp \left( -\frac{(x-v)^\top(x-v)}{2} \right)   \end{aligned}$$
---
> [!definition] 
> Let $\Omega \subseteq \mathbb{R}^n$ and $\psi:\mathbb{R}^n \times \mathbb{R}^n\to \mathbb{R}_{\geq 0}$.
> 1. for $\alpha>0$, a measure $\pi$ on $\Omega$ is ***$\alpha$-entropically stable*** w.r.t. $\psi$ if for all $v\in \mathbb{R}^n$: $$\psi(\mathbb{E}_{x\sim T_{v}\pi}[x],\mathbb{E}_{x\sim \pi}[x])\leq \alpha \cdot  D(T_{v}\pi\| \pi)$$
---
> [!h] Example 1
> We have that:
> 1. $\pi=\mathcal{N}(\mu,\Sigma)$ is $2\lambda_{\text{max}}(\Sigma)$-entropically stable w.r.t. $(x,y)\mapsto \|x-y\|^{2}$.

> [!proof]-
> We have that for $\pi=\mathcal{N}(\mu,\Sigma)$, $T_{v}\pi=\mathcal{N}(\mu+\Sigma v,\Sigma)$. Then, $$D(T_{v}\pi\|\pi)=\frac{1}{2} (\Sigma v)^\top\Sigma ^{-1}\Sigma v=\frac{1}{2}v^\top \Sigma v $$If we take $\psi:(x,y)\mapsto \|x-y\|^{2}$, then: $$\begin{aligned}\psi(\mathbb{E}_{x\sim T_{v}\pi}[x],\mathbb{E}_{x\sim \pi}[x])&=\left\| \mu+\Sigma v-\mu \right\|^{2}=\left\| \Sigma v \right\| ^{2}=v^\top \Sigma^{2} v \end{aligned}$$Hence, $\alpha_{\text{Ent}}\leq 2\lambda_{\text{max}}(\Sigma)$.
---
> [!lemma] Theorem 1
> Let $\kappa I \leq W \leq (1-\kappa) I$ and $h\in \mathbb{R}^n$ be arbitrary. Then, there exists a mixture: $$\mu_{W,h}=\mathbb{E}_{z\sim\rho}[\mu_{0,Wz+h}]$$ s.t.
> 1. $\mu_{W,h}$ is $\frac{1}{\kappa}$-entropically stable w.r.t. $(x,y)\mapsto \|x-y\|^{2}$
> 2. $C_{\text{var}}(\rho,\mu_{0,W z+h})\geq \exp \left( -1/\kappa \right)$
> 3. $C_{\text{MLSI}}(\mu_{W,h})\geq \frac{1}{n} \frac{1}{1-\kappa}$

> [!proof]+
> We have that: $$\int i=1 \, dsnefnefiwndkfmmdmdmfmff $$
> I can't do this anymore. 
