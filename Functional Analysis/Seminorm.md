#Definition #FunctionalAnalysis 

> [!definition]
> We have that:
> 1. A ***seminorm*** on a $\mathbb{K}$-[[vector space]] $V$ is a map $p:V \to \mathbb{R}_{\geq 0}$ s.t. 
> 	 1. $p(\alpha v)=\left| \alpha \right|p(v)$ for all $\alpha\in \mathbb{K}$ and $v\in V$
> 	 2. $p(v_{1}+v_{2})\leq p(v_{1})+p(v_{2})$ for all $v_{1},v_{2}\in V$.
> 2. A ***seminorm*** on an [[abelian group]] $M$ is a map $\|\cdot\|:M\to \mathbb{R}_{\geq 0}$ s.t.
> 	1. $\|0\|=0$ and 
> 	2. $\left\| f-g \right\|\leq \left\| f \right\|+\left\| g \right\|$ for all $f,g\in M$.
> 3. A ***seminorm*** on a [[ring]] with identity $A$ is a map $\|\cdot\|:A\to \mathbb{R}_{\geq 0}$ s.t. 
> 	1. $\|\cdot\|$ is a seminorm on $A$ as an additive group.
> 	2. $\|1\|=1$.
> 	3. $\left\| fg \right\|\leq \left\| f \right\|\left\| g \right\|$ for all $f,g\in A$.

^e0febd

- **Remark**: A seminorm differs from a [[Norm|norm]] in a sense that it is possible that $p(v)=0$ for some $v \neq 0$.  
- **Related definition**: A seminorm is called ***non-Archimedian*** if $\left\| f-g \right\|\leq \max(\left\| f \right\|,\left\| g \right\|)$. ^a18329
- **Related definition**: The ***seminorm topology*** has a base made up of the following sets: $$N(v,r):=\{ w\in M:\|w-v\|<r \}$$where $v\in M$, $r>0$. ^8c8b4e
- **Related definition**: Two seminorms $\|\cdot\|,\|\cdot\|'$ on abelian group $M$ are ***equivalent*** if there exist $c,c'>0$ s.t. $c\|f\|\leq \|f\|'\leq c'\|f\|$ for all $f\in M$.
- **Related definition**: Let $\varphi:M\to N$ be a homomorphism of seminored groups. We say that:
  1. $\varphi$ is ***bounded*** if there exists $c>0$ s.t. $\left\| \varphi(f) \right\|\leq \left\| f \right\|$ for all $f\in M$.
  2. $\varphi$ is ***admissible*** if the residue seminorm on $M / \text{ker }\varphi$ is equivalent to the restriction of $\|\cdot\|_{N}$ onto $\text{im }\varphi$.
- **Related definition**: A seminorm on a ring $A$ is called 
	1. ***power-multiplicative*** if $\left\| f^n \right\|=\left\| f \right\|^n$ for all $f\in A$ and $n\geq 1$.
	2.  ***multiplicative*** if $\left\| fg \right\|=\left\| f \right\|\left\| g \right\|$ for all $f,g\in A$.
	3. a ***valuation*** if it is a multiplicative norm.
---
##### Properties
###### Seminorms on Vector Spaces
> [!lemma] Theorem 1 (Hahn-Banach)
> Let $V$ be a $\mathbb{K}$-vector space, $p:V \to [0,+\infty)$ a seminorm, $M \subseteq V$ a $\mathbb{K}$-vector subspace and $f:M \to \mathbb{K}$ a linear form with: $$\left| f(v) \right| \leq p(v)$$for all $v\in M$. Then, there is a $\mathbb{K}$-linear extension $F:V \to \mathbb{K}$ s.t.
> 1. $F$ is linear.
> 2. $F|_{M}=f$.
> 3. $\left| F(v) \right|\leq p(v)$ for all $v\in V$.

