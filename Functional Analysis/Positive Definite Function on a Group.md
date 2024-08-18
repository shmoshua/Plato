#Definition #FunctionalAnalysis 

> [!definition]
> Let $G$ be a group and $\mathcal{H}$ a [[Hilbert Space|$\mathbb{C}$-Hilbert space]]. 
> 1. A ***positive-definite function*** on $G$ is a function $\Phi:G\to \mathcal{B}(\mathcal{H})$ s.t. for every $g_{1},\dots,g_{n}\in G$ and $x_{1},\dots,x_{n}\in \mathcal{H}$, $$\sum_{i,j=1}^{n}\braket{ \Phi(g_{j}^{-1}g_{i})x_{i} , x_{j} } \geq 0$$
- **Remark**: If $\mathcal{H}=\mathbb{C}$, using that $\mathcal{B}(\mathbb{C})\cong \mathbb{C}$, a function $\Phi:G\to \mathbb{C}$ is ***positive definite*** if for every $g_{1},\dots,g_{n}\in G$ and $c_{1},..,c_{n}\in \mathbb{C}$ s.t. $$\sum_{i,j=1}^{n}c_{i}\overline{c_{j}}\Phi(g_{j}^{-1}g_{i})\geq 0$$
---
##### Properties

> [!lemma] Lemma 1
> Let $\Phi:G\to \mathbb{C}$ be positive definite. Then,
> 1. $\Phi(x ^{-1})=\overline{\Phi(x)}$ for all $x\in G$.
> 2. $\left| \Phi(x) \right|\leq \Phi(e)$ for all $x\in G$.
> 3. $\left| \Phi(x)-\Phi(y) \right|^{2}\leq 2\Phi(e)\text{Re}(\Phi(e)-\Phi(x  ^{-1}y))$ for every $x,y\in G$.

