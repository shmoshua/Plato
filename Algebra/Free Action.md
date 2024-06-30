#Definition #Algebra 

> [!definition]
> A [[group action]] $G\curvearrowright X$ is ***free*** if for every $x\in X$, 
> 1. for all $g\neq e$, $gx\neq x$, i.e. $\text{St}_{G}(x)=\{ e \}$.

---
##### Properties
> [!lemma] Lemma 1
> Let $G\curvearrowright X$ be a group action. TFAE:
> 1. the action is free.
> 2. for $x, y\in X$, there exists at most 1 element $g\in G$ s.t. $gx=y$. 

> [!proof]-
> Assume there are two elements $g,h$. Then, $$gh^{-1}(y)=g(x)=y$$which is a contradiction.
> 
> Conversely, let $x\in X$. if there is $g\neq e$ s.t. $gx=x$, this is a contradiction as $ex=x$ as well.
---
