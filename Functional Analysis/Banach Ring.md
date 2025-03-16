#Definition #FunctionalAnalysis 

> [!definition]
> Let $A$ be a normed [[ring]], i.e. it is equipped with a [[Seminorm|norm]] $\|\cdot\|$.
> 1. $A$ is a ***Banach ring*** if it is [[Banach Space|Banach]] w.r.t. the norm.
- **Related definition**: A [[Seminorm|seminorm]] $\left| \cdot \right|$ on a Banach ring $A$ is called ***bounded*** if there exists $c>0$ s.t. $\left| f \right|\leq c\left\| f \right\|$ for all $f\in A$.
---
##### Properties
> [!lemma] Proposition 1
> Let $A$ be a Banach ring. For $x\in A$, we have that:
> 1. $\lim_{ n \to \infty }\|x^n\|^{1 / n}\leq \|x\|$.
> 2. if $\lim_{ n \to \infty }\|x^n\|^{1 / n}<1$, then $1-x$ is a unit, i.e. $(1-x)^{-1}=\sum_{n=0}^{\infty}x^n$ where $x^0=1$.

> [!proof]-
> We have:
> 1. $\|x^n\|\leq \|x\|^n$ by Banach ring for all $n$.
> 2. Let $q$ s.t. $\lim_{ n \to \infty }\|x^n\|^{1 / n}< q<1$. Then, there exists $n_{0}\geq 1$ s.t. $\|x^n\|^{1 /n}\leq q$ for all $n\geq n_{0}$, i.e. $\left\| x^n \right\|\leq q^n$. Hence, $$\sum_{n=N}^{\infty}\left\| x^n \right\| \leq \sum_{n=N}^{\infty}q^n=\frac{q^N}{1-q}$$and the series is absolutely convergent. Further, $$(1-x)\sum_{n=0}^{\infty}x^n=\sum_{n=0}^{\infty}x^n-\sum_{n=1}^{\infty}x^n=1$$
---
> [!lemma] Proposition 2 (Quotient and Product Banach Ring)
> Let $A$ and $(A_{i})_{i\in I}$ be Banach rings. 
> 1. for a proper closed ideal $I\unlhd A$, $A / I$ is Banach w.r.t. [[Seminorm|residue norm]].
> 2. $\prod_{i\in I}^{}A_{i}:=\{ (f_{i})_{i\in I}: \exists c>0, \|f\|_{i}\leq c, \forall i\in I \}$ is Banach w.r.t. $\|(f_{i})_{i\in I}\|:=\sup_{i\in I}\left\| f_{i} \right\|$.

