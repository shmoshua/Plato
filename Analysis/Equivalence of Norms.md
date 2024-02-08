#Definition #Analysis  #LST 

> [!definition]
> For a [[Vector Space|vector space]] $V$ with two norms, $\|\cdot\|_{a}$ and $\|\cdot\|_{b}$, the two norms are ***equivalent*** if there exists $c>0$ s.t. for all $v\in V$: $$c^{-1}\|v\|_{a} \leq \|v\|_{b}\leq c\|v\|_{a}$$
- **Remark**: Two norms on a $\mathbb{K}$-vector space induce the same topology if and only if they are equivalent.
---
##### Properties
> [!lemma] Theorem 1
> The equivalence of norm is symmetric and transitive.

>[!proof]-
>If we have $m_{l},m_{u} >0$ with $m_{l}\leq m_{u}$ and $m_{l}\|v\|_{a} \leq \|v\|_{b}\leq m_{u}\|v\|_{a}$, then we have $$\frac{1}{m_{u}}\|v\|_{b} \leq \|v\|_{a}\leq \frac{1}{m_{l}}\|v\|_{b}$$
>Further, if we have $m_{l},m_{u} >0$ with $m_{l}\leq m_{u}$ and $m_{l}\|v\|_{a} \leq \|v\|_{b}\leq m_{u}\|v\|_{a}$ and $n_{l},n_{u} >0$ with $n_{l} \leq n_{u}$ with $n_{l}\|v\|_{b} \leq \|v\|_{c}\leq n_{u}\|v\|_{b}$, then $$m_{l}n_{l}\|v\|_{a}\leq\|v\|_{c}\leq n_{u}m_{u}\|v\|_{a}$$
---
> [!lemma] Fact 2
> Let $\|\cdot\|_{a}$ and $\|\cdot\|_{b}$ be two equivalent norms on $(V,F)$ with $F=\mathbb{R}$ or $\mathbb{C}$. A sequence $\{ v_{i} \}_{i\geq 0}\subseteq V$ converges to some $v\in V$ in $(V,F,\|\cdot \|_{a})$ if and only if it converges to $v$ in $(V,F,\|\cdot\|_{b})$.

>[!proof]-
>Suppose that $\{ v_{i} \}_{i\geq 0}$ converges to $v\in V$ w.r.t $\|\cdot\|_{a}$, i.e. for all $\varepsilon>0$ there exists $N\in \mathbb{N}$ s.t. $\|v_{m}-v\|_{a}<\varepsilon$ for all $m\geq N$. We also know that due to equivalence, there exists $m_{u}\geq m_{l}>0$ s.t. $m_{l}\|v\|_{a}\leq\|v\|_{b}\leq m_{u}\|v\|_{a}$ for all $v$. Fix an arbitrary $\varepsilon>0$. Then, there exists $N\in \mathbb{N}$ s.t. $\|v_{m}-v\|_{a }< \frac{\varepsilon}{m_{u}}$. Therefore, $$\|v_{m}-v\|_{b}\leq m_{u}\|v_{m}-v\|_{a}<m_{u} \frac{\varepsilon}{m_{u}}=\varepsilon$$for all $m \geq N$.
---
> [!lemma] Theorem 3
> Any two norms on a finite-dimensional space $V$ are equivalent.

>[!proof]-
> Let $n:=\text{dim}_{\mathbb{K}}V$ and $\Phi:\mathbb{K}^n\to V$ a $\mathbb{K}$-vector space isomorphism. Since any norm of $V$ composed with $\Phi$ gives a norm on $\mathbb{K}^n$, it is sufficient to show the statement for $V=\mathbb{K}^n$. 
> 
> Let $\|\cdot\|\in \mathbb{K}^n$ be a norm and for all $x\in \mathbb{K}^n$, $$\|x\|=\left\| \sum_{i=1}^{n}x_{i}e_{i} \right\| \leq \sum_{i=1}^{n}\left| x_{i} \right| \|e_{i}\|\leq \sqrt{ \sum_{i=1}^{n}\left| x_{i} \right| ^{2} }\sqrt{ \sum_{i=1}^{n}\left\| e_{i} \right\| ^{2} }=c\|x\|_{2}$$
> Therefore, $\|\cdot\|$ is continuous w.r.t the Euclidean topology on $\mathbb{K}^n$ since: $$\left\| x-y \right\|\leq c\left\| x-y \right\| _{2}\quad \forall x,y\in \mathbb{K}^n $$By Heine-Borel, the subset: $$S:=\{ x\in \mathbb{K}^n:\|x\|_{2}=1 \}$$is compact. Since $\|\cdot\|$ is continuous and non-vanishing on $S$, there exists $c_{1},c_{2}>0$ s.t. $$c_{1}\leq\|x\|\leq c_{2},\quad \forall x\in S$$Thus, for all $x\in \mathbb{K}^n \backslash\{ 0 \}$, $$c_{1}\leq \left\| \frac{x}{\|x\|_{2}} \right\|\leq c_{2} $$which implies that $\|\cdot\|$ and $\|\cdot\|_{2}$ are equivalent.

---
> [!lemma] Fact 4
> Two norms on an infinite-dimensional space $V$ are not necessarily equivalent.

>[!proof]-
>Consider the functions $f\in C([0,1],\mathbb{R})$ and the two norms $\|f\|_{\infty}$ and $\|f\|_{1}$. Assume there exists $m_{u}\geq m_{l}>0$ s.t. $$m_{l}\|f\|_{1}\leq \|f\|_{\infty}\leq m_{u}\|f\|_{1}$$Consider $f_{m_{u}}(t)=t^{m_{u}}$. Then, $\|f_{m_{u}}\|_{\infty}=1$ and $\|f_{m_{u}}\|_{1}= \frac{1}{m_{u}+1}$. So, $\|f_{{m_{u}}}\|_{\infty}> m_{u}\|f_{{m_{u}}}\|_{1}$, which is a contradiction.
---
##### Examples
- For $\mathbb{R}^n$, [[1-Norm|$\|\cdot\|_{1}$]] and [[Infinity Norm|$\|\cdot\|_{\infty}$]] are equivalent as $$\|x\|_{\infty}=\max_{i\in[n]}|x_{i}|\leq \sum_{i=1}^{n}|x_{i}|=\|x\|_{1}\leq n \cdot \|x\|_{\infty}$$

---