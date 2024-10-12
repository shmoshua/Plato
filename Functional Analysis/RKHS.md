#Definition #FunctionalAnalysis 

> [!definition]
> Let $X$ be a set. 
> 1. the ***reproducing kernel Hilbert space (RKHS)*** is a [[Hilbert space]] $\mathcal{H}$ of functions $f:X\to \mathbb{R}$ s.t. $\text{ev}_{x}:\mathcal{H}\to \mathbb{R},f\mapsto f(x)\in \mathcal{H}^{*}$ for all $x\in X$. 


- **Related definition**: For $f(x)=\sum_{i=1}^{n}\alpha_{i}k(x,x_{i})$ and $g(x)=\sum_{j=1}^{m}\beta_{j}k(x,x'_{i})$, the RKHS inner product is given by: $$\braket{ f ,g  }_{k}:=\sum_{i=1}^{n}\sum_{j=1}^{m}\alpha_{i}\beta_{j}k(x_{i},x'_{j}) $$

---
##### Properties
> [!lemma] Proposition 1
> Let $\mathcal{H}$ be a RKHS. 
> 1. For $\{ f_{n} \}_{n}\subseteq \mathcal{H}$ and $f\in \mathcal{H}$, convergence in $\mathcal{H}$ implies pointwise convergence, i.e.: $$\lim_{ n \to \infty } \left\| f_{n}-f \right\| =0\quad \implies\quad \lim_{ n \to \infty } \left| f_{n}(x)-f(x) \right|=0,\quad \forall x\in X $$

> [!proof]-
> We have that:
> 1. For any $x\in X$, $$\left| f_{n}(x)-f(x) \right| =\left| \text{ev}_{x}(f_{n}-f) \right|\leq \left\| \text{ev}_{x} \right\| \left\| f_{n}-f \right\| _{\mathcal{H}} $$where $\left\| \text{ev}_{x} \right\|$ is bounded by the definition of RKHS.
---
> [!lemma] Theorem 2 (Existence of Reproducing Kernels)
> Let $\mathcal{H}$ be a Hilbert space. TFAE:
> 1. $\mathcal{H}$ is a RKHS.
> 2. $\mathcal{H}$ has a [[Kernel|reproducing kernel]].

> [!proof]-
> We have:
> 1. (1=>2): Let $\mathcal{H}$ be a RKHS. Then, $\text{ev}_{x}\in \mathcal{H}^{*}$ for all $x\in X$ and there exists $f_{x}\in\mathcal{H}$ s.t. $$\text{ev}_{x}(f)=\braket{ f , f_{x} },\quad \forall f\in \mathcal{H}$$Then, we can define a kernel $k: X\times X\to \mathbb{K}$ as follows: $$k(x,y)=f_{y}(x)$$As we have that $k(x,y)=\braket{ k(\cdot,x ) , k(\cdot,y ) } =\braket{ f_{x} , f_{y} }$, $k$ is a SPsD kernel. It is easy to check that $k$ is reproducing $\mathcal{H}$. 
>    
> 2. (2=>1): Let $k:X\times X\to \mathbb{R}$ be a reproducing kernel of $\mathcal{H}$. Then, we have that: $$\left| \text{ev}_{x}(f) \right| =\left| f(x) \right| =\left| \braket{ f , k(\cdot,x ) }_{\mathcal{H}}  \right|\leq \left\| f \right\| _{\mathcal{H}}\cdot \left\| k(\cdot,x ) \right\| _{\mathcal{H}}=\left\| f_{\mathcal{H}} \right\| \cdot \sqrt{ k(x,x) } $$ which is well-defined as $k(x,x)\geq 0$. Hence, $\text{ev}_{x}$ is continuous.
---
> [!lemma] Theorem 3 (Moore-Aronszajn)
> Let $k:X\times X\to \mathbb{R}$ be an SPsD kernel. Then,
> 1. $\mathcal{H}_{0}:=\text{Span}(\{ k(\cdot,x) \}_{x\in X})$ is an [[inner product space]] with: $$\left\langle \sum_{i=1}^n\alpha_{i}k(\cdot ,x_{i}) ,  \sum_{j=1}^{m}\beta_{j}k(\cdot ,y_{j})\right\rangle :=\sum_{i=1}^{n}\sum_{j=1}^{m}\alpha_{i}\beta_{j}k(x_{i},y_{j})$$
> 2. $\mathcal{H}:=\overline{\mathcal{H}_{0}}$ is a RKHS with $k$ as the reproducing kernel.

