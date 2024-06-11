#Definition #Topology 

> [!definition]
> A ***metric space*** is a pair $(X,d)$ for a set $X$ and a real function $d:X\times X \to [0,+\infty)$ called the ***metric/distance*** such that:
> 1. **Non-degeneracy**: $d(x,y)=0$ if and only if $x=y$.
> 2. **Symmetry**: $d(x,y)=d(y,x)$ for all $x,y\in X$
> 3. **Triangle Inequality**: $d(x,z)\leq d(x,y)+d(y,z)$ for all $x,y,z\in X$.
> 

- **Related Definition**: $(X,d)$ is ***complete***, if every [[Cauchy Sequence| Cauchy sequence]] of points in $X$ has a limit that is also in $X$.
---
##### Properties
> [!lemma] Proposition 1
> The metric $d$ defines a [[Topological Space|topology]] $\mathcal{T}_{d}$ on $X$ as follows: $U\in \mathcal{T}_{d}$ if and only if for all $x\in U$, there exists $r>0$ s.t. $$B_{<r}(x):=\{ y\in X:d(x,y)<r \}\subseteq U$$

> [!proof]-
> We will show that $\mathcal{T}_{d}$ is a topology.
> 1. $\varnothing,X\in \mathcal{T}_{d}$ (take any $r>0$)
> 2. Let $(U_{\lambda})_{\lambda\in \Lambda}\subseteq \mathcal{T}_{d}$ and $x\in \bigcup_{\lambda\in \Lambda}^{}U_{\lambda}$. Then, there exists $\alpha\in \Lambda$ s.t. $x\in U_{\alpha}$ and there exists $r>0$ s.t. $B_{<r}(x)\subseteq U_{\alpha}\subseteq \bigcup_{\lambda\in \Lambda}^{}U_{\alpha}$.
> 3. Let $U_{1},U_{2}$ be open and $x\in U_{1}\cap U_{2}$. Then, there exists $r_{1},r_{2}>0$ s.t. $B_{<r_{1}}(x)\subseteq U_{1}$ and $B_{<r_{2}}(x)\subseteq U_{2}$. Then, $B_{<r}(x)\subseteq U_{1}\cap U_{2}$ for $r:=\min\{ r_{1},r_{2} \}$.
- -**Remark**: There can be infinitely many metrics defining the same topology, e.g. $d_{p}(x,y):=\left( \sum_{i=1}^{n}\left| x_{i}-y_{i} \right|^p \right)^{1/p}$ on $\mathbb{R}^n.$
---
> [!lemma] Proposition 2
> Let $(X,d)$ be a complete metric space. For a subset $A \subseteq X$, the following are equivalent: 
> 1. the closure $\overline{A}$ of $A$ is compact.
> 2. $A$ is totally bounded, i.e. for all $\varepsilon>0$, there exists a finite set $F \subseteq A$ s.t. $$A\subseteq \bigcup_{x\in F}^{}\overline{B(x,\varepsilon)}$$

> [!proof] Proof Missing

---
> [!lemma] Proposition 1
> Let $X$ be a set and $d_{1},d_{2}$ two distances on $X$. If there exist $a,b>0$ s.t.$$\quad d_{1}(x,y)^a\leq d_{2}(x,y)\leq d_{1}(x,y)^b,\quad \forall(x,y)\in X\times X$$Then the topologies coincide.

> [!proof]-
> Let $U\subseteq \mathcal{T}_{d_{1}}$. Then, for any $x\in X$, there exists $r>0$ s.t. $B^1_{<r}(x)\subseteq U$. Consider $B^2_{<r^{1/a}}(x)$. We have:$$B^2_{<r^{1 /a}}(x)=\{ y\in X:d_{2}(x,y)<r^{1/a} \}\subseteq \{ y\in X:d_{1}(x,y)<r \}=B^1_{<r}(x)\subseteq U$$Therefore, $U\subseteq \mathcal{T}_{d_{2}}$. The opposite inclusion holds by symmetry.


---
##### Examples
> [!h] Example 1
> A metric space $X$ is discrete if $d(x,y)=\delta_{xy}$ as $\{ x \}=B_{<1/2}(x)$.
---
> [!h] Example 2 
> For a metric space $(X,d)$, $$\delta(x,y)= \frac{d(x,y)}{1+d(x,y)}$$is a distance on $X$. Further, 
> 1. $\mathcal{T}_{d}=\mathcal{T}_{\delta}$.
> 2. $\delta\leq 1$.

