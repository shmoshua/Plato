#Definition #MeasureTheory 

> [!definition]
> In $\mathbb{R}^n$, for $s\geq 0$, $\delta>0$, the ***$s$-dimensional Hausdorff measure of step $\delta$*** is defined as: $$\mathcal{H}^s_{\delta}(A):=\inf \left\{  \left. \sum_{k=1}^{\infty}r_{k}^s   \right| A \subseteq \bigcup_{k=1}^{\infty}B_{<r_{k}}(x_{k}),0 < r_{k}<\delta\right\}$$
> for $\varnothing \neq A \subseteq \mathbb{R}^n$, $\mathcal{H}^s_{\delta}(\varnothing)=0$. Then, the ***$s$-dimensional Hausdorff measure*** is defined as: $$\mathcal{H}^s(A):=\sup_{\delta >0}\mathcal{H}^s_{\delta}(A)=\lim_{ \delta \to 0 } \mathcal{H}^s_{\delta}(A)$$
>  The ***Hausdorff dimension*** of a set $A \subseteq \mathbb{R}^n$ is then defined as: $$\text{dim}_{\mathcal{H}}(A):=\text{inf}\{ s\geq 0:\mathcal{H}^s(A)=0 \}=\sup\{ s\geq 0:\mathcal{H}^s(A)=+\infty \}$$
- **Remark**: If $s >0$, allowing $r_{k}\geq0$ does not change the definition.
- **Remark**: $\mathcal{H}^s_{\delta}$ is non-increasing w.r.t. $\delta$.
- **Remark**: For all $A\subseteq \mathbb{R}^n$, $s_{0}:=\text{dim}_{\mathcal{H}}(A)$, $0\leq \mathcal{H}^{s_{0}}(A)\leq+\infty$. More importantly, $\text{dim}_{\mathcal{H}}(A)$ is not necessarily an integer.
---
##### Properties
> [!lemma] Proposition 1
> For all $s\geq 0$ and $\delta>0$, $\mathcal{H}^s_{\delta}$ is a measure. Consequently, $\mathcal{H}^s$ is a measure.
	
> [!proof]-
> Trivially, we have that $\mathcal{H}^s(\varnothing)=0$. Then, for any $A \subseteq \bigcup_{k=0}^{\infty}A_{k}$ and $\delta>0$, we have: $$\mathcal{H}^s_{\delta}(A)\leq \sum_{k=0}^{\infty}\mathcal{H}^s_{\delta}(A_{k})\leq \sum_{k=0}^{\infty}\mathcal{H}^s(A_{k})$$
> 	By taking $\delta \to {0}$, we have that: $\mathcal{H}^s(A)\leq \sum_{k=0}^{\infty}\mathcal{H}^s(A_{k})$.
---
> [!lemma] Theorem 2
> For $s\geq 0$, $\mathcal{H}^s$ is metric and [[Borel Measure|Borel regular]]. However, $\mathcal{H}^s_{\delta}$ is generally not Borel/metric.