> [!proof]-
> We have that:
> 1. **Claim 1: $\braket{ f , k(\cdot,x) }_{\mathcal{H}_{0}}=f(x)$** 
> 	For $f:=\sum_{i=1}^{n}\alpha_{i}k(\cdot,x_{i})$, we have: $$\braket{ f , k(\cdot ,x) } _{\mathcal{H}_{0}}=\sum_{i=1}^{n}\alpha_{i}k(x_{i},x)=\sum_{i=1}^{n}\alpha_{i}k(x,x_{i})=f(x)$$
> 2. **Claim 2: The inner product is well-defined**.
>    Linearity and symmetry are clear. We have that for $f:=\sum_{i=1}^{n}\alpha_{i}k(\cdot,x_{i})$, $$\braket{ f , f } =\sum_{i,j=1}^{n}\alpha_{i}\alpha_{j}k(x_{i},x_{j})\geq 0$$Lastly, we have that if $\braket{ f , f }=0$, for all $x\in X$, $$\left| f(x) \right| =\left| \braket{ f , k(\cdot ,x) } \right| \leq \left\| f \right\| _{\mathcal{H}_{0} }\sqrt{ k(x,x) } =0$$
> 3. **Claim 3: $\text{ev}_{x}:\mathcal{H}_{0}\to \mathbb{R}$ is continuous** 
>    We have that: $$\left| \text{ev}_{x}(f)-\text{ev}_{x}(g) \right| =\left| f(x)-g(x) \right| =\left| \braket{ f-g , k(\cdot ,x) }  \right| \leq \left\| f-g \right\| \cdot \sqrt{ k(x,x) }$$
> 4. **Claim 4: For every Cauchy sequence $\{ f_{n} \}_{n}\subseteq \mathcal{H}_{0}$ converging to 0 pointwisely, it does so in $\mathcal{H}_{0}$ norm as well.**
>    Let $\{ f_{n} \}_{n}\subseteq \mathcal{H}_{0}$ be such Cauchy sequence. As it is Cauchy, there exists $A>0$ s.t. $\left\| f_{n} \right\|<A$. For $\varepsilon>0$, let $N\in \mathbb{N}$ s.t. $\left\| f_{n}-f_{m} \right\|\leq \varepsilon / 2A$ for all $n,m\geq \mathbb{N}$. 
>    
>    Let $f_{N}=\sum_{i=1}^{n}\alpha_{i}k(\cdot,x_{i})$ and define $M\in \mathbb{N}$ s.t. $\left| f_{n}(x_{i}) \right|< \frac{\varepsilon}{2n \left| \alpha_{i} \right|}$ for all $i\in[n]$. Then, for $n\geq N,M$, $$\begin{align}\left\| f_{n} \right\| ^{2}&\leq \left| \braket{ f_{n}-f_{N} , f_{n} }  \right| +\left| \braket{ f_{N} , f_{n} }  \right| \\&\leq \left\| f_{n}-f_{N} \right\| \left\| f_{n} \right\| +\sum_{i=1}^{n}\left| \alpha_{i}f_{n}(x_{i}) \right| \\&\leq \varepsilon\end{align}$$
> 5. **Claim 5: $k$ is the reproducing kernel of $\mathcal{H}$**
>    For $f\in\mathcal{H}$, we have that: $$\begin{align} \braket{ f , k(\cdot ,x) } &=\lim_{ n \to \infty } \braket{ f_{n} , k(\cdot ,x) } =\lim_{ n \to \infty } f_{n}(x)=f(x)\end{align}$$
---
