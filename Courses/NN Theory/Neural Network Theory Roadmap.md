#Roadmap #MachineLearning 

### 1. Sigmoidal Function Approximation

> [!definition]
> A function $\sigma:\mathbb{R} \to \mathbb{R}$ is called ***discriminatory*** if:
> 1. for any signed Borel measure $\mu\in M(I_{n})$, $$\int_{I_{n}} \sigma(\braket{ y , x } +\theta)  \, d\mu(x)=0, \forall y\in \mathbb{R}^n,\theta\in \mathbb{R}\quad\implies\quad \mu=0 $$
---
![[Bounded Linear Map#^76d1d2]]
![[Bounded Linear Map#^5b1d9c|p]]

---
> [!lemma] Corollary 1
> Let $M$ be a subspace of $(X,\|\cdot\|)$. Then, for $x_{0}\in X$, TFAE:
> 1. $x_{0}\in \overline{M}$
> 2. there is no $F\in \mathcal{B}(X)$ s.t. $F|_{M}=0$ and $F(x_{0})\neq 0$.

> [!proof]-
> We have that:
> 1. (1=>2): Assume we have such $F$. Then, as $F$ is continuous, we have that: $$0\neq F(x_{0})=F(\lim_{ n \to \infty } x_{n})=\lim_{ n \to \infty } F(x_{n})=0$$which is a contradiction.
> 2. (2=>1): Let $x_{0}\notin \overline{M}$. Let $M':=M+\braket{ x_{0} }$. Further, we define: $$f:M'\to \mathbb{R}, \quad x+\lambda x_{0}\mapsto \lambda$$Then, $f$ is linear. Now we have that there exists $\delta>0$ s.t. $\delta< d(x_{0},M)$. Now, $$\delta \left| f(x+\lambda x_{0}) \right| =\delta \left| \lambda \right| <\left| \lambda \right| \left\| -\lambda ^{-1}x-x_{0} \right\| \leq \left\| x+\lambda x_{0} \right\| $$Hence, $\left\| f \right\|\leq \delta ^{-1}$. Therefore, by Hahn-Banach $f$ can be extended to $F\in \mathcal{B}(X)$ where $F|_{M}=0$ and $F(x_{0})=1$, which is a contradiction.
- **Corollary**: If every $F\in \mathcal{B}(X)$ with $F|_{M}=0$ has that $F=0$, then $\overline{M}=X$.
---
> [!lemma] Theorem (Riesz Representation)
> For any $L\in C(I_{n})^{*}$, there exists a unique $\mu\in M(I_{n})$ s.t. $$L(f)=\int_{I_{n}}^{} f \, d\mu,\quad \forall f\in C(I_{n}) $$

---
#### 1.1 Sigmoidal Function Are Dense in Continuous Functions
> [!definition] 
> A bounded measurable function $\sigma:\mathbb{R}\to \mathbb{R}$ is ***sigmoidal*** if
> $$\sigma(x)\to \begin{cases}1&x\to \infty\\0&x\to -\infty\end{cases}$$

---
> [!lemma] Theorem 1 (Density of Sigmoidal Function)
> Let $\sigma:\mathbb{R}\to \mathbb{R}$ be a sigmoidal function. Then, $$\overline{\braket{ \sigma(\braket{ y , \cdot  } +\theta):y\in \mathbb{R}^n,\theta\in \mathbb{R} } }=(C(I_{n}),\|\cdot \|_{\infty})$$

> [!proof]+
> Let $K_{y,\theta}:\mathbb{R}^n\to \mathbb{R},x\mapsto \sigma(\braket{ y , x }+\theta)$. 
> 1. **Claim 1: If $\sigma$ is continuous and discriminatory, then: $$U(\sigma):=\text{span}(\{ K_{y,\theta}:y\in \mathbb{R}^n,\theta\in \mathbb{R} \})$$is dense in $C(I_{n})$.** 
>    
>    Let $L\in C(I_{n})^{*}$ with $L|_{U(\sigma)}=0$. By Riesz representation, there exists a unique $\mu\in M(I_{n})$ with $L(f)=\int_{I_{n}} f \, d\mu$ for all $f\in C(I_{n})$. Then, $$0=L(K_{y,\theta})=\int_{I_{n}}\sigma(\braket{ y , x } +\theta)  \, d\mu(x)= $$
