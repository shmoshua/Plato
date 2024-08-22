#Definition #LieGroups 

> [!definition]
> In a [[Locally Compact Group|LCH group]] $G$, a ***lattice*** is a subgroup $\Gamma\leq G$ s.t. 
> 1. $\Gamma$ is discrete
> 2. there exists a finite $G$-invariant regular Borel measure on $G / \Gamma$.
---
> [!lemma] Proposition 1
> Let $G$ be an LCH group and $\Gamma\leq G$ a lattice. Then, $G$ is [[Unimodular Group|unimodular]].

^58e178

> [!proof]-
> By definition, there exists a finite $G$-invariant regular Borel measure $\mu_{G / \Gamma}$ on $G / \Gamma$. Then, by [[Homogeneous Space|Weil's formula]], $\Delta_{G}|_{\Gamma}=\Delta_{\Gamma}=1$ as $\Gamma$ is discrete. Therefore, $\Gamma\leq\text{ker }\Delta_{G}$ and we can factor $\Delta_{G}=\Delta \circ p$ where $\Delta:G / \Gamma\to \mathbb{R}_{>0}$. Further, for $g\in G$ and $x\in G / \Gamma$, we have: $$\Delta(gx)=\Delta_{G}(g)\Delta(x)$$Now, consider the pushforward $\Delta_{*}(\mu_{G / \Gamma})$ is a finite measure. Further, the measure is $\Delta_{G}(G)$-invariant as for $g\in G$: $$\mu_{G / \Gamma}(\Delta ^{-1}(\Delta_{G}(g)E))=\mu_{G / \Gamma}(g\Delta ^{-1}(E))=\mu_{G / \Gamma}(\Delta ^{-1}(E))$$ However, there are no finite measures on $\mathbb{R}_{>0}^\times$ which are invariant under a non-trivial subgroup. Therefore, $\Delta_{G}(G)=\{ 1 \}$. 

^5ab53c

---
##### Examples
> [!h] Example 1 (Rn)
> Let $\mathcal{R}$ be the set of all lattices on $\mathbb{R}^n$. For a subgroup $\Gamma\leq \mathbb{R}^n$, TFAE:
> 1. $\Gamma\in \mathcal{R}$
> 2. there exists a basis $f_{1},\dots,f_{n}\in \mathbb{R}^n$ s.t. $\Gamma=\mathbb{Z}f_{1}+\dots+\mathbb{Z}f_{n}$.

> [!proof]-
> We have that:
> 1. (1=>2): Let $\Gamma\leq \mathbb{R}$ non-empty. We will show that $\Gamma$ is dense or $\Gamma=a\mathbb{Z}$ for $a\in \mathbb{R}$. As it is non-empty, there exists $x\in \Gamma$ s.t. $x>0$. Let $y\in \mathbb{R}$ and $n_{y}$ be the largest integer s.t. $n_{y}x\leq y<(n_{y}+1)x$. Then, $\left| n_{y}x-y \right|\leq x$ and as $n_{y}x\in \Gamma$, therefore, let $a:=\inf\{ x\in \Gamma: x>0 \}$ and if $a=0$, then $\Gamma$ is dense.
> 
> 	If $a>0$, then $a\in \Gamma$. Otherwise, there exists $b\in \Gamma$ s.t. $b<2a$. As $b\neq a$, there exists $c\in \Gamma$ with $a<c<b$ as well. Then, $a>b-c>0$ and $b-c\in \Gamma$ which is a contradiction. Then, $\Gamma=a\mathbb{Z}$. Indeed, if $b\in \Gamma$ is not in a form of $an$, then there exists $n$ with $0<b-an<a$ and this is a contradiction to the minimality of $a$. This proves the statement.
> 
> 	We will now use induction on $n$. Let $0\neq a\in \Gamma$. Then, $\Gamma \cap a\mathbb{R}$ is a discrete subgroup of $a\mathbb{R}$ and therefore, there exists $b\in \Gamma \cap a\mathbb{R}$ s.t. $\Gamma \cap a\mathbb{R}=b\mathbb{Z}$. Let $\Gamma'=p(\Gamma )$ where $p:\mathbb{R}^n\to \mathbb{R}^n /a\mathbb{R}$. 
> 
> 	We claim that $\Gamma'$ is a lattice in $\mathbb{R}^n / a\mathbb{R}$. Firstly, it is discrete: otheriwse, there exists a sequence $x_{j}\in \Gamma$ s.t. $x_{j}+a\mathbb{R}\to a\mathbb{R}$. In other words, there exists $\ell_{j}\in a\mathbb{R}$ s.t. $x_{j}-\ell_{j}\to 0$. Select $y_{j}\in \Gamma \cap a\mathbb{R}$ such that $\ell_{j}-y_{j}\in [0,b]$. Passing to a subsequence we may assume that $\ell_{j}-y_{j}$ converges to some $\ell\in a\mathbb{R}$. But then $x_{j}-y_{j}=(x_{j}-\ell_{j})+(\ell_{j}-y_{j})$ converges to $\ell$ as well. Because $x_{j},y_{j}\in \Gamma$, we get $x_{j}-y_{j}\in \Gamma$ and the discreteness of $\Gamma$ now implies that $x_{j}-y_{j}=\ell$ for $j$ sufficiently large. However $y_{j}\in a\mathbb{R}$ and $\ell\in a\mathbb{R}$ now leads to $x_{j}\in a\mathbb{R}$, for $j$ sufficiently large, a contradiction. 
> 
> 	As $\mathbb{R}^n$ is abelian, $\Gamma\unlhd \mathbb{R}^n$ and   $\mathbb{R}^n / \Gamma$ is a topological group. Therefore, by [[Haar Measure|Proposition 4]], $\mathbb{R}^n / \Gamma$ is compact. Therefore, $(\mathbb{R}^n / a\mathbb{R}) / \Gamma'$ is compact as a continuous image of the production, $x+\Gamma\mapsto p(x)+\Gamma'$. Therefore, $\Gamma'$ is a lattice and by induction hypothesis, there exists a basis $g_{1},\dots,g_{n-1}\in \mathbb{R}^{n-1}$ and $f_{1}+a\mathbb{R},\dots,f_{n-1}+a\mathbb{R}\in \mathbb{R}^n / a\mathbb{R}$ linearly independent s.t. $\Gamma'=\mathbb{Z} f_{1}+\dots+\mathbb{Z}f_{n-1}+a\mathbb{R}$. Therefore, by setting $f_{n}:=b$, we have that: $$\Gamma=\mathbb{Z}f_{1}+\dots+\mathbb{Z}f_{n}$$ 
> 
> 2. (2=>1): The other direction is obvious as $\mathbb{Z}f_{1}+\dots+\mathbb{Z}f_{n}$ is discrete and as $\Gamma\cong \mathbb{Z}^n$. Therefore, $\mathbb{R}^n / \Gamma\cong \mathbb{R}^n / \mathbb{Z}^n\cong (\mathbb{R} / \mathbb{Z})^n$ which is compact and therefore has a finite Haar measure.
---
> [!h] Example 2 
> Let $F_{\{ a,b \}}$ be the [[Free group]] generated on two generators $a,b$. Then, 
> 1. $F_{\{ a,b \}}$ is countable and 
> 2. $F_{\{ a,b \}}$ is a LCH group with the discrete topology.
> 3. Then, $F_{\{ a,b \}}$ is a lattice of itself.
---
> [!h] Example 3
> Consider $G:=(\mathbb{R}_{>0},\cdot)$. Then, 
> 1. $\Gamma:=\exp(\mathbb{Z})$ is a discrete subgroup of $G$.
> 2. $\Gamma$ is a lattice.

> [!proof]-
> As $G$ and $\Gamma$ are both abelian, they are unimodular and $\Delta_{G}|_{\Gamma}=\Delta_{\Gamma}=1$. Therefore, we can use [[Homogeneous Space|Weil's formula]]. Therefore, there exists a unique $G$-invariant regular Borel measure $\mu$ on $G / \Gamma$ s.t. :$$\int_{\mathbb{R}_{>0}}\frac{f(x)}{x}  \, dx=\int_{G / \Gamma} \left( \sum_{\gamma\in \Gamma}^{}f(g\gamma) \right) \, d\mu(g\Gamma)  $$Choose $f=\chi_{[1,e)}$. Then, $$\int_{1}^{e} \frac{1}{x} \, dx=\int_{G / \Gamma}^{} \left( \sum_{n\in \mathbb{Z}}^{}\chi_{[1,e)}(g\cdot \exp(n)) \right)  \, d\mu(g\Gamma)=\int_{G / \Gamma}^{} 1  \, d\mu(g\Gamma) =\mu(G / \Gamma) $$Therefore, $\Gamma$ has a finite $G$-invariant regular Borel measure. This shows that $\Gamma$ is a lattice.
---
