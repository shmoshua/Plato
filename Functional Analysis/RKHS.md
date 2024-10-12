#Definition #FunctionalAnalysis 

> [!definition]
> Let $X$ be a set. 
> 1. the ***reproducing kernel Hilbert space (RKHS)*** is a Hilbert space $\mathcal{H}$ of functions $f:X\to \mathbb{K}$ s.t. $\text{ev}_{x}:\mathcal{H}\to \mathbb{K},f\mapsto f(x)$ is continuous for all $x\in X$. 


- **Related definition**: For $f(x)=\sum_{i=1}^{n}\alpha_{i}k(x,x_{i})$ and $g(x)=\sum_{j=1}^{m}\beta_{j}k(x,x'_{i})$, the RKHS inner product is given by: $$\braket{ f ,g  }_{k}:=\sum_{i=1}^{n}\sum_{j=1}^{m}\alpha_{i}\beta_{j}k(x_{i},x'_{j}) $$

---
##### Properties
> [!lemma] Proposition 1
> Let $\mathcal{H}$ be a RKHS. 
> 1. For $\{ f_{n} \}_{n}\subseteq \mathcal{H}$ and $f\in \mathcal{H}$, convergence in $\mathcal{H}$ implies pointwise convergence, i.e.: $$\lim_{ n \to \infty } \left\| f_{n}-f \right\| =0\quad \implies\quad \lim_{ n \to \infty } \left| f_{n}(x)-f(x) \right|=0,\quad \forall x\in X $$

> [!proof]+
> We have that:
> 1. For any $x\in X$, $$\left| f_{n}(x)-f(x) \right| =\left| \text{ev}_{x}(f_{n}-f) \right|\leq \left\| \text{ev}_{x} \right\| \left\| f_{n}-f \right\| _{\mathcal{H}} $$where $\left\| \text{ev}_{x} \right\|$ is bounded by the definition of RKHS.