> [!proof]-
> We have that:
> 1. By [[Seminorm|Proposition 2.3]] we have that $A / I$ is complete w.r.t. the residue norm as an additive group. Now, we only have to show that it is also a norm as a ring. Of course we have: $$\left\| 1+I \right\|\leq \left\| 1 \right\| =1 $$Now assume that $\left\| 1+I \right\|<1$. Then, there exists $m\in I$ s.t. $\left\| 1+m \right\|<1$. Then, by Proposition 1, $1-1-m=-m$ is a unit. This is a contradiction to the fact that $I$ is proper. Hence, $\left\| 1+I \right\|=1$. 
>    
>    Similarly, for $f,g\in A$, $\left\| fg+I \right\|\leq \left\| f+I \right\|\left\| g+I \right\|$. Indeed, let $m,m'\in I$ s.t. $\left\| f+m \right\|\leq \left\| f+I \right\|+\varepsilon$ and $\left\| g+m' \right\|\leq \left\| g+I \right\|+ \varepsilon$. Then, $$\begin{aligned}\left\| fg+I \right\|& \leq \left\| (f+m)(g+m') \right\| \\&\leq \left\| f+m \right\|\left\| g+m' \right\| \leq \left\| f+I \right\| \left\| g+I \right\| +\varepsilon(\left\| f+I \right\| +\left\| g+I \right\| )+\varepsilon^{2} \end{aligned}$$By taking $\varepsilon$ to zero, we have our statement. 
> 2. We have that $\left\| 0 \right\|=0$ and: $$\left\| f-g \right\| =\sup_{i\in I}\left\| f_{i}-g_{i} \right\| \leq \sup_{i\in I}\left\| f_{i} \right\| +\left\| g_{i} \right\| \leq \left\| f \right\| +\left\| g \right\| $$Further, $\left\| 1 \right\|=1$ and $\left\| fg \right\|\leq \left\| f \right\|\left\| g \right\|$ with the same argument as above. To show that it is Banach, let $(f_{n})_{n}$ be a Cauchy sequence. Then, for any $\varepsilon>0$ there exists $m$ s.t. $$\left\| f_{n,i}-f_{m,i} \right\| \leq \left\| f_{n}-f_{m} \right\| \leq \varepsilon,\quad \forall n\geq m,i\in I$$Hence, $(f_{n,i})_{n}$ is Cauchy for all $i$ and converges to $f_{i}$. 
> 	1. **$f$ is bounded**. For $\varepsilon>0$, we have for some $n$: $$\left\| f \right\| \leq \left\| f-f_{n} \right\| +\left\| f_{n} \right\| \leq \varepsilon+\left\| f_{n} \right\| <+\infty$$
> 	2. **$f_{n}\to f$ in norm**: For $\varepsilon>0$, there exists $K$ s.t. $\left\| f_{n}-f_{m} \right\|< \varepsilon$ for all $n,m\geq K$. Then, by $n\to \infty$, we have that: $$\left\| f-f_{m} \right\|\leq \left\| f-f_{n} \right\| +\left\| f_{n}-f_{m} \right\| <2\varepsilon $$for large $n,m\geq K$.
>    
>    This shows that we have a Banach ring.
---
> [!lemma] Proposition 3 (Bounded Seminorms)
> Let $A$ be a Banach ring and $\left| \cdot \right|$ a seminorm on $A$.
> 1. if $\left| \cdot \right|$ is [[Seminorm|power-multiplicative]], then $\left| f \right|\leq \left\| f \right\|$ for all $f\in A$.

> [!proof]+
> We have that:
> 1. there exists $c>0$ with $\left| f \right|\leq c\left\| f \right\|$ for all $f\in A$. Hence, $$\left| f \right|^n=\left| f^n \right|\leq C\left\| f^n \right\|\leq C \left\| f \right\| ^n,\quad \forall n$$Therefore, $\left| f \right|\leq C^{1 / n} \left\| f \right\|$ for all $n$ and $\left| f \right|\leq \left\| f \right\|$.
---
##### Examples
> [!h] Example 1
> We have that:
> 1. Any ring $A$ is a Banach ring with $\left| \cdot \right|_{0}:A \to \mathbb{R}_{\geq 0},f\mapsto \mathbb{1}_{f\neq 0}$.
> 2. $\mathbb{Z}$ is a Banach ring with absolute value $\left| \cdot \right|$.

> [!proof]-
> We have that:
> 1. Obviously $\left| \cdot \right|_{0}$ is a seminorm on $A$ as a ring. Further by definition it is a norm as well. Now, if we have a Cauchy sequence $(f_{n})_{n}$, by taking $\varepsilon = 1 /2$, there exists $n_{0}$ s.t. $\left| f_{m}-f_{n_{0}} \right|_{0}=0$, i.e. $f_{m}=f_{n_{0}}$ for all $m\geq n_{0}$. By taking $f:=f_{n_{0}}$, we have that $f_{n}\to f$.
> 2. $\left| \cdot \right|$ is a norm on $\mathbb{Z}$ as an abelian group. Further, it is a multiplicative norm. With the same arguments as above, for any Cauchy sequence $(n_{k})_{k}$ there exists $k_{0}$ s.t. $n_{\ell}=n_{k_{0}}$ for all $\ell\geq k_{0}$. Hence, the sequence converges. 
---
> [!h] Example 2 (Power Series Banach Ring)
> Let $A$ be a Banach ring and $r>0$. Then, $$A\langle r^{-1}T\rangle:=\left\{  f=\sum_{i=0}^{\infty}a_{i}T^i: a_{i}\in A, \left\| f \right\| :=\sum_{i=0}^{\infty}\left\| a_{i} \right\| r^i <+\infty \right\}$$
> 1. $A\langle r^{-1}T\rangle$ is a Banach ring.
> 2. $1-aT$ is invertible if and only if $\sum_{i=0}^{\infty}\left\| a^i \right\|r^i<\infty$.

> [!proof]-
> We have that:
> 1. $\left\| 0 \right\|=0$ and $$\left\| \sum_{i=0}^{\infty}(a_{i}-b_{i})T^i \right\|=\sum_{i=0}^{\infty}\left\| a_{i}-b_{i} \right\| r^i\leq \sum_{i=0}^{\infty}\left\| a_{i}\right\|r^i+\sum_{i=0}^{\infty}\left\|b_{i} \right\| r^i=\left\| \sum_{i=0}^{\infty}a_{i}T^i \right\|+\left\| \sum_{i=0}^{\infty}b_{i}T^i \right\|  $$Further, $$\left\| \sum_{i=0}^{\infty}a_{i}T^i \right\| =\sum_{i=0}^{\infty}\left\| a_{i} \right\| r^i=0$$then $a_{i}=0$ for all $i$. Lastly, $\left\| 1 \right\|=1$ and $$\left\| \sum_{i,j=0}^{\infty}a_{i}b_{j}T^{i+j} \right\| \leq \sum_{i,j=0}^{\infty}\left\| a_{i} \right\| \left\| b_{j} \right\| r^{i+j}=\left\| \sum_{i=0}^{\infty}a_{i}T^i \right\| \cdot \left\| \sum_{j=0}^{\infty}b_{j}T^j \right\| $$Hence, $A \braket{ r^{-1}T  }$ is a normed ring. Now, let $(f_{n})_{n}$ be a Cauchy sequence. Then, for any $\varepsilon>0$ there exists $m$ s.t:$$\left\| \sum_{i=0}^{\infty}(a_{n,i}-a_{m,i}) T^i\right\|=\sum_{i=0}^{\infty}\left\| a_{n,i}-a_{m,i} \right\| r^i<\varepsilon,\quad \forall n\geq m $$Then, $\left\| a_{n,i}-a_{m,i} \right\|< \varepsilon /r^i$ and we have that for all $i\geq 0$ $(a_{n,i})_{n}$ is Cauchy. Hence, $a_{n,i}\to a_{i}$ and we have that similarly to Proposition 2.2, $\sum_{i=0}^{\infty}a_{n,i}T^i$ converges to $\sum_{i=0}^{\infty}a_{i}T^i$ and the limit is in $A\langle r^{-1}T\rangle$. 
> 2. We have that: $$(1-aT)\left( \sum_{i=0}^{\infty}a^i T^i \right)=\sum_{i=0}^{\infty}a^iT^i-\sum_{i=1}^{\infty}a^iT^i=1$$Hence, if $1-aT$ is invertible if and only if  $\sum_{i=0}^{\infty}a^i T^i\in A\braket{ r^{-1}T  }$, i.e. $\sum_{i=0}^{\infty}\left\| a^i \right\|r^i<+\infty$. 

---