> [!proof]-
> We can assume that $\mathbb{K}=\mathbb{C}$ as for $\mathbb{R}$, it follows from [[Gauge Function|Hahn-Banach, the Analytic form]]. 
> 
> Now, let $f:M \to \mathbb{C}$ and $f=f_{1}+if_{2}$ where $f_{1},f_{2}:M\to \mathbb{R}$. Then, firstly, we have: $$f_{1}(iv)+if_{2}(iv)=f(iv)=if(v)=-f_{2}(v)+if_{1}(v)$$
> and $f_{1}(iv)=-f_{2}(v)$. As we have, 
>  $$f_{1}(v) \leq p(v)$$and there is a linear extension $F_{1}:V \to \mathbb{R}$ with: $$F_{1} (v)\leq p(v) $$for all $v\in V$. Now define $F(v):=F_{1}(v)-iF_{1}(iv)$. Then, 
>  1. $F$ is $\mathbb{C}$-linear as $F(iv)=iF(v)$.
>  2. $F$ extends $f$ as for all $v\in M$:$$F(v)=F_{1}(v)-iF_{1}(iv)=f_{1}(v)-if_{1}(iv)=f(v)$$
>  3. $|F|$ is bounded by $p$. Let $v\in V$ and $\alpha\in \mathbb{C}$ with $\left| \alpha \right|=1$ s.t.:
> $$\left| F(v) \right| =\alpha F(v)=F(\alpha v)=F_{1}(\alpha v)$$Thus, $$\left| F(v) \right| =F_{1}(\alpha v)\leq p(\alpha v)=p(v)$$
---
###### Seminorms on Abelian Groups
> [!lemma] Proposition 1 (Topology with Seminorms)
> Let $M$ be an abelian group and $\|\cdot\|$ a seminorm on $M$. Then, 
> 1. $\|-x\|=\|x\|$ for all $x\in M$.
> 2. $\left| \left\| f \right\|-\left\| g \right\| \right|\leq \left\| f+g \right\|$ for all $f,g\in M$.
> 3. $\left| \left\| f \right\|-\left\| g \right\| \right|\leq \left\| f-g \right\|$ for all $f,g\in M$.
> 4. the seminorm topology $\tau_{\|\cdot\|}$ is indeed a topology.
> 5. $\tau_{\|\cdot\|}$ is Hausdorff if and only if $\|\cdot\|$ is a norm, i.e. $\|f\|=0$ only when $f=0$.
> 6. if $\|\cdot\|$ and $\|\cdot\|'$ are equivalent, $\tau_{\|\cdot\|}=\tau_{\|\cdot\|'}$. 

^eaf99a

