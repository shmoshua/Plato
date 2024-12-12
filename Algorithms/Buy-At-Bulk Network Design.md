#Definition #Algorithms 

> [!definition]
> Let $G=(V,E)$ be a [[graph]] with $w: E\to \mathbb{R}_{\geq 0}$ edge weights. Let $f:\mathbb{R}_{\geq 0}\to \mathbb{R}_{\geq 0}$ further be a sub-additive cost function, i.e. $f(x+y)\leq f(x)+f(y)$. Given $k$ commodity triplets $(s_{i},t_{i},d_{i})\in V\times V\times \mathbb{R}_{\geq 0}$, the ***buy-at-bulk network design problem*** aims to find $c:E\to \mathbb{R}_{\geq 0}$ s.t.
> 1. $\sum_{e\in E}^{}f(c_{e})w_{e}$ is minimized.
> 2. there is a [[Flow (Graph)|flow]] $g: E\to \mathbb{R}_{\geq 0}$ meeting the demands $d_1,\dots,d_{k}$ and capacity $c$.

^a1f6f3

---
##### Properties
> [!lemma] Theorem 1 (Tree Embedding)
> Consider the following algorithm:
> ```pseudo
> \begin{algorithm}\caption{NetworkDesign($G=(V,E)$)}
> \begin{algorithmic} 
> \State $c\gets 0$
> \State $T\gets$ \Call{TreeEmbedding}{$G$}
> \State $T\gets$ \Call{Contract}{$T$}
> \For{$i\in\{ 1,\dots,k \}$}
> \State $p_{i}\gets$ shortest $s_{i}$-$t_{i}$ path in $T$
> \For{$e\in p_{i}$}
> \State $q_{u,v}\gets$ shortest $u$-$v$-path in $G$
> \State $c_{e'}\gets c_{e'}+d_{i}$ for each $e'\in q_{u,v}$
> \EndFor
> \EndFor
> \Return $c$
> \end{algorithmic}
> \end{algorithm}
> ```

^2e1b3e

---