> [!proof]-
> We will show:
> 1. **$\mathcal{H}^s$ is metric, and therefore Borel.**
> 	For all $A,B\in \mathbb{R}^n$, s.t. $\delta_{0}:=d(A,B)>0$, consider $0<\delta< \frac{\delta_{0}}{4}$. Then, there exists $x_{k},r_{k}$ s.t. $$A \cup B\subseteq\bigcup_{k=0}^{\infty}B_{<r_{k}}(x_{k})$$where $r_{k}<\delta$. Now consider:
> 	1. $\mathcal{A}:=\{ B_{<r_{k}}(x_{k}):B_{<r_{k}}(x_{k})\cap A\neq \varnothing \}$ and
> 	2. $\mathcal{B}:=\{ B_{<r_{k}}(x_{k}):B_{<r_{k}}(x_{k})\cap B\neq \varnothing \}$
> 	   
> 	Then, we observe that $\mathcal{A}\cap \mathcal{B}=\varnothing$ and therefore,$$\mathcal{H}^s_{\delta }(A)+\mathcal{H}^s_{\delta}(B)\leq \sum_{B(x_{k},r_{k})\in \mathcal{A}}^{}r^s_{k}+\sum_{B(x_{k},r_{k})\in \mathcal{B}}^{}r^s_{k}\leq \sum_{k}^{}r^s_{k}$$
> 	By taking the infimum over all coverings $B(x_{k},r_{k})$ of $A\cup B$, we get: $$\mathcal{H}^s_{\delta }(A)+\mathcal{H}^s_{\delta}(B)\leq \mathcal{H}^s_{\delta}(A\cup B)$$
> 	Therefore, by taking $\delta\to{0}$, $$\mathcal{H}^s(A)+\mathcal{H}^s(B)=\mathcal{H}^s(A\cup B)$$
> 3. **$\mathcal{H}^s$ is Borel regular.**
>     Let $A \subseteq \mathbb{R}^n$. If $\mathcal{H}^s(A)=\infty$, choose $B=\mathbb{R}^n$. Therefore, assume that $\mathcal{H}^s(A)<+\infty$. 
>     
>     For $\delta:=\frac{1}{\ell}$, choose a covering $\bigcup_{_{k}}^{}B_{<r_{k,\ell}}(x_{k}) \supseteq A$ with $r_{k,\ell}< \frac{1}{\ell}$ s.t. $$\sum_{k}^{}r_{k,\ell}^s\leq \mathcal{H}^s_{\frac{1}{\ell}}(A)+\frac{1}{\ell}$$ Set $B_{\ell}:=\bigcup_{_{k}}^{}B_{<r_{k,\ell}}(x_{k})$ and $B:=\bigcap_{\ell}^{}B_{\ell}$.  Then, $B\in \mathcal{B}(\mathbb{R}^n)$ with $A \subseteq B$. Most importantly, for all $\ell$, $$\mathcal{H}^s_{\frac{1}{\ell}}(A)\leq\mathcal{H}^s_{\frac{1}{\ell}}(B)\leq\mathcal{H}^s_{\frac{1}{\ell}}(B_{\ell})\leq \sum_{k}^{}r^s_{k,\ell}\leq \mathcal{H}^s_{\frac{1}{\ell}}(A)+\frac{1}{\ell}$$  
>     We let $\ell \to +\infty$ and get: $$\mathcal{H}^s(B)=\mathcal{H}^s(A)$$
---
> [!lemma] Proposition 3
> $\mathcal{H}^0$ is the counting measure.

> [!proof]-
> We will consider the two cases:
> 1. Let $A$ be finite. Then, $A=\{ x_{1},\dots,x_{k} \}\subseteq \mathbb{R}^n$. We now consider $\delta_{0}:=\inf_{i,j\in[k]}\left| x_{i}-x_{j} \right|$, the minimal distance between two points. Then, for all $0<\delta< \frac{\delta_{0}}{4}$, if $\{ z_{\ell},r_{\ell} \}_{{\ell\in I}}$  is a covering s.t. $$A \subseteq \bigcup_{\ell\in I}^{}B_{{<r_{\ell}}}(z_{\ell})$$then, $\left| I \right|\geq k$. Therefore, $\mathcal{H}^0_{\delta}(A)\geq k$. However, $\bigcup_{i=1}^{k}B_{<\delta}(x_{i})$ is a covering of $A$ with $k$ sets. Therefore, $\mathcal{H}^0_{\delta}(A)=k$ and $$\mathcal{H}^0(A)=\lim_{ \delta \to 0 } \mathcal{H}^0_{\delta}(A)=k$$
> 2. Let $A$ be infinite. Then, for all $k\geq 1$, there exists $A_{k} \subseteq A$ s.t. $\left| A_{k} \right|=k$. Therefore,
> 	$$\lim_{ k \to \infty } \mathcal{H}^0(A_{k})\leq \mathcal{H}^0(A)=\infty$$
---

> [!lemma] Lemma 4
> For $A \subseteq \mathbb{R}^n$ and $0 \leq s<t<\infty$, it holds that: 
> 1. $\mathcal{H}^s(A)<+\infty \implies \mathcal{H}^t(A)=0$ and
> 2. $\mathcal{H}^t(A)>0\implies \mathcal{H}^s(A)=+\infty$

