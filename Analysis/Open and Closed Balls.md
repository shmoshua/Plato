#Definition #LST #Analysis 

> [!definition]
> In a [[Metric Space|metric space]] $(X,d)$, the ***open ball*** of radius $r>0$ centered at $x\in X$ is the set: $$B_{<r}(x)=\{ y\in V :d(x,y) <r\}$$ 
> Similarly, the ***closed ball*** of radius $r>0$ centered at $x\in X$ is the set: $$B_{\leq r}(x)=\{ y\in V :d(x,y) \leq r\}$$ 
> The ball $B(0,1)$ is called the ***unit ball*** of $(V,F,\|\cdot\|)$.
---
##### Properties
> [!lemma] Proposition 1
> Every closed ball is a closed set.

> [!proof]-
> Consider $\overline{B}(x,r)$. Then, to show that $X \backslash \overline{B}(x,r)$ is open, let $y\in X \backslash \overline{B}(x,r)$. Then, $d(x,y)>r$ and $d(x,y)-r>0$.  Further, $B(y,d(x,y)-r)\subseteq X \backslash \overline{B}(x,r)$. Therefore, $X \backslash \overline{B}(x,r)$ is open and $\overline{B}(x,r)$ is closed.
---
##### Related Definitions
- [[Topology of Metric Spaces]]
- [[Bounded Sets]]