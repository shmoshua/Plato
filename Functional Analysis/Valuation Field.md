#Definition #FunctionalAnalysis 

> [!definition]
> Let $A$ be a [[field]]. $A$ is a ***valuation field*** if:
> 1. $A$ can be endowed a [[Seminorm|valutation]] $\|\cdot\|$ that makes $A$ a [[Banach ring]].

- **Related definition**: If $\|\cdot\|$ is [[Seminorm|non-Archimedean]], then $A$ is a ***non-Archimedean field***.

---
##### Properties
> [!lemma] Proposition 1
> Let $A$ be a normed field. 
> 1. if $\left| \cdot \right|$ and $\left| \cdot \right|'$ are two [[Seminorm|valuations]] on $A$ inducing the same topology, then there exists $a>0$ with $\left| f \right|'=\left| f \right|_{1}^a$ for all $f\in A$.

> [!proof]+
> We have that:
> 1. We have that for a norm $\left| \cdot \right|$, $$N(0,1)=\{ f\in A:\lim_{ n \to \infty } f^n =0 \}$$Hence, for $\left| \cdot \right|$ and $\left| \cdot \right|'$, $B_{<1}(0)=B_{<1}'(0)$. 
>    
>    
>    Assume they induce the same topology. Then, there exists $c>0$ s.t. $B'_{<c}(0)\subseteq B_{<1}(0)$, i.e. $\left| x \right|'<c\implies \left| x \right|<1$. Similarly, there exists $c'>0$ s.t. $\left| x \right|<c'\implies \left| x \right|'<1$. Hence, $$$$
>    
>    Hence, $\text{id}:(A, \left| \cdot \right|)\to (A,\left| \cdot \right|')$ is a homeomorphism. We show that then $\left| \cdot \right|$ and $\left| \cdot \right|'$ are equivalent. Let $f\in A$. Then, as $0\in N(f,\left| f \right|+\varepsilon)$ for any $\varepsilon>0$, there exists $\delta>0$ s.t. $N'(0,\delta)\subseteq N(f,\left| f \right|+\varepsilon)$. Hence, $$\left| f \right| '$$