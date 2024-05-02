#Definition #FunctionalAnalysis 

> [!definition]
> Let $\lambda$ be the [[Lebesgue Measure]] on $\mathbb{R}$ restricted to $[0,1]$ and $L^1([0,1],\lambda)$. The ***Volterra algebra*** is the algebra $L^1([0,1])$ with multiplication defined as [[Convolution (Rn)|convolution]]:
> $$(f*g)(x)=\int_{0}^{x} f(x-t)g(t) \, dt $$
---
##### Properties
> [!lemma] Proposition 1
> The Volterra algebra is a commutative non-unital [[Banach Algebra]].

> [!proof]-
> We have:
> 1. **The Volterra algebra is Banach**: $L^1([0,1])$ is a Banach space from [[Lp Space|Theorem 7]] and 
> 	$$\begin{align}\left\| f*g \right\| _{1}&\leq \int_{0}^{1}\int_{0}^{x} \left| f(x-t) \right| \left| g(t) \right|  \, dt   \, dx \\&=\int_{0}^{1} \left( \int_{t}^{1} \left| f(x-t) \right|  \, dx  \right) \left| g(t) \right|  \, dt\\&\leq\int_{0}^{1} \left( \int_{0}^{1} \left| f(y) \right|  \, dy  \right) \left| g(t) \right|  \, dt\\&=\left\| f \right\| _{1}\left\| g \right\| _{1}\end{align}$$
> 2. **The Volterra algebra is commutative**:$$(f*g)(x)=\int_{0}^{x} f(x-t)g(t) \, dt=\int_{0}^{x} f(y)g(x-y) \, dy =(g*f)(x) $$
> 3. **The Volterra algebra is non-unital**: 
> 	Assume the unit $\delta\in L^1([0,1])$ exists. Using [[Laplace Transform]], we get that: 
> 	$$\mathcal{L}(f*\delta)=\mathcal{L}(f)\cdot \mathcal{L}(\delta)$$for all $f\in L^1([0,1])$. 
---
> [!lemma] Proposition 2
> The [[Guelfand Spectrum]] of the Volterra algebra is empty.