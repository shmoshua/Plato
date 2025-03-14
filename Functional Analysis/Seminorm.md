#Definition #FunctionalAnalysis 

> [!definition]
> We have that:
> 1. A ***seminorm*** on a $\mathbb{K}$-[[vector space]] $V$ is a map $p:V \to \mathbb{R}_{\geq 0}$ s.t. 
> 	 1. $p(\alpha v)=\left| \alpha \right|p(v)$ for all $\alpha\in \mathbb{K}$ and $v\in V$
> 	 2. $p(v_{1}+v_{2})\leq p(v_{1})+p(v_{2})$ for all $v_{1},v_{2}\in V$.
> 2. A ***seminorm*** on an [[abelian group]] $M$ is a map $\|\cdot\|:M\to \mathbb{R}_{\geq 0}$ s.t.
> 	1. $\|0\|=0$ and 
> 	2. $\left\| f-g \right\|\leq \left\| f \right\|+\left\| g \right\|$ for all $f,g\in M$.

^e0febd

- **Remark**: A seminorm differs from a [[Norm|norm]] in a sense that it is possible that $p(v)=0$ for some $v \neq 0$.  
- **Remark**: A seminorm is called ***non-Archimedian*** if $\left\| f-g \right\|\leq \max(\left\| f \right\|,\left\| g \right\|)$. ^a18329
- **Remark**: The ***seminorm topology*** has a base made up of the following sets: $$N(v,r):=\{ w\in M:\|w-v\|<r \}$$where $v\in M$, $r>0$. ^8c8b4e
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
> 2. the seminorm topology $\tau_{\|\cdot\|}$ is indeed a topology.
> 3. $\tau_{\|\cdot\|}$ is Hausdorff if and only if $\|\cdot\|$ is a norm, i.e. $\|f\|=0$ only when $f=0$.

^eaf99a

> [!proof]-
> We have that:
> 1. For any $x\in M$, $$\|-x\|=\|0-x\|\leq \|0\|+\|x\|=\|x\|$$As $x= -(-x)$, we have our statement.
> 2. It suffices to show that $A:=N(v,s)\cap N(w,t)$ is open in $\tau_{\|\cdot\|}$ for any $v,w\in M$ and $s,t>0$. Let $u\in A$. Then, we have that $\|u-v\|<s$ and $\|w-v\|<t$. 
>    
>    Let $\varepsilon:= \min \{ s-\|u-v\|,t-\|w-v\| \}> 0$. Then, for any $x \in N(u,\varepsilon)$, $$\|v-x\|=\|v-u+u-x\|\leq \|v-u\|+\|u-x\|< \|u-v\|+ \varepsilon\leq s$$Similarly $\|w-x\|< t$. Hence, $N(u,\varepsilon)\subseteq A$. This shows the statement.
> 3. Let $\tau_{\|\cdot\|}$ be Hausdorff. However, assume that we have $f\neq 0$ s.t. $\left\| f \right\|=0$. Then, let $s,t>0$ s.t. $$N(0,s)\cap N(f,t)=\varnothing$$However, $\left\| f-0 \right\|\leq \left\| f \right\|+\left\| 0 \right\|=0<s$ and $f\in N(0,s)$. This is a contradiction. 
>    
>    Conversely, if $\|\cdot\|$ is a norm. Assume that there exists $u,v$ s.t. $N(u,s)\cap N(v,t)\neq \varnothing$ for all $s,t>0$. Then, $v\in N(u,s)$ for all $s > 0$ and $\|u-v\|=0$. This shows that $u=v$.

^dd4e85

---