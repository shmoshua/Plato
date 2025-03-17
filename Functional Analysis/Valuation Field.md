#Definition #FunctionalAnalysis 

> [!definition]
> Let $A$ be a [[field]]. $A$ is a ***valuation field*** if:
> 1. $A$ can be endowed a [[Seminorm|valutation]] $\|\cdot\|$ that makes $A$ a [[Banach ring]].

- **Related definition**: If $\|\cdot\|$ is [[Seminorm|non-Archimedean]], then $A$ is a ***non-Archimedean field***.

---
##### Properties
> [!lemma] Proposition 1
> Let $A$ be a normed field. 
> 1. if $\left| \cdot \right|$ and $\left| \cdot \right|'$ are two [[Seminorm|valuations]] on $A$ inducing the same topology, then there exists $a>0$ with $\left| f \right|'=\left| f \right|^a$ for all $f\in A$.

> [!proof]+
> We have that:
> 1. We have that for a norm $\left| \cdot \right|$, $$N(0,1)=\{ f\in A:\lim_{ n \to \infty } f^n =0 \}$$Hence, for $\left| \cdot \right|$ and $\left| \cdot \right|'$, $B_{<1}(0)=B_{<1}'(0)$ and $B_{\le 1}(0)=B_{\leq 1}'(0)$. Hence, for the unit spheres, $S=S'$. 
>    
>    Now, let $f,g\in A$ s.t. $\left| f \right|=\left| g \right|$. Then, $$\left|  \right| $$
>    
>    
>    
>    
>    Assume they induce the same topology. Then, there exists $c>0$ s.t. $B'_{<c}(0)\subseteq B_{<1}(0)$, i.e. $\left| x \right|'<c\implies \left| x \right|<1$. Then, $\left| x \right|'\leq c$ implies $\left| x \right|\leq 1$ by continuity of the norm. Hence, for any $f\in A$, $$\left| \frac{f}{\left| f \right|' } \right| \leq  \frac{1}{c},\quad \left| f \right| \leq  \frac{1}{c}\left| f' \right| $$for all $f\neq 0$. By symmetry, the two valuations are equivalent. Now, let $f,g\in A$ s.t. $\left| f \right|=\left| g \right|$. Then, $$$$
>    
>    $\varphi:\mathbb{R}_{\geq 0}\to \mathbb{R}_{\geq 0}$ s.t. $$\varphi(\left| f \right| )=\left| f \right| '$$
>    
>    
>    
>    Now, let $c\left| f \right|'\leq \left| f \right|\leq d\left| f \right|'$ for all $f\in A$. However, we have that: 
>    
>    $$\left| f \right| $$
> 2. 
>    Similarly, there exists $c'>0$ s.t. $\left| x \right|<c'\implies \left| x \right|'<1$. Hence, $$$$
>    
>    Hence, $\text{id}:(A, \left| \cdot \right|)\to (A,\left| \cdot \right|')$ is a homeomorphism. We show that then $\left| \cdot \right|$ and $\left| \cdot \right|'$ are equivalent. Let $f\in A$. Then, as $0\in N(f,\left| f \right|+\varepsilon)$ for any $\varepsilon>0$, there exists $\delta>0$ s.t. $N'(0,\delta)\subseteq N(f,\left| f \right|+\varepsilon)$. Hence, $$\left| f \right| '$$