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

> [!proof]+
> We have that:
> 1. Let $\rho:= \mathcal{N}(z;0,\lambda v v^\top)$. Then, we can write $z=tv$ where $t\sim \mathcal{N}(0,\lambda)$. Hence,$$\begin{aligned}\int_{\Omega}\mu_{W,z}(x)  \, d\rho(z)&\propto\int_{\Omega}\exp \left( \frac{1}{2}x^\top Wx +\braket{ z , x }  \right)   d\rho(z) \\&\propto \exp \left( \frac{1}{2}x^\top Wx \right) \int_{\mathbb{R}}\exp \left(t\braket{ v, x }  \right)\exp \left( -\frac{t^{2}}{2\lambda} \right)   dt\\&\propto \exp \left( \frac{1}{2}x^\top Wx \right) \int_{\mathbb{R}}\exp \left( -\frac{t^{2}}{2\lambda}+t \braket{ v , x } \right)   dt \\&\propto \exp \left( \frac{1}{2}x^\top Wx \right) \int_{\mathbb{R}}\exp \left( -\frac{(t-\lambda\braket{ v , x } )^{2}}{2\lambda}+ \frac{\lambda\braket{ v , x } ^{2}}{2}\right)   dt\\&\propto \exp \left( \frac{1}{2}x^\top Mx  \right) \int_{\mathbb{R}}\exp \left( -\frac{(t-\lambda\braket{ v , x } )^{2}}{2\lambda}\right)dt \\&\propto \exp \left( \frac{1}{2}x^\top Mx  \right) \end{aligned}$$
> 2. Then, we have: $$p(z,x)=\rho(x|z)\rho(z)$$