> [!proof]-
> We have that:
> 1. For any $x\in M$, $$\|-x\|=\|0-x\|\leq \|0\|+\|x\|=\|x\|$$As $x= -(-x)$, we have our statement.
> 2. We have that: $$\left\| f \right\| =\left\| f+g-g \right\|\leq \left\| f+g \right\| +\left\| g \right\|,\quad \left\| g \right\| =\left\| f+g-f \right\| \leq \left\| f+g \right\| +\left\| f \right\|   $$
> 3. We have that: $$\left\| f+(-g) \right\| \geq \left| \left\| f \right\| -\left\| -g \right\|  \right| =\left| \left\| f \right\| -\left\| g \right\|  \right| $$
> 4. It suffices to show that $A:=N(v,s)\cap N(w,t)$ is open in $\tau_{\|\cdot\|}$ for any $v,w\in M$ and $s,t>0$. Let $u\in A$. Then, we have that $\|u-v\|<s$ and $\|w-v\|<t$. 
>    
>    Let $\varepsilon:= \min \{ s-\|u-v\|,t-\|w-v\| \}> 0$. Then, for any $x \in N(u,\varepsilon)$, $$\|v-x\|=\|v-u+u-x\|\leq \|v-u\|+\|u-x\|< \|u-v\|+ \varepsilon\leq s$$Similarly $\|w-x\|< t$. Hence, $N(u,\varepsilon)\subseteq A$. This shows the statement.
> 3. Let $\tau_{\|\cdot\|}$ be Hausdorff. However, assume that we have $f\neq 0$ s.t. $\left\| f \right\|=0$. Then, let $s,t>0$ s.t. $$N(0,s)\cap N(f,t)=\varnothing$$However, $\left\| f-0 \right\|\leq \left\| f \right\|+\left\| 0 \right\|=0<s$ and $f\in N(0,s)$. This is a contradiction. 
>    
>    Conversely, if $\|\cdot\|$ is a norm. Assume that there exists $u,v$ s.t. $N(u,s)\cap N(v,t)\neq \varnothing$ for all $s,t>0$. Then, $v\in N(u,s)$ for all $s > 0$ and $\|u-v\|=0$. This shows that $u=v$.
> 4. Let $C\|f\|\leq \|f\|'\leq C'\|f\|$ for all $f\in M$. Then, for any $v\in M$ and $r>0$, we will show that $N(v,r)$ is open in $\tau_{\|\cdot\|'}$. For any $w\in N(v,r)$, we have that $\|v-w\|<r$ and: $$\|x-w\|'<C(r-\|v-w\| )\implies \|v-x\|\leq \|v-w\|+\|w-x\|<r$$for any $x$. Hence, $N'(w,C(r-\|v-w\|))\subseteq N(v,r)$. This shows the statement and the other direction holds by symmetry.

^dd4e85

---
> [!lemma] Proposition 2 (Residue Seminorm)
> Let $M$ be an abelian group and $N\leq M$. Then, for a seminorm $\|\cdot\|$ on $M$, the ***residue seminorm*** is a seminorm on $M / N$ defined as:$$\|\cdot \|:M / N\to \mathbb{R}_{\geq 0},\quad f\mapsto \inf \{ \|g\|: g\in q^{-1}(f) \}$$where $q:M\to M / N$ is the quotient homomorphism.
> 1. the residue seminorm is a seminorm.
> 2. the residue seminorm is a norm if and only if $N$ is closed in $M$.
> 3. if $M$ is complete w.r.t. a norm and $N$ is closed, then $M / N$ is complete w.r.t. the residue norm.

> [!proof]-
> We have that:
> 1. $\|0\|=0$ as $q(0)=0$. Now for $f,g\in M / N$, we have for any $q(f_{0})=f$ and $q(g_{0})=g$, $$\inf\|f_{0}-g_{0}\|\leq \left\| f_{0}-g_{0} \right\|\leq \left\| f_{0} \right\| +\left\| g_{0} \right\|  $$ Hence, $\|f-g\|\leq \|f\|+\|g\|$. 
> 2. If the residue seminorm is a norm, then $\left\| f \right\|=0$ only when $f=0$. If $N$ is not closed, then there exists $(x_{n})_{n}\subseteq N$ s.t. $\lim_{ n \to \infty }x_{n}=: x\notin N$. Hence, $x+N\neq N$. We first claim that $\lim_{ n \to \infty }\|x_{n}+N\|=\|x+N\|$. Let $\varepsilon>0$. Then, there exists $n_{0}$ s.t. $x_{n}\in N(x,\varepsilon)$ for all $n\geq n_{0}$. Thus: $$\left| \left\| x_{n} +N\right\| -\|x+N\| \right| \leq \left\| x_{n}-x+N \right\|\leq \left\| x_{n}-x \right\| < \varepsilon, \quad \forall n\geq n_{0} $$
>    This shows that $\|x+N\|=0$ and $x+N=0$ which is a contradiction.
>    
>    Conversely, if $N$ is closed in $M$. Let $x\in M$ with $\left\| x+N \right\|=0$. Then, we have $(y_{n})_{n}\subseteq N$ s.t. $\lim_{ n \to \infty }\left\| x+y_{n} \right\|=0$. This means $\lim_{ n \to \infty }x+y_{n}=0$ and $x+\lim_{ n \to \infty }y_{n}=0$ where $\lim_{ n \to \infty }y_{n}\in N$ by the closure. Hence, $x\in N$.
> 3. As $N$ is closed, the residue seminorm is a norm and we have that from $\|x+N\|\leq\|x\|$ that $q:M\to M / N$ is continuous. 
>    
>    Now, let $(f_{n})_{n}\subseteq M / N$ s.t. $\sum_{n=1}^{\infty}\|f_{n}\|$ converges.
>    
>    Then, by definition we can choose $x_{n}\in q^{-1}(f_{n})$ s.t. $\|x_{n}\|\leq 2\|f_{n}\|$. Therefore $\sum_{n=1}^{\infty}\|x_{n}\|$ converges too and as $M$ is Banach, by [[Banach Space|Proposition 3]], $\sum_{n=1}^{\infty}x_{n}$ converges to say $x$. Hence, by definition, we have that $\sum_{n=1}^{\infty}f_{n}$ converges to $x+N$. Using Proposition 3 again, we have that $M / N$ is Banach.

---
> [!lemma] Proposition 3 (Seminormed Group Homomorphism)
> 