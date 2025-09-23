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
> Let $\sigma:\mathbb{R}\to \mathbb{R}$ be a continuous sigmoidal function. Then, $$\overline{\braket{ \sigma(\braket{ y , \cdot  } +\theta):y\in \mathbb{R}^n,\theta\in \mathbb{R} } }=(C(I_{n}),\|\cdot \|_{\infty})$$

> [!proof]+
> Let $K_{y,\theta}:\mathbb{R}^n\to \mathbb{R},x\mapsto \sigma(\braket{ y , x }+\theta)$. 
> 1. **Claim 1: If $\sigma$ is continuous and discriminatory, then: $$U(\sigma):=\text{span}(\{ K_{y,\theta}:y\in \mathbb{R}^n,\theta\in \mathbb{R} \})$$is dense in $C(I_{n})$.** 
>    
>    Let $L\in C(I_{n})^{*}$ with $L|_{U(\sigma)}=0$. By Riesz representation, there exists a unique $\mu\in M(I_{n})$ with $L(f)=\int_{I_{n}} f \, d\mu$ for all $f\in C(I_{n})$. Then, $$0=L(K_{y,\theta})=\int_{I_{n}}\sigma(\braket{ y , x } +\theta)  \, d\mu(x) $$Hence, as $\sigma$ is discriminatory, $\mu=0$ and $L=0$. The rest follows by Corollary of Corollary 1.
> 2. **Claim 2**: **Every sigmoidal function is discriminatory**.
>    Let $\sigma:\mathbb{R}\to \mathbb{R}$ be sigmoidal and $\mu\in M(I_{n})$. Assume that  $$\int_{I_{n}} \sigma(\braket{ y , x } +\theta) \, d\mu(x)=0,\quad \forall y\in \mathbb{R}^n,\theta\in \mathbb{R} $$Let $0\neq y_{0}\in \mathbb{R}^n$. Fix $\theta,\varphi\in \mathbb{R}$. We now define a function: $$\gamma:I_{n}\to \mathbb{R},\quad x\mapsto\begin{cases}1&\braket{ y_{0} , x }+\theta>0 \\\sigma(\varphi)&\braket{ y_{0} , x }+\theta=0\\0&\braket{ y_{0} , x }+\theta<0\end{cases}$$and set $\sigma_{\lambda}:x\mapsto \sigma(\lambda (\braket{ y_{0} , x }+\theta)+\varphi)$. Then, as $\lambda\to \infty$, we have that $\sigma_{\lambda}\to \gamma$. Moreover, as $\sigma$ is bounded by assumption, we can use Lebesgue theorem to have: $$\int_{I_{n}} \gamma \, d\mu=\lim_{ \lambda \to \infty } \int_{I_{n}} \sigma_{\lambda} \, d\mu  =0$$
>    Let now $\Pi_{y_{0},\theta},H_{y_{0},\theta}$ be the hyperplane defined by: $$\Pi_{y_{0},\theta}=\{ x\in \mathbb{R}^n: \braket{ y_{0} , x } +\theta=0 \},\quad H_{y_{0},\theta}:=\{ x\in \mathbb{R}^n : \braket{ y_{0} , x } +\theta>0\}$$Then, $$0=\int_{I_{n}}\gamma  \, d\mu=\sigma(\varphi)\mu(\Pi_{y_{0},\theta}\cap I_{n})+\mu(H_{y_{0},\theta}\cap I_{n}),\quad \forall \varphi,\theta\in \mathbb{R} $$Further, by sigmoidality, we have that $\mu(\Pi_{y_{0},\theta}\cap I_{n})=\mu(H_{y_{0},\theta}\cap I_{n})=0$. For $\theta$ large enough, we have that $I_{n}\subseteq H_{y_{0},\theta}$ and we have that $\mu(I_{n})=0.$
>    
>    Now, let us define: $$\lambda(A):=\mu(\{ x\in  I_{n},\braket{ y_{0} , x } \in A \})$$Then, by constructon $\lambda$ is a signed Borel measure on $\mathbb{R}$. Furthermore, $$\lambda([\theta,\infty))=\mu(\{ x\in I_{n}:\braket{ y_{0} , x } \geq \theta \})=\mu(\Pi_{y_{0},-\theta}\cap I_{n})+\mu(H_{y_{0},-\theta}\cap I_{n})=0$$Similarly, $\lambda((\theta,\infty))=0$ and $\lambda(A)=0$ for all Borel $A\subseteq \mathbb{R}$.
>    
>    Next, let $F:L^\infty(\mathbb{R})\to \mathbb{R}$ be a functional defined as: $$F(h):=\int_{I_{n}}^{} h(\braket{ y_{0} , x } ) \, d\mu(x) $$Then $F$ is linear and we have that: $$F(1_{A})=\int_{I_{n}}^{} 1_{A}(\braket{ y_{0} , x } ) \, d\mu(x)=\lambda(A)=0 $$for any Borel $A\subseteq \mathbb{R}$. By linearity, $F(s)=0$ for all simple functions $s$. As simple functions are dense, we have that $F=0$. In particular, $$\int_{I_{n}}\sin(\braket{ y_{0} , x } )  \, d\mu(x) = 0,\quad \int_{I_{n}}\cos(\braket{ y_{0} , x } )  \, d\mu(x) $$as $\sin,\cos\in L^\infty(\mathbb{R})$. Therefore, $$\int_{I_{n}}e^{i\braket{ y_{0} , x } }  \, d\mu(x) =0,\quad \forall y_{0}\in \mathbb{R}^n$$where for $y_{0}=0$ it holds as $\mu(I_{n})=0$. In other words, the Fourier-Stieltjes form of $\mu$ is zero and hence $\mu=0$.