> [!proof]-
> We have: 
> 1. **Showing $\delta$ is a distance**: The non-negativity, non-degeneracy and symmetry are clear from the definition. For triangle inequality, notice that for $a,b,c\geq 0$ s.t. $a\leq b+c$, we have: $$\frac{a}{1+a}\leq \frac{b+c}{1+b+c}=\frac{b}{1+b+c}+ \frac{c}{1+b+c}\leq \frac{b}{1+b}+\frac{c}{1+c}$$This shows the triangle inequality.
> 2. **Showing $\delta$ and $d$ define the same topology**: For any $x\in X$ and $r>0$, as $\delta(x,y)\leq d(x,y)$ (from the non-negativity of $d(x,y)$), $B_{<r}^d(x)\subseteq B_{<r}^\delta(x)$. On the other hand, $d(x,y)= \delta(x,y)/(1-\delta(x,y))$ and $B_{< \frac{r}{1-r}}^\delta(x)\subseteq B^\delta_{<r}(x)$. This shows that the topologies coincide.  
> 3. **Showing that $\delta(x,y)\leq 1$**: Indeed, $d(x,y)\leq 1+d(x,y)$ for all $x,y\in X\times X$.
---
> [!h] Example 3
> Let $X=\mathbb{R}^2$. Let $d$ denote the euclidean distance on $X$. Define for $(x,y)\in X\times X$, $$\delta(x,y)=\begin{cases}d(x,y)&\exists\lambda\in \mathbb{R}: y=\lambda x\\d(x,0)+d(0,y)&\text{otherwise}\end{cases}$$
> 1. $\delta$ is a distance on $\mathbb{R}^{2}$.
> 3. $\mathcal{T}_{d}\subseteq \mathcal{T}_{\delta}$.
> 4. $\mathcal{T}_{\delta}\not\subseteq \mathcal{T}_{d}$.

> [!proof]-
> We have:
> 1. The symmetry and non-negativity are clear from the definition. For non-degeneracy, if $x=y$, then $\delta(x,y)=d(x,y)=0$. If $\delta(x,y)=0$, then $d(x,y)=0$ and $x=y$ or $d(x,0)+d(0,y)=0$ with $x$ not proportional to $y$, which cannot happen. Lastly, for triangle inequality, let $x,y,z\in \mathbb{R}^{2}$. Firstly, by triangle inequality of $d$, notice that $d(x,y)\leq\delta(x,y)$. If $x$ and $z$ are proportional, $$\delta(x,z)=d(x,z)\leq d(x,y)+d(y,z)\leq\delta(x,y)+\delta(y,z)$$If $x$ and $z$ are not proportional, by transitivity of proportionality, $y$ is not proportional to at least one of $x,z$. Wlog assume $y$ is not proportional to $x$. Then, $$\delta(x,z)=d(x,0)+d(0,z)\leq d(x,0)+d(0,y)+d(y,z)\leq\delta(x,y)+\delta(y,z)$$This proves the statement.
> 2. For $y,z\in \mathbb{R}^{2}$, let $[y:z]$ define the line that goes through $y$ and $z$. Then, geometrically we can consider the ball as follows: $$B_{<r}^\delta(x)=([0:x]\cap B_{<r}^d(x))\cup (B_{<r-d(x,0)}(0)\backslash [0:x])$$ where $B_{<\varepsilon}(0)=\varnothing$ for $\varepsilon\leq 0$. In other words, the open balls are a union of a line segment of length $2r$ that goes centered at $x$ and an open ball at $0$ with radius $r-d(x,0)$ minus the line that goes through the origin and $x$, if $r-d(x,0)$ is positive.
> 3. Let $U\in \mathcal{T}_{d}$. Then, for $x\in U$, there exists $r>0$ s.t. $B^d_{<r}(x)\subseteq U$. 
   If $x=0$, then, $B^\delta_{r}(x)=B^d_{r}(x)\subseteq U$. Otherwise, let $\varepsilon:=\min\{ r,d(x,0)\}>0$. Then, $$B_{<\varepsilon}^\delta(x)=[0:x]\cap B_{<\varepsilon}^d(x)\subseteq B_{<r}^d(x)\subseteq U$$
> 4. Consider $B^\delta_{1}((2,0))$, which is equal to a line segment between $(1,0)$ and $(3,0)$. This is clearly not open in the Euclidean space.
---
