#Definition #FunctionalAnalysis 

> [!definition]
> Let $E$ be a $\mathbb{R}$-vector space and $A\subseteq E$ a [[Convex Set|convex]] subset. 
> 1. $x\in A$ is an ***extreme point*** if for all $y,z\in A$ it holds that: $$x\in (y,z)\implies x=y=z$$
>    $\text{ex}(A)$ denotes the set of all extreme points in $A$.
> 2. A convex subset $B\subseteq A$ is ***extreme*** if for all $y,z\in A$:$$(y,z)\cap B\neq \varnothing\implies[y,z]\subseteq B$$
>    
> where $[x,y]:=\{ tx+(1-t)y:t\in[0,1] \}$ and $(x,y):=\{ tx+(1-t)y:t\in(0,1) \}$.
---
##### Properties
> [!lemma] Fact 1
> Let $A,B,C\subseteq E$ be convex sets with $A\subseteq B\subseteq C$. Then, if $A$ is extreme in $B$ and $B$ is extreme in $C$, then $A$ is extreme in $C$. 

> [!proof]-
> For $y,z\in C$, if $(y,z)\cap A\neq \varnothing$, then as $A\subseteq B$, $(y,z)\cap B\neq \varnothing$. Since $B$ is extreme in $C$, we have: $$[y,z]\subseteq B$$In particular, $y,z\in B$ and since $A$ is extreme in $B$, $[y,z]\subseteq A$.
---
> [!lemma] Fact 2
> Let $E$ be a [[Topological Vector Space with Seminorms|topological vector space]] generated by a sufficient family of seminorms. Let $A,B$ closed, convex, non-empty sets s.t. $B\subseteq A$ and $B$ is extreme in $A$. Then, $B$ contains an extreme point in $A$.

> [!proof]-
> We have:
> 1. **Using Zorn's lemma to find the maximal element**:
> We use [[Poset|Zorn's lemma]] on $\mathcal{E}(B)$ where: $$\mathcal{E}(B):=\{ C\subseteq B:C\text{ is closed, convex, non-empty and extreme in }A \}$$Further, $C_{1}\leq C_{2}\iff C_{2}\subseteq C_{1}$. As $B\in \mathcal{E}(B)$, $\mathcal{E}(B)$ is not empty. Therefore, $(\mathcal{E}(B),\leq)$ defines a poset.
> 
>    Let $\mathcal{C}\subseteq \mathcal{E}(B)$ be a totally ordered subset. We will show that $\mathcal{C}$ is upper bounded. Let $C_{1},\dots,C_{n}\in \mathcal{C}$ and assume $C_{n}\subseteq C_{n-1}\subseteq\dots \subseteq C_{1}$. Then, $$\bigcap_{i=1}^{n}C_{i}=C_{n}$$and since $C_{n}\in \mathcal{C}$, $C_{n}\neq \varnothing$. As $A$ is a compact Hausdorff space, $$M=\bigcap_{C\in \mathcal{C}}^{}C\neq \varnothing$$and $M\in \mathcal{E}(B)$. $M$ is of course convex and closed in $A$ and we only need to show that $M$ is extreme in $A$.  
> 
>    Let $y,z\in A$ s.t. $(y,z)\cap M\neq \varnothing$. Then, for all $C\in \mathcal{ C}$, $(y,z)\cap C\neq \varnothing$ and since $C$ is extreme in $A$, $[y,z]\in C$. Therefore, $[y,z]\in M$. Hence, $M$ is an upper bound for $\mathcal{C}$.
> 
>    Therefore, by Zorn's lemma, $\mathcal{E}(B)$ admits a maximal element $Z\in \mathcal{E}(B)$. 
>    
>  2. **Showing $Z$ is a singleton set**:
>     Assume there exists $x,y\in Z$ s.t. $x\neq y$. Then, by [[Topological Vector Space with Seminorms|Theorem 6]], there exists $F\subseteq E^{*}$ s.t. $$F(x)<F(y)$$Let $m:=\max\{ F(z):z\in Z \}$ which exists as $Z$ is compact and $F$ is continuous. Let $D:=\{ z\in Z : F(z)=m \}$. Then, $D\neq\varnothing$, $D$ is closed and compact. Let's show that $D$ is extreme in $Z$. 
> 
>     Let $v,w\in Z$ and $(v,w)\cap D\neq \varnothing$. Therefore, there exists $t\in(0,1)$ s.t. $tv+(1-t)w\in D$, i.e. $$F(tv+(1-t)w)=m\geq F(v),F(w)$$and $$(1-t)F(v)\leq(1-t)F(w),\quad F(v)\leq F(w)$$Similarly, $$tF(w)\leq tF(v),\quad F(w)\leq F(v)$$Therefore, $F(w)=F(v)=m$ which shows that $[v,w]\in D$. Hence, $D\in \mathcal{E}(B)$ as $D$ is extreme in $A$ as well. However, since $x\notin D$, $Z\leq D$ and this contradicts the statement that $Z$ is maximal. 
> 
>      Therefore, $Z$ is an extreme singleton set. 
---
> [!lemma] Theorem 2 (Krein-Milman)
> Let $E$ be a [[Topological Vector Space with Seminorms|topological vector space]] generated by a sufficient family of seminorms. Further, let $A\subseteq E$ be a non-empty, convex, compact set. Then, $$\overline{\text{co}(\text{ex}(A))}=A$$

> [!proof]-
> We may assume that $A\neq \varnothing$. Then, $\text{ex}(A)\neq \varnothing$ and clearly, $\overline{\text{co}(\text{ex}(A))}\subseteq A$. Assume there exists $x\in A$ s.t. $x\notin \overline{\text{co}(\text{ex}(A))}$. Then by [[Topological Vector Space with Seminorms|Hahn-Banach 2nd Geometric form]], there exists $\alpha\in R$ and $F\in E^{*}$ s.t. $$F(x)>\alpha>F(y)\quad \forall y\in \overline{\text{co}(\text{ex}(A))}$$Now let $m:=\max\{ F(z): z\in A \}$ and $D:=\{ z\in A: F(z)=m \}$. Then, $D$ is non-empty, closed, convex and extreme in $A$. From Fact 2, we know that $D$ contains an extreme point  $e\in A$. However, as $e\in \overline{\text{co}(\text{ex}(A))}$,$$F(e)=m\geq F(x)>F(e)$$which is a contradiction.
- **Remark**: The closure is necessary: Counterexample: $A=M^1([0,1])$. Then: $$\text{ex}(A)=\{ \delta_{x}: x\in[0,1] \}$$But if we don't have the closure, we cannot represent probability distributions with infinite support.
---