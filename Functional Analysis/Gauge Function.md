#Definition #FunctionalAnalysis 

> [!definition]
> A ***gauge*** on a $\mathbb{R}$-vector space $V$ is a function $p:V \to \mathbb{R}$ s.t.:
> 1. $p(\lambda x)=\lambda p(x)$ for all $\lambda>0$,
> 2. $p(x+y)\leq p(x)+p(y)$ for all $x,y\in V$.
- **Remark**: for all $r \in \mathbb{R}$, the sub-levels $\{ v\in V:p(v)<r \}$ and $\{ v\in V:p(v)\leq r \}$ are [[Convex Set|convex]].
---
##### Properties

> [!lemma] Theorem 1 (Hahn-Banach, the Analytic Form)
> Let $V$ be a $\mathbb{R}$-vector space, $p:V \to \mathbb{R}$ a gauge function. For a subspace $M \subseteq V$, if $f:M \to \mathbb{R}$ is a linear form with $$f(v)\leq p(v)$$for all $v\in M$, then there exists a linear extension $F:V \to \mathbb{R}$ of $f$ with:
> 1. $F$ is linear
> 2. $F|_{M}=f$ and
> 3. $F(v)\leq p(v)$ for all $v\in V$.

> [!proof]-
> We have the following steps:
> 1. **Defining $\mathcal{P}$:**
> Let us define$$\mathcal{P}:=\{ (h,D):M\subseteq D \subseteq V\ \mathbb{R}\text{-linear subspace}, h:D \to \mathbb{R} \text{ linear}, \left. h \right|_{M}=f, h\leq p \text{ on } D\}$$We then define an ordering on $\mathcal{ P}$ as follows: $$(h_{1},D_{1})\leq(h_{2},D_{2}) \iff D_{1}\subseteq D_{2}\land h_{2}|_{D_{1}}=h_{1}$$
> We will now show that we can use [[Poset|Zorn's lemma]] on $\mathcal{P}$.
> 2. **Showing that $(\mathcal{P},\leq)$ is a non-empty inductive [[Poset|poset]].**
> 	1. As $(f,M)\in \mathcal{P}$, $\mathcal{P}\neq \varnothing$.
> 	2. Let $Q \subseteq \mathcal{P}$ be a totally ordered. Then, we define: $$E:=\bigcup_{(h,D)\in Q}^{}D$$Since $Q$ is totally ordered, $E$ is a $\mathbb{R}$-vector subspace of $V$. 
> 	   
> 	   Now, define $j: E \to \mathbb{R}$ by $\left. j \right|_{D}=h$ whenever $(h,D)\in Q$. Then, $(j,E)\in \mathcal{P}$ and this is an upper bound for $Q$. 
> 3. **Finding the linear extension $F$**:
> 	By Zorn's lemma, we have a maximal element $(F,E)\in \mathcal{ P}$. All we have to show is that $E=V$.
> 
> 	Assume that $E \neq V$. Let $x_{0} \in V \backslash E$ and $D:=E + \mathbb{R}x_{0}$. Further, define $h:D \to \mathbb{R}$ s.t. for all $v\in E$: $$h(v+tx_{0})=F(v)+\alpha t$$We now will choose $\alpha\in \mathbb{R}$ in such a way, that $h \leq p$ on $D$. In other words, we need $\alpha$ s.t. $$F(v)+\alpha t\leq p(v+tx_{0})$$for all $v\in E$ and $t\in \mathbb{R}$. Using the homogeneity of $p$, we can prove instead that:
> 	1. $F(v)+\alpha\leq p(v+x_{0})$ for all $v\in E$
> 	2. $F(v)-\alpha\leq p(v-x_{0})$ for all $v\in E$
>    
> 	Then, we have: $$F(v)+\alpha t=|t|(F(v / |t|)+\text{sgn}(t)\alpha)\leq \left| t \right| p(v/ \left| t \right| +\text{sgn}(t)x_{0})=p(v+tx_{0})$$
> 
> 	To show the existence of $\alpha$ that meet 1 and 2, we must show that: $$\sup_{y\in E}\{ F(y)-p(y-x_{0}) \}\leq \inf_{x\in E}\{ p(x+x_{0})-F(x) \}$$or equivalently, for all $x,y\in E$:$$F(y)-p(y-x_{0})\leq p(x+x_{0})-F(x)$$ However, we have that: $$\begin{align}F(x)+F(y)=F(x+y)\leq p(x+y)=p((x+x_{0})+(y-x_{0}))\leq p(x+x_{0})+p(y-x_{0})\end{align}$$This concludes the proof.
---
> [!lemma] Proposition 2
> Let $E$ be a $\mathbb{R}$-vector space and $A\subseteq E$ a [[Convex Set|convex]] and [[Absorbant Set|absorbant]] set with $0\in A$. Then, the function: $$p_{A}(v):=\inf\{ \rho>0:v\in \rho A \}$$is a gauge in $E$ for which it further holds that: 
> 1. $\{ v\in E: p_{A}(v)<1 \}\subseteq A\subseteq \{ v\in E:p _{A}(v)\leq 1 \}$
> 2. If $A\subseteq B$ and $B$ is convex and absorbant, then $p_{B}\leq p_{A}$.
> 
> Further, if $A$ is open, $\{ v\in E: p_{A}(v)<1 \}= A$

> [!proof]-
> Firstly, $p_{A}$ is well-defined as $A$ is absorbant. 
> 1. Let $v\in E$ and $\lambda>0$. Then, $v\in \rho A \iff\lambda v\in \lambda \rho A$. Therefore, $$p_{A}(\lambda v)=\lambda p_{A}(v)$$
> 2. If $v,w\in E$, and $\lambda>0$, $\rho>0$ s.t. $p_{A}(v)<\rho$ and $p_{A}(w)<\lambda$. By definition, $v\in \rho A$ and $w\in \lambda A$. This means there exists $x,y\in A$ s.t. $$v=\rho x,\quad w=\lambda y$$
> 	From convexity, we then have: $$v+w=\rho x+\lambda y=(\rho +\lambda)\left( \frac{\rho}{\rho+\lambda}x+\frac{\lambda}{\rho + \lambda}y \right)\in (\rho+  \lambda) A$$Therefore, $p_{A}(v+w)\leq \rho +\lambda$ for every $\rho>p_{A}(v)$ and $\lambda>p_{A}(w)$. This shows that $p_{A}(v+w)\leq p_{A}(v)+p_{A}(w)$.
> 3. We first show: $A\subseteq \{ v\in E: p_{A}(v)\leq 1 \}$. For $v\in A$, we have that $p_{A}(v)\leq 1$. Conversely, if $v\in E$ s.t. $p_{A}(v)<1$, then pick $p_{A}(v)<\lambda<1$. Hence, $v\in \lambda A$ and there exists $x\in A$ s.t. $$v=\lambda x=\lambda x+(1-\lambda)0\in A$$
> 4. If there exists $v\in E$ for which $p_{A}(v)<p_{B}(v)$, choose $\rho$ between the two values, then we have: $$v\in \rho A\subseteq \rho B$$ and this is a contradiction.
> 5. We have to show that if $A$ is open $A\subseteq \{ v\in E:p_{A}(v)<1 \}$. Let $v\in A$. Then, as $A$ is open, there exists $\varepsilon>0$ s.t. $tv\in A$ for all $t\in[1-\varepsilon,1+\varepsilon]$.
>    
>    In particular, $(1+\varepsilon)v\in A$ and $v\in \frac{1}{1+\varepsilon}A$. Therefore, $p_{A}(v)\leq \frac{1}{1+\varepsilon}<1$.
---
> [!lemma] Proposition 3
> Let $V$ be a [[Topological Vector Space with Seminorms|topological vector space with seminorms]] $\{ \|\cdot\|_{a} \}_{a\in B}$.  Then, let: $$A=N(0,F,\varepsilon)=\{ v\in V:\max_{a\in F} \|v\|_{a}<\varepsilon\}$$where $F$ is finite and $\varepsilon>0$. Then, $$p_{A}(v)= \frac{1}{\varepsilon}\max_{a\in F}\|v\|_{a}$$

> [!proof]-
> As $A$ is open and $0\in A$, by [[Absorbant Set|Lemma 1]], $A$ is absorbant, therefore $p_{A}$ is well-defined. Now, let $\rho>0$. Then, $$\begin{align}v\in \rho A &\iff v\in \rho N(0,F,\varepsilon)\\&\iff \frac{v}{\rho}\in N(0,F,\varepsilon)\\&\iff\max_{a\in F}\frac{\|v\|_{a}}{\rho}<\varepsilon\\&\iff \frac{1}{\varepsilon}\max_{a\in F}\|v\|_{a}<\rho\end{align}$$Therefore, we have that $p_{A}(v)=\frac{1}{\varepsilon}\max_{a\in F}\|v\|_{a}$.
---
##### Examples
