#Definition #FunctionalAnalysis 

> [!definition]
> For a [[Hilbert Space|Hilbert space]] $\mathcal{H}$, an operator $T\in \mathcal{B}(\mathcal{H},\mathcal{H})$ is a ***compact, self-adjoint operator*** if:
> 1. $T\in \mathcal{K}(\mathcal{H})$, i.e. $T$ is [[Compact Operator|compact]] and 
> 2. $T=T^{*}$, i.e. $T$ is [[Adjoint Linear Map|self-adjoint]].
---
##### Properties
> [!lemma] Lemma 1
> Let $T\in \mathcal{B}(\mathcal{H})$. Then, the following hold:
> 1. If $T=T^{*}$ and $W\subseteq \mathcal{H}$ is a $T$-invariant subspace, i.e. $T(W)\subseteq W$, then $W^{\bot}$ is $T$-invariant.
> 2. If $T=T^{*}$, then $\braket{ T(v) , v }\in \mathbb{R}$, in particular all eigenvalues of $T$ are in $\mathbb{R}$.
> 3. $\left\| T \right\|=\sup_{\|u\|,\|v\|\leq 1}\left| \braket{ T(u) ,  v} \right|$
> 4. If $T=T^{*}$ and $\lambda\neq\beta$, then $\mathcal{H}_{\lambda}{\bot} \mathcal{H}_{\beta}$.

> [!proof]-
> We show that: 
> 1. Let $v\in W$ and $w\in W^{\bot}$. Therefore, we show that $T(w)$ is orthogonal to $v$.$$\braket{ v , T(w) } =\braket{ \underbrace{ T(v) }_{ \in W } , w }=0 $$
> 2. For $v\in \mathcal{H}$, $$\overline{\braket{ T(v) , v } }=\braket{ v , T(v) } =\braket{ T(v) , v } $$Therefore, $\braket{ T(v) , v }$ is real and if $v$ is an eigenvector of $\alpha$, $$\alpha \braket{ v,v  }=\braket{ \alpha v , v } =\braket{ T(v) , v } \in \mathbb{R} $$Hence, $\alpha$ is real.
> 3. From the definition, $$\left\| T \right\| =\sup_{\left\| u \right\| \leq 1}\left\| T(u) \right\| $$but for all $w\in \mathcal{H}$, $$ \|w\|=\sup_{\left\| i(v) \right\| \leq 1}\left| i(v)(w) \right| =\sup_{\|v\|\leq 1}\left| \braket{ w , v }  \right|  $$Therefore, $$\left\| T \right\| = \sup_{\|u\|,\|v\|\leq 1}\left| \braket{ T(u) , v }  \right| $$
> 4. Let $v\in \mathcal{H}_{\lambda}$ and $w\in \mathcal{H}_{\beta}$. Then, $$\lambda \braket{ v , w } =\braket{ \lambda v , w } =\braket{ T(v) , w } =\braket{ v , T(w) } =\braket{ v , \beta w } =\beta \braket{ v , w } $$where we use that $\beta\in \mathbb{R}$. As $\lambda\neq\beta$, we have that $\braket{ v , w }=0$.
---
> [!lemma] Lemma 2
> Let $T\in \mathcal{B}(\mathcal{H})$ and $T=T^{*}$. Then, $$\left\| T \right\| =\sup_{\|v\|\leq 1}\left| \braket{ T(v) , v }  \right| $$

> [!proof]-
> Let $\alpha:=\sup_{\|v\|\leq 1}\left| \braket{ T(v) , v }  \right|\leq \sup_{\|v\|\leq 1}\left\| T(v) \right\|\|v\|\leq\sup_{\|v\|\leq 1}\|T(v)\|=\|T\|$. So we show that $\left\| T \right\|\leq\alpha$, more specifically, we show that for all $v,w\in \mathcal{H}$: $$\left| \braket{ T(v) , w }  \right| \leq\alpha \|v\|\|w\| $$Wlog we can assume $\braket{ T(v) , w }\in \mathbb{R}$ (otherwise we can rotate it onto the real plane). Then, we have: $$\begin{align}\braket{ T(v+w) , v+w }  &=\braket{ T(v) ,v  }+2\braket{ T(v) , w } +\braket{ T(w) , w }  \\\braket{ T(v-w) , v-w }  &=\braket{ T(v) ,v  }-2\braket{ T(v) , w } +\braket{ T(w) , w }  \end{align}$$Hence, $$\begin{align}4\left| \braket{ T(v) , w } \right|  &=\left|\braket{ T(v+w) , v+w }-\braket{ T(v-w) , v-w }  \right|\\&\leq\left|\braket{ T(v+w) , v+w }\right|+\left|\braket{ T(v-w) , v-w }  \right|\\&\leq\alpha \|v+w\|^{2} +\alpha\|v-w\|^{2} \\&=2\alpha (\|v\|^{2}+\|w\|^{2})\end{align} $$from the parallelogram identity. As this holds for all $v,w\in \mathcal{H}$, we have $v'=\frac{v}{\sqrt{ a }}$ and $w'=\sqrt{ a }w$ for $a>0$. Then, $$4\left| \braket{ T(v) , w }  \right| \leq 2\alpha\left(  \frac{\|v\|^{2}}{a}+a\|w\|^{2} \right)$$By assuming $w\neq 0$ and setting $a=\|v\| / \|w\|$, $$4\left| \braket{ T(v) , w }  \right| \leq 4\alpha\|v\|\|w\|$$From which we have the desired inequality. Therefore, $$\|T\|=\sup_{\|v\|,\|w\|\leq 1}\left| \braket{ T(v) , w }  \right| \leq\alpha$$from Lemma 1.3.
---
> [!lemma] Lemma 3
> Either $\left\| T \right\|$ or $-\left\| T \right\|$ is an eigenvalue of $T$.