> [!proof]-
> We have:
> 1. Let $x\in G$ and $c\in \mathbb{C}$. Then, by using $x_{1}=e$, $x_{2}=x$, $c_{1}=1$,$c_{2}=c$, $$0\leq (1+\left| c \right| ^{2})\Phi(e)+c\Phi(x)+\overline{c}\Phi(x ^{-1})$$Consider:
> 	1. from $c=0$, $\Phi(e)\geq 0$.
> 	2. from $c=1$, $2\Phi(e)+\Phi(x)+\Phi(x ^{-1})\geq 0$ and $\Phi(x)+\Phi(x ^{-1})\in \mathbb{R}$.
> 	3. from $c=i$, $2\Phi(e)+i\Phi(x)-i\Phi(x ^{-1})\geq 0$ and $i(\Phi(x)-\Phi(x ^{-1}))\in \mathbb{R}$
> 	
> 	Therefore, $\Phi(x)+\Phi(x ^{-1})=\overline{\Phi(x)}+\overline{\Phi(x ^{-1})}$ and $-\Phi(x)+\Phi(x ^{-1})=\overline{\Phi(x)}-\overline{\Phi(x ^{-1})}$. This implies that $\overline{\Phi(x)}=\Phi(x ^{-1})$. 
> 2. Plugging 1 into above, $$(1+\left| c \right| ^{2})\Phi(e)+2\text{Re}(c\Phi(x))\geq0\quad \forall c\in C$$By choosing $c\in \mathbb{T}$ s.t. $c\Phi(x)=-\left| \Phi(x) \right|$, we get that $2\Phi(e)-2\left| \Phi(x) \right|\geq 0$.
> 3. For $x_{1},x_{2},x_{3}\in G$ and $c_{1},c_{2},c_{3}\in \mathbb{C}$, we get that: $$(\left| c_{1} \right|^{2}+\left| c_{2} \right|^{2}+\left| c_{3} \right| ^{2}  )\Phi(e)+2\text{Re}(\overline{c_{1}}c_{2}\Phi(x_{1}^{-1}x_{2}))+2\text{Re}(\overline{c_{2}}c_{3}\Phi(x_{2}^{-1}x_{3}))+2\text{Re}(\overline{c_{1}}c_{3}\Phi(x_{1}^{-1}x_{3}))\geq 0$$By taking $x_{1}=e,x_{2}=x,x_{3}=y,c_{1}=1,c_{3}=-c_{2}$, we get: $$(1+2\left| c_{2} \right| ^{2})\Phi(e)+2\text{Re}(c_{2}\Phi(x))-2\text{Re}(\left| c_{2} \right| ^{2}\Phi(x  ^{-1}y))-2\text{Re}(c_{2}\Phi(y))\geq 0$$Therefore, $$2\left| c_{2} \right| ^2(\Phi(e)-\text{Re}(\Phi(x  ^{-1}y)))+2\text{Re}(c_{2}\Phi(x)-c_{2}\Phi(y))+\Phi(e)\geq 0$$For $\lambda\in \mathbb{R}$, let $c_{2}\in \mathbb{C}$ s.t. $c_{2}(\Phi(x)-\Phi(y))=\lambda \left| \Phi(x)-\Phi(y) \right|$. Then, $$2\lambda^{2}(\Phi(e)-\text{Re}(\Phi(x ^{-1} y)))+2\lambda \left| \Phi(x)-\Phi(y) \right| +\Phi(e)\geq 0,\quad \forall \lambda\in \mathbb{R}$$Then, the discriminant has to be non-positive: $$4\left| \Phi(x)-\Phi(y) \right| ^{2}-8\Phi(e)(\Phi(e)-\text{Re}(\Phi(x ^{-1}y)))\leq 0$$This proves the statement.
- **Corollary**: A continuous, positive definite function $\Phi:G\to \mathbb{C}$ on a LCH group $G$ is left and right [[Uniformly Continuous Function|uniformly continuous]].
---
![[LCA Group#^074e1a]]

---
##### Examples
> [!h] Example 1 (Unitary Representation)
> Let $\pi:G\to \text{U}(\mathcal{H})$ be a [[unitary representation]]. Then, 
> 1. for any $v\in \mathcal{H}$, $\Phi:G\to \mathbb{C},g\mapsto \braket{ \pi(g)v , v }$ is positive definite.

> [!proof]-
> $$\sum_{i,j=1}^{n}\braket{ \pi(g_{j}^{-1}g_{i})v ,v  }c_{i}\overline{c_{j}}=\sum_{i,j=1}^{n}\braket{ c_{i}\pi(g_{i})v ,c_{j}\pi(g_{j})v  }=\left\| \sum_{i=1}^{n}c_{i}\pi(g_{i})v \right\| ^{2}\geq 0$$
---
> [!h] Example 2 (LCA Group)
> Let $G$ be an [[LCA group]] and $\mu$ a positive bounded measure on $\widehat{G}$. Then, $$\Phi(x):=\int_{\widehat{G}}^{}(x,\chi)  \, d\mu(\chi) $$is continuous and positive definite.

> [!proof]-
> We have:
> 1. **$\Phi$ is positive definite**:
>    Since $\left| (x,\chi) \right|=1$ for all $x\in G$ and $\chi\in \widehat{G}$, $$\int_{\widehat{G}}^{} \left| (x,\chi) \right|  \, d\mu(\chi)=\mu(\widehat{G})<+\infty $$and $\chi\mapsto (x,\chi)$ is in $L^1(\widehat{G},\mu)$. Next, if $x_{1},\dots,x_{n}\in G$ and $c_{1},\dots,c_{n}\in \mathbb{C}$, $$\begin{align}\sum_{i,j=1}^{n}c_{i}\overline{c_{j}}\Phi(x_{j}^{-1}x_{i})&=\int_{\widehat{G}}^{} \sum_{i,j=1}^{n}c_{i}\overline{c_{j}}(x_{j}^{-1}x_{i},\chi) \, d\mu(\chi)\\&=\int_{\widehat{G}}^{} \sum_{i,j=1}^{n}c_{i}\overline{c_{j}} (x_{i},\chi)\overline{(x_{j},\chi)}\, d\mu(\chi)\\&=\int_{\widehat{G}}^{} \left| \sum_{i=1}^{n}c_{i}(x_{i},\chi) \right| ^{2} \, d\mu(\chi)\\&\geq 0 \end{align} $$
> 2. **$\Phi$ is continuous**:
>    It suffices to show the continuity at $e\in G$. Let $\varepsilon>0$ and $C\subseteq \widehat{G}$ a compact subset with $\mu(C)>\mu(\widehat{G})-\varepsilon$. Then, $$\left| \Phi(x)-\Phi(e) \right| \leq \int_{\widehat{G}}^{} \left| (x,\chi)-1 \right|  \, d\mu(\chi) = \int_{C}^{} +\int_{\widehat{G} \backslash C} \leq \int_{C}\left| (x,\chi)-1 \right|   \, d\mu(\chi) +2\varepsilon $$However, by [[Fourier Transform|Proposition 6]], $N(C,\varepsilon / \mu(C))$ is an open neighborhood of $e$ in $G$. Then, for any $x\in N(C, \varepsilon / \mu(C))$, $$\left| \Phi(x)-\Phi(e) \right| \leq \int_{C} \frac{\varepsilon}{\mu(C)}  \, d\mu(\chi)+2\varepsilon=3\varepsilon $$