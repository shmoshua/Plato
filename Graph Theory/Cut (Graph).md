#Definition #GraphTheory 

> [!definition]
> Let $G:=(V,E)$ be a [[graph]]. A ***cut*** is $(A,B)$ s.t. $A\sqcup B=V$. 

^27b1e1

- **Related definition**: For a cut $(A,B)$, a ***cut set*** is defined as $E\cap (A\times B)$. 
- **Related definition**: For a weight function $w:E \to \mathbb{R}$, the ***(weighted) value*** of $(A,B)$  is defined as $c_{w}(A,B):=\sum_{e\in E\cap (A\times B)}^{}w(e)$. 
- **Related definition**: For $s,t\in V$, a cut is an ***$(s,t)$-cut*** if $s\in A$ but $t\notin A$.
- **Related definition**: A ***minimum $(s,t)$-cut*** is an $(s,t)$-cut with the least number of edges in the cut set. 
---
##### Properties

> [!lemma] Theorem 1 (Max-cut)
> Let $G:=(V,E)$ be a graph with $m$ edges. Then
> 1. $\max_{(A,B),A\sqcup B = V}e(A,B)\geq m / 2$.

^b245ae

> [!proof]-
> We will assign the vertices into $A$ and $B$ uniformly randomly independently. Let $X=\sum_{e\in E}^{}\mathbb{1}_{\{ \left| e\cap A \right|=1\}}$. Then:
> 1. **Claim 1: $\mathbb{E}[X] = m / 2$**
>    $\mathbb{P}(\left| e\cap A \right|=1\lor \left| e\cap B \right|=1)=\frac{1}{2}$. Therefore, $\mathbb{E}[X]=\sum_{e\in E}^{} \frac{1}{2}=\frac{m}{2}$. 
>    
>  Or one can simply make sure that we move the vertices until they have more than half of its neighbors on the other side.

^b83c9a

- **Remark**: Maxcut $\geq m / 2+c\sqrt{ m }$. 
---

> [!lemma] Theorem 2 (Karger)
> Let $s$ be the size of the minimal cut set. Then, for all $\alpha\geq 1$, 
> 1. the number of cut set of size $\leq\alpha s$ is $\leq n^{2\alpha}$
---
> [!lemma] Theorem 3 (LP)
> Considering the following LP: 
> $$\begin{array}{rll}\text{min}&\sum_{\{ u,v \}\in E}^{} d_{uv}\\\text{subject to}&d_{uv}\geq 0& \forall u,v\in V\\&d_{uv}=d_{uv}&\forall u,v\in V\\&d_{uv}\leq d_{uw}+d_{wv}&\forall u,v,w\in V\\&d_{st}=1\end{array}$$
> Let $d^{*}$ be the optimum and let $(S^{*}, V \backslash S^{*})$ be the minimum $(s,t)$ cut. 
> 1. $\sum_{\{ u,v \}\in E}^{}d^{*}_{e}=\sum_{\{ u,v \}\in E}^{}\left| \chi_{S^{*}} (u)-\chi_{S^{*}}(v)\right|$
> 
---

$$$$