> [!proof]-
> We may assume that $T \neq 0$. Let $(v_{n})_{n\geq 1}$ s.t. $\left\| v_{n} \right\|=1$ and $$\lim_{ n \to \infty } \left| \braket{ T(v_{n}) , v_{n} }  \right| =\left\| T \right\| $$this exists due to Lemma 2. We may also assume that $\lim_{ n \to \infty }\braket{ T(v_{n}) , v_{n} }=\lambda$ where $\left| \lambda \right|=\left\| T \right\|$
> 
> As $T$ is compact, we have that $(T(v_{n}))_{n}\subseteq \overline{T(B_{\leq 1}(0))}$ and modulo passing to the subsequence, we may assume that $\lim_{ n \to \infty }T(v_{n})=:w$. Then, $$\begin{align}\left\| T(v_{n})-\lambda v_{n} \right\|^{2}&=\left\| T(v_{n}) \right\|^{2} -2\lambda \braket{ T(v_{n}) , v_{n} } +\lambda^{2}\left\| v_{n} \right\| ^{2} \\&\leq \left\| T \right\| ^{2}-2\lambda \braket{ T(v_{n}) , v_{n} } +\lambda^{2}\\&=2(\left\| T \right\| ^{2}-\lambda \braket{ T(v_{n}) , v_{n} } )\to 2(\left\| T \right\| ^{2}-\left\| T \right\| ^{2})=0\end{align} $$This implies that $\left\| w-\lambda v_{n} \right\|\to 0$ and $\lim_{ n \to \infty }\lambda v_{n}=w$. As $\left\| v_{n} \right\|=1$ and $\lambda\neq 0$, $w\neq 0$.
> 
> Therefore, by continuity: $$w=\lim_{ n \to \infty } T(v_{n})=\frac{T(w)}{\lambda}$$From which it follows that $T(w)=\lambda w$.
---
> [!lemma] Theorem 4 (Spectral Theorem)
> Let $T\in \mathcal{B}(\mathcal{H})$ be compact and self-adjoint. Then, 
> 1. $\mathcal{H}$ has an orthonormal basis consisting of eigenvectors of $T$ and 
> 2. for all eigenvalue $\lambda\neq 0$, $\text{dim } \mathcal{H}_{\lambda}<+\infty$ and
> 3. for all $\varepsilon>0$, $$\{ \lambda\in \mathbb{C}:\left| \lambda \right| \geq\varepsilon, \text{dim }\mathcal{H}_{\lambda}>0 \}$$is finite.

> [!proof]-
> We have that: 
> 
> 1. By [[Poset|Zorn's lemma]], we can choose an orthonormal set $A\subseteq \mathcal{H}$ of eigenvalues of $T$ that is maximal among all subsets of consisting eigenvectors.
>    
>    Let $\braket{ A }$ denote the $\mathbb{C}$-vector space generated by $A$ and $W:=\overline{\braket{ A  }}$. We want to show that $W=\mathcal{H}$, in other words, $W^{\bot}=\{ 0 \}$.As $T(W)\subseteq W$ and $T$ is self-adjoint, we have that $T(W^{\bot})\subseteq W^{\bot}$. Now, consider $T|_{W^{\bot}}$ which is self-adjoint. If $W^{\bot}\neq (0)$, then from Lemma 3, $T|_{W^{\bot}}$ has an eigenvector $u$ with $\|u\|=1$, but $A \cup \{ u \}\supsetneq A$ is a contradiction. 
> 
> 2. For $\varepsilon>0$, we define: $W:=\overline{\underset{ \left| \lambda \right|\geq \varepsilon }{ \oplus }\mathcal{H}_{\lambda}}$. Observe that $\underset{ \left| \lambda \right|\geq \varepsilon }{ \oplus }\mathcal{H}_{\lambda}$ is a direct sum since for $\lambda\neq\beta$, $\mathcal{H}_{\lambda}\bot\mathcal{H}_{\beta}$. We now want to show that $\text{dim }W <+\infty$.
> 	
> 	Let $P_{\lambda}:\mathcal{H}\to \mathcal{H}_{\lambda}$ be the orthogonal projection on the closed subspace $\mathcal{H}_{\lambda}$. Now, let $v\in B^W_{\leq \varepsilon}(0)$. Then,  $v=\sum_{\left| \lambda \right|\geq \varepsilon}^{}P_{\lambda}(v)$  with $$\|v\|^{2}=\sum_{\left| \lambda \right| \geq \varepsilon}^{}\left\| P_{\lambda}(v) \right\| ^{2}$$Now, define $w:=\sum_{\left| \lambda \right|\geq \varepsilon}^{} \frac{1}{\lambda}P_{\lambda}(v)$. Then, $$\|w\|^{2}=\sum_{\left| \lambda \right| \geq \varepsilon}^{} \frac{1}{\lambda^{2}}\left\| P_{\lambda}(v) \right\| ^{2}\leq \frac{1}{\varepsilon^{2}}\|v\|^{2}\leq 1 $$and $$T(w)=\sum_{\left| \lambda \right| \geq \varepsilon}^{} \frac{1}{\lambda}T(P_{\lambda}(v))=\sum_{\left| \lambda \right| \geq \varepsilon}^{} \frac{1}{\lambda}\lambda P_{\lambda}(v)=v$$Therefore,  $B^W_{\leq\varepsilon}(0)\subseteq T(B^W_{\leq 1}(0))$ and from the compactness of $T$, $B^W_{\leq \varepsilon}(0)$ is compact. Thus, $W$ is finite-dimensional.
---
