#Definition #Algebra 

> [!definition]
> Let $A$ be a set and a binary operation $\circ:A\times A\to A$. 
> 1. $(A,\circ)$ is a ***semigroup*** if $\circ$ is associative.

---
##### Properties

> [!lemma] Proposition 1
> A finite semigroup has an idempotent element.

> [!proof]-
> Let $s\in A$. Then, there exists $k>0$ s.t. $s^p=s^{p+k}$. Hence, $$s^{p+k}=s^k s^p=s^{p+2k}$$and therefore, $s^p=s^{p+mk}$ for all $m$.
> 
> Now, choose $r>0$ s.t.  $p+r=0$ mod $k$. Then, $$(s^{p+r})^{2}=s^{p+r+p+r}=s^{p+r+mk}=s^{p+r}$$