>[!proof]-
>We will show them:
>1. Let $\mathcal{H}^s(A)<+\infty$.  Then, for $\delta>0$, let $A \subseteq \bigcup_{k}^{}B_{<r_{k}}(x_{k})$ with $r_{k }<\delta$. It holds that: $$\mathcal{H}_{\delta}^t(A)\leq \sum_{k}^{}r_{k}^t\leq \delta^{t-s}\sum_{k}^{}r_{k}^s$$By taking the infimum over all coverings, $$\mathcal{H}_{\delta}^t(A)\leq\delta^{t-s}\mathcal{H}_{\delta}^s(A)$$Let $\delta\to{0}$ and we get $\mathcal{H}^t(A)=0$.
>2. Follows from 1. 
---
> [!lemma] Proposition 5
> For all $A\subseteq \mathbb{R}^n$, $\mathcal{L}^n(A)=w_{n}\mathcal{H}^n(A)$.
---
> [!lemma] Proposition 6
> For all $s>n$ and $A \subseteq \mathbb{R}^n$, $\mathcal{H}^s(A)=0$.

> [!proof]-
> Using the [[Dyadic Cubes]], we can partition $\mathbb{R}^n$ into cubes $Q$ of length $1$. However, using the above example, we have that $\mathcal{H}^n(Q)<+\infty$. Therefore, from Lemma 4, $$\mathcal{H}^s(\mathbb{R}^n)\leq\sum_{Q}\mathcal{H}^s(Q)=0$$Therefore, $\mathcal{H}^s(A)\leq \mathcal{H}^s(\mathbb{R}^n)=0$. 
- **Corollary**: For all $A\subseteq \mathbb{R}^n$, $\text{dim}_{\mathcal{H}}(A)\leq n$.
---
> [!lemma] Proposition 7
> If $A\subseteq \mathbb{R}^n$ is open, then $\text{dim}_{\mathcal{H}}(A)=n$. 
---
##### Examples
> [!claim]
> Consider $Q:=[-1,1]^n\subseteq \mathbb{R}^n$. For all $n\in \mathbb{N}$, it holds that:
> $$w_{n}^{-1}\mathcal{L}^n(Q)\leq \mathcal{H}^n(Q)\leq 2^{-n}n^{n/2}\mathcal{L}^n(Q)$$where $w_{n}=\mathcal{L}^n(B_{<1}(0))=\pi^{n/2}/\Gamma(1+n /2)$.

> [!proof]-
> Consider the following:
> 1. **Upper bound**: 
>    We take $\delta>0$. For $k\geq 0$, we split $Q$ into $2^{(k+1)n}$ sub-cubes $\{ Q_{\ell} \}$ of side-length $\frac{1}{2^k}$. Then, each cube $Q_{\ell}$ is included in the ball $B_{<\sqrt{ n }/2^{k+1}}(x_{\ell})$ where $x_{\ell}$ denotes the center of the cube. 
>    
>    If we then choose $k$ s.t. $\frac{\sqrt{ n }}{2^{k+1}}<\delta$,  then: $$\mathcal{H}^n_{\delta}(Q)\leq \sum_{\ell=1}^{2^{(k+1)n}}\left( \frac{\sqrt{ n }}{2^{k+1}} \right)^n=n^{n/2}\leq 2^{-n}n^{n/2}\mathcal{L}^n(Q) $$By taking $\delta\to{0}$, we have: $\mathcal{H}^n(Q)\leq 2^{-n}n^{n/2}\mathcal{L}^n(Q)$ .
> 2. **Lower bound**:
> 	Let $\delta>0$. We consider a covering of $Q$, $Q\subseteq \bigcup_{k=0}^{\infty}B_{<r_{k}}(x_{k})$ where $0<r_{k}<\delta$. Then, $$\mathcal{L}^n(Q)\leq w_{n}\sum_{k=0}^{\infty}r_{k}^n$$
>     By taking the infimum over all coverings and taking $\delta\to0$, we get that: $$w_{n}^{-1}\mathcal{L}^n(Q)\leq \mathcal{H}^n(Q)$$
---
##### Examples of Sets with Non-integer Hausdorff Dimensions
- [[Cantor Set|Triadic Cantor set]]: $C:=\bigcap_{_{k=0}}^{\infty}C_{k}$ where $C_{0}=[0,1]$ and $C_{i+1}$ is obtained from $C_{i}$ by removing the open middle third from each connected component of $C_{i}$. Then, $$\text{dim}_{\mathcal{H}}(C)=\frac{\ln 2}{\ln 3}$$
---