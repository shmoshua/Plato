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
> 2. if $\left| \cdot \right|,\left| \cdot \right|'\neq \left| \cdot \right|_{0}$ from [[Banach Ring|Example 1]], then $a$ is unique.

> [!proof]-
> We have that:
> 1. We have that for a norm $\left| \cdot \right|$, $$N(0,1)=\{ f\in A:\lim_{ n \to \infty } f^n =0 \}$$Hence, for $\left| \cdot \right|$ and $\left| \cdot \right|'$, $B_{<1}(0)=B_{<1}'(0)$ and $B_{\le 1}(0)=B_{\leq 1}'(0)$. Hence, for the unit spheres, $S=S'$. 
>    
>    Now, let $f,g\in A$ s.t. $\left| f \right|=\left| g \right|$. Then, $$1=\left| f f^{-1} \right|=\left| f \right| \left| f^{-1} \right| =\left| g \right| \left| f^{-1} \right| =\left| gf^{-1} \right| $$Hence $\left| gf^{-1} \right|'=1$ and we have that $\left| g \right|'=\frac{1}{\left| f^{-1} \right|'}=\left| f \right|'$. Hence, we can define $\varphi:\mathbb{R}_{\geq 0}\to \mathbb{R}_{\geq 0}$ s.t. $\varphi(\left| f \right|)=\left| f \right|'$ for all $f\in A$.
>    
>    Finally, we show that $\varphi$ is a power function. We have: $$\varphi(\lim_{ n \to \infty } \left| f_{n} \right| )=\varphi(\left| f \right| )=\left| f \right| '=\lim_{ n \to \infty } \left| f_{n} \right| '=\lim_{ n \to \infty } \varphi(\left| f_{n} \right| )$$Hence, $\varphi$ is continuous. Further, for any $f,g\in A$, $$\varphi(\left| f \right| \left| g \right| )=\varphi(\left| fg \right| )=\left| fg \right| '=\left| f \right| '\left| g \right| '=\varphi(\left| f \right| )\varphi(\left| g \right| )$$
>    We conclude by pointing that the only continuous multiplicative function on the positive reals is the power function. 
> 2. Obvious. 

---
> [!lemma] Proposition 2
> Let $A$ be a valuation field that is not non-Archimedean. Then, 
> 1. $A\cong \mathbb{R}$ or $A\cong \mathbb{C}$ with norm $\left| \cdot \right|_{\varepsilon}$ for $0<\varepsilon\leq 1$ where $\left| f \right|_{\varepsilon}:= \left| f \right|^\infty$. 

---
