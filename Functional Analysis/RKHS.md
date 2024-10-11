#Definition #ML 

> [!definition]
> Let $X$ be a set and $k:X\times X\to \mathbb{R}$ a SPsD [[kernel]]. Then,
> 1. the ***reproducing kernel Hilbert space (RKHS)*** of $k$ is given as: $$\mathcal{H}_{k}(X):=\left\{  \left. f:X\to \mathbb{R},x\mapsto \sum_{i=1}^{n}\alpha_{i}k(x,x_{i})    \right| n\in \mathbb{N}, x_{i}\in X,\alpha_{i}\in \mathbb{R} \right\}$$

- **Related definition**: For $f(x)=\sum_{i=1}^{n}\alpha_{i}k(x,x_{i})$ and $g(x)=\sum_{j=1}^{m}\beta_{j}k(x,x'_{i})$, the RKHS inner product is given by: $$\braket{ f ,g  }_{k}:=\sum_{i=1}^{n}\sum_{j=1}^{m}\alpha_{i}\beta_{j}k(x_{i},x'_{j}) $$

---
##### Properties
> [!lemma] Proposition 1
> We have that: 
> 1. $\mathcal{H}_{k}(X)$ is a [[Hilbert space]].

> [!proof]+
> We have that:
> 1. Linearity and symmetry is clear. For positive definiteness, we have that: $$\braket{ f , f }_{k}=\sum_{i,j=1}^{n}\alpha_{i}\alpha_{j}k(x_{i},x_{j})\geq 0 $$by the definition of a kernel function. Hence, $\mathcal{H}_{k}(X)$ is an inner product space.
> 	
> 	To show that it is Banach, let $\{ f_{i} \}_{i}$ be a Cauchy sequence. Then, for any $\varepsilon>0$, there exists $N\in \mathbb{N}$ s.t. $$\left\|  f_{n}-f_{m}\right\|_{k}^2 =$$ 