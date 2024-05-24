#Definition #LieGroups 

> [!definition]
> In a [[Locally Compact Topological Group|LCH group]] $G$, a ***lattice*** is a subgroup $\Gamma\leq G$ s.t. 
> 1. $\Gamma$ is discrete
> 2. there exists a finite $G$-invariant regular Borel measure on $G / \Gamma$.
---
##### Examples
> [!h] Example 1 (Rn)
> Let $\mathcal{R}$ be the set of all lattices on $\mathbb{R}^n$. For a subgroup $\Gamma\leq \mathbb{R}^n$, the following are equivalent:
> 1. $\Gamma\in \mathcal{R}$
> 2. there exists a basis $f_{1},\dots,f_{n}\in \mathbb{R}^n$ s.t. $\Gamma=\mathbb{Z}f_{1}+\dots+\mathbb{Z}f_{n}$

> [!proof]+
> Let $\Gamma\leq \mathbb{R}$ non-empty. We will show that $\Gamma$ is dense or $\Gamma=a\mathbb{Z}$ for $a\in \mathbb{R}$. As it is non-empty, there exists $x\in \Gamma$ s.t. $x>0$. Let $y\in \mathbb{R}$ and $n_{y}$ be the largest integer s.t. $n_{y}x\leq y<(n_{y}+1)x$. Then, $\left| n_{y}x-y \right|\leq x$ and as $n_{y}x\in \Gamma$, therefore, let $a:=\inf\{ x\in \Gamma: x>0 \}$ and if $a=0$, then $\Gamma$ is dense.
> 
> If $a>0$, then $a\in \Gamma$. Otherwise, there exists $b\in \Gamma$ s.t. $b<2a$. As $b\neq a$, there exists $c\in \Gamma$ with $a<c<b$ as well. Then, $a>b-c>0$ and $b-c\in \Gamma$ which is a contradiction. Then, $\Gamma=a\mathbb{Z}$. Indeed, if $b\in \Gamma$ is not in a form of $an$, then there exists $n$ with $0<b-an<a$ and this is a contradiction to the minimality of $a$. This proves the statement.
> 
> We will use induction on $n$. Let $0\neq a\in \Gamma$. Then, $\Gamma \cap a\mathbb{R}$ is a discrete subgroup of $a\mathbb{R}$ and therefore, there exists $b\in \Gamma \cap a\mathbb{R}$ s.t. $\Gamma \cap a\mathbb{R}=b\mathbb{Z}$. Let $\Gamma'=p(\Gamma )$ where $p:\mathbb{R}^n\to \mathbb{R}^n /a\mathbb{R}$. 
> 
> We claim that $\Gamma'$ is discrete. For $x\in \Gamma$, $$p ^{-1}(x+a\mathbb{R})=\Gamma \cap$$
> 
> Let $\Gamma\in \mathcal{R}$. Then, 