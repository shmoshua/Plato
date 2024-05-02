#Definition #Analysis #FunctionalAnalysis 

> [!definition]
> For a [[normed space|normed space]] $(V,\|\cdot\|)$, the ***dual space*** $V^{*}$ of $V$ is the set of all [[Bounded Linear Map|bounded linear maps]] $\mathcal{A}:V \to \mathbb{K}$, denoted by $\mathcal{B}(V,\mathbb{K})$.
- **Remark**: For any normed space $(V,\|\cdot\|)$, $V^*$ is a [[Banach Space|Banach space]]. Check [[Bounded Linear Map|here]].
---
##### Properties
> [!lemma] Corollary 1 (from Hahn-Banach)
> Let $(V,\|\cdot\|)$ be a [[Analysis/Normed Space|normed space]] and $0\neq v_{0}\in V$. Then, there exists $f_{0}\in V^*$ with:
> 1. $\left\| f_{0} \right\|=1$
> 2. $f_{0}(v_{0})=\left\| v_{0} \right\|$

> [!proof]-
> Let $M:=\mathbb{K}v_{0}$ and $f:M \to \mathbb{K}$ be $f(tv_{0})=t\left\|v_{0} \right\|$. Then, $$\left\| f \right\| =\sup_{\|tv_{0}\|\leq 1}|t|\|v_{0}\|=\sup_{|t|\|v_{0}\|\leq 1}|t|\|v_{0}\|=1$$
> 
> Then, by [[Bounded Linear Map|Corollary 3]], there exists $f_{0}\in V^{*}$ with $\left. f_{0} \right|_{M}=f$, in particular $f_{0}(v_{0})=f(v_{0})=\left\| v_{0} \right\|$ and $$\left\| f_{0} \right\| =\left\| f \right\| =1$$
---
> [!lemma] Corollary 2
> Let $(V,\|\cdot\|)$ be a [[Analysis/Normed Space|normed space]]. Then, for all $v\in V$:$$\|v\|=\sup \{ |f(v)|:f\in V^{*}, \|f\|\leq 1 \}=\max \{ |f(v)|:f\in V^{*}, \|f\|\leq 1 \}$$

> [!proof]-
> Firstly, if $\left\| f \right\|\leq 1$, then $\left| f(v) \right|\leq \left\| f \right\|\|v\|\leq\|v\|$. But, from Corollary 1, we know this is also a maximum.
---
> [!lemma] Corollary 3 (from Banach-Steinhaus)
> Let $E$ be a [[normed space]] and $B\subseteq E$ be a subset s.t. for all $f\in E^{*}$, $f(B)\subseteq \mathbb{K}$ is bounded. Then, $B\subseteq E$ is bounded.

> [!proof]-
> Let $V = E^{*}$, $W=\mathbb{K}$ and $\Lambda=B$. We define for all $v\in B$: $$\begin{array}{cccc} {T_{v}:}&{E^{*}}&\to&{\mathbb{K}}\\&{f} &\mapsto & {f(v)} \end{array}{}$$Then, from the assumption, $\sup_{v\in B}\left| T_{v}(f) \right|<+\infty$ for all $f\in E^*$. By [[Bounded Linear Map|Banach-Steinhaus]], $$\sup_{v\in B}\left\| T_{v} \right\| <+\infty$$However, $$\left\| T_{v} \right\| =\sup_{\left\| f \right\| \leq 1}\left| f(v) \right| =\|v\|$$Therefore, $$\sup_{v\in B}\|v\|<+\infty$$which proves that $B$ is bounded.
---
> [!lemma] Corollary 4 (from Banach-Steinhaus)
> Let $E$ be a [[Banach space]] and $B\subseteq E^{*}$ s.t. $$\{ f(x):f \in B \}\subseteq \mathbb{K}$$ is bounded for all $x\in E$. Then, $B\subseteq E^{*}$ is bounded.

> [!proof]-
> We have that $\sup_{f\in B}\left| f(x) \right|<+\infty$ for all $x\in E$. Therefore, from Banach-Steinhaus, $$\sup_{f\in B}\left\| f \right\| <+\infty$$which shows that $B\subseteq E^{*}$ is bounded.
---
##### Examples

-  ***Locally compact Hausdorff spaces***: Let $X$ be a locally compact Hausdorff space. A continuous function $f:X \to \mathbb{K}$ is said to vanish at infinity, if for all $\varepsilon>0$, there exists a compact subset $K \subseteq X$ s.t. $$\left| f(x) \right| <\varepsilon$$for all $x\in X \backslash K$. Let $$C_{0}(X,\mathbb{C})=\{ f:X \to \mathbb{C},\text{ continuous and vanishing at }\infty \}$$Then, $(C_{0}(X,\mathbb{C}),\|\cdot\|_{\infty})$ is a [[Banach Space|Banach space]]. Then, the dual is described by the space of complex measures.
---
##### Related Definitions
- [[Bidual Space]]