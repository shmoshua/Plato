#Definition #FunctionalAnalysis 

> [!definition]
> Let $X$ be a set. 
> 1. the ***reproducing kernel Hilbert space (RKHS)*** is a [[Hilbert space]] $\mathcal{H}$ of functions $f:X\to \mathbb{K}$ s.t. $\text{ev}_{x}:\mathcal{H}\to \mathbb{K},f\mapsto f(x)\in \mathcal{H}^{*}$ for all $x\in X$. 


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

> [!proof]+
> We have:
> 1. (1=>2): Let $\mathcal{H}$ be a RKHS. Then, $\text{ev}_{x}\in \mathcal{H}^{*}$ for all $x\in X$ and there exists $f_{x}\in\mathcal{H}$ s.t. $$\text{ev}_{x}(f)=\braket{ f , f_{x} },\quad \forall f\in \mathcal{H}$$Then, we can define a kernel $k: X\times X\to \mathbb{K}$ as follows: $$k(x,y)=f_{x}(y)$$We first show that this is a SPsD kernel. For symmetry, we have that: $$k(x,y)$$
>    
> 2. (2=>1): Let $k:X\times X\to \mathbb{K}$ be a reproducing kernel of $\mathcal{H}$. Then, we have that: $$\left| \text{ev}_{x}(f) \right| =\left| f(x) \right| =\left| \braket{ f , k(x,\cdot ) }_{\mathcal{H}}  \right|\leq \left\| f \right\| _{\mathcal{H}}\cdot \left\| k(x,\cdot ) \right\| _{\mathcal{H}}=\left\| f_{\mathcal{H}} \right\| \cdot \sqrt{ k(x,x) } $$ which is well-defined as $k(x,x)\geq 0$. Hence, $\text{ev}_{x}$ is continuous.