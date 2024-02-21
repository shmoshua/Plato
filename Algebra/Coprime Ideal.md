#Definition #Algebra

> [!definition]
> Let $R$ be a non-trivial [[ring]]. Two [[Ideal|ideals]] $\mathfrak{a}, \mathfrak{b}\subseteq R$ are ***coprime*** if $\mathfrak{a}+\mathfrak{b}=R$.
---
##### Properties
> [!lemma] Lemma 1
> Let $R$ be a commutative ring. If $\mathfrak{a},\mathfrak{b}\subseteq R$ are coprime, $\mathfrak{a}\cdot \mathfrak{b}=\mathfrak{a}\cap \mathfrak{b}$.

> [!proof]-
> The inclusion $\subseteq$ trivially holds. For the converse, let $x\in \mathfrak{a\cap \mathfrak{b}}$. As $\mathfrak{a,b}$ are coprime, $$1_{R}\in \mathfrak{a+b}\implies 1=y+z$$where $y\in \mathfrak{a}$ and $z\in \mathfrak{b}$. Then, $x=xy+xz\in\mathfrak{a\cdot b}$. 
---
> [!lemma] Proposition 2
> Let $R$ be a commutative ring. Then, for two coprime ideals $\mathfrak{a,b}\subseteq R$:$$R / \mathfrak{ab}\cong R / \mathfrak{a}\times R / \mathfrak{b}$$ 

> [!proof]-
> We define the following isomorphism: $$\begin{array}{cccc} {\varphi:}&{R}&\to&{R / \mathfrak{a}\times R / \mathfrak{b}}\\&{x} &\mapsto & {(x+\mathfrak{a},x+\mathfrak{b})} \end{array}{}$$Then, $\varphi$ is of course a homomorphism. 