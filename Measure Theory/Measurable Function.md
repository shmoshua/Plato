#Definition #MeasureTheory 

> [!definition]
> Let $\mu$ be a [[Measure|measure]] on $\mathbb{R}^n$ and $\Omega \subseteq \mathbb{R}^n$ a [[Measurable Set|$\mu$-measurable set]]. Then, a function $f:\Omega \to[-\infty,\infty]$ is ***$\mu$-measurable*** if and only if: 
> 1. $f^{-1}[\{ -\infty \}]$ and $f^{-1}[\{ \infty \}]$ are $\mu$-measurable and
> 2. $f^{-1}[A]$ is $\mu$-measurable for all [[Borel Sigma-Algebra|Borel sets]] $A\in\mathcal{B}(\mathbb{R})$.

- **Equivalent definition**: 
	1. $f^{-1}[\{ -\infty \}]$ and $f^{-1}[\{ \infty \}]$ are $\mu$-measurable and
	2. $f^{-1}[U]$ is $\mu$-measurable for all open sets $U\subseteq \mathbb{R}$
- **Equivalent definition**: 
	1. $f^{-1}[\{ -\infty \}]$ and $f^{-1}[\{ \infty \}]$ are $\mu$-measurable and
	2. $f^{-1}(-\infty,a)$ is $\mu$-measurable for all $a\in \mathbb{R}$
 - **Equivalent definition**: 
	1. $f^{-1}[-\infty,a)$ is $\mu$-measurable for all $a\in \mathbb{R}$.
	
---
##### Properties
> [!lemma] Theorem 1
> Let $f,g:\Omega\to \mathbb{R}$ be $\mu$-measurable functions and $h:\mathbb{R} \to \mathbb{R}$ [[Continuous Function|continuous]]. Then, 
> 1. $h\circ f$ is $\mu$-measurable.
> 2. $f+g,f\cdot g,|f|,\min(f,g),\max(f,g)$ are $\mu$-measurable. 
> 3. If $g(x)\neq 0$ for all $x\in \Omega$, $\frac{f}{g}$ is $\mu$-measurable.
> 4. If $f_{k}:\Omega \to \overline{\mathbb{R}}$ is $\mu$-measurable for all $k$, $\inf_{k}f_{k}, \sup_{k}f_{k},\liminf_{ k \to \infty }f_{k},\limsup_{ k  \to \infty }f_{k}$ are $\mu$-measurable.

> [!proof]-
> We have that:
> 1. We have: $(h\circ f)^{-1}[\{ -\infty \}]=f^{-1}[h^{-1}[\{ -\infty \}]]=\varnothing$ (same for $\infty$) Then, for all open $U\subseteq \mathbb{R}$ $$(h\circ f)^{-1}[U]=f^{-1}[\underbrace{ h^{-1}[U] }_{ \text{open} }]$$is measurable.
> 2. We will show them one by one: 
> 	- $f+g$: We have that: $$(f+g)^{-1}[(-\infty,a)]=\bigcup_{r+s<a,r,s\in \mathbb{Q}}^{}f^{-1}[(-\infty,r)]\cap g^{-1}[(-\infty,s)]$$
> 	- $f^{2}$: We have that: $$(f^{2})^{-1}[(-\infty,a)]=\begin{cases}\varnothing&a<0\\f^{-1}[(-\infty,\sqrt{ a } )]\backslash f^{-1}[(-\infty,-\sqrt{ a }]]&a\geq 0\end{cases}$$
> 	- $f\cdot g=\frac{1}{2}((f+g)^{2}-f^{2}-g^{2})$
> 	- If $g\neq 0$, $$\left( \frac{1}{g} \right)^{-1}[(-\infty,a)]=\begin{cases}g^{-1}\left[ \left( \frac{1}{a},0 \right) \right]&a<0\\g^{-1}[(-\infty,0)]&a=0\\g^{-1}[(-\infty,0)]\cup g^{-1}\left[ \left( \frac{1}{a},\infty \right) \right] & a>0\end{cases}$$
> 	- $f^+(x):=\begin{cases}f(x)&f(x)\geq 0\\0&f(x)<0\end{cases}$ is $\mu$-measurable as $f^+=s^+\circ f$ where: $$s^+(x):=\begin{cases}x&x\geq 0\\0&x<0\end{cases}$$is continuous. 
> 	- $f^-(x):=\begin{cases}-f(x)&f(x)\leq 0\\0&f(x)>0\end{cases}$ is analgous to $f^+$.
> 	- $\left| f \right|=f^++f^-$.
> 	- $\max(f,g)=f+(g-f)^+$
> 	- $\min(f,g)=f-(g-f)^-$
> 3. We have: 
> 	- $(\inf_{k}f_{k})^{-1}[-\infty,a)=\bigcup_{k=0}^{\infty}f_{k}^{-1}[-\infty,a)$
> 	- $(\sup_{k}f_{k})^{-1}[-\infty,a)=\bigcup_{\ell=1}^{\infty}\bigcap_{k=1}^{\infty}f_{k}^{-1}[-\infty,a-\frac{1}{\ell})$
> 	- $\liminf_{ k \to \infty }f_{k}=\sup_{m\geq 1}\inf_{k\geq m}f_{k}$
> 	- $\limsup_{ k \to \infty }f_{k}=\inf_{m\geq 1}\sup_{k\geq m}f_{k}$

---
> [!lemma] Proposition 2
> For a set $A\subseteq \mathbb{R}^n$, the characteristic function $\chi_{A}$ is $\mu$-measurable if and only if $A$ is $\mu$-measurable.

> [!proof]-
> For any $a\in \mathbb{R}$, we have: $$\chi_{A}^{-1}[(-\infty,a)]=\begin{cases}\varnothing&a\leq 0\\A^c&0<a\leq 1\\\mathbb{R}^n&1<a\end{cases}$$Therefore, $\chi_{A}$ is measurable if and only if $A$ is measurable.
---
> [!lemma] Theorem 3
> For a $\mu$-measurable function $f:\Omega\to [0,+\infty]$ where $\Omega$ is $\mu$-measurable, there exists $\mu$-measurable sets $\{ A_{k} \}_{k}\subseteq \mathcal{P}(\Omega)$ s.t. $$f(x)=\sum_{k=1}^{\infty} \frac{1}{k}\chi_{A_{k}}(x)$$

> [!proof]-
> We will define $\{ A_{k} \}$ inductively and show that they are $\mu$-measurable.
> 1. $A_{1}:=\{ x\in \Omega:f(x)\geq 1 \}=f^{-1}[1,+\infty]$ which is $\mu$-measurable.
> 2. $A_{k}:=\left\{  x\in \Omega :f(x)\geq \frac{1}{k}+\sum_{j=1}^{k-1} \frac{1}{j}\chi_{A_{j}}(x)\right\}=\left( f-\sum_{j=1}^{k-1} \frac{1}{j}\chi_{A_{j}} \right)^{-1}\left[ \frac{1}{k},+\infty \right]$
> 
> Now, we will show that $f(x)=\sum_{k=1}^{\infty} \frac{1}{k} \chi_{A_{k}}(x)$.
> - ($\geq$): Let's take $x\in \Omega$. We have two cases:
>   1. $\sup \{ k: x\in A_{k} \}=+\infty$
>      Then, there exists a sequence $(k_{n})_{n}$ s.t. $\lim_{ n \to \infty }k_{n}=+\infty$ and for all $n$, $$f(x)\geq \frac{1}{k_{n}}+\sum_{j=1}^{k_{n}-1} \frac{1}{j}\chi_{A_{j}}(x)$$By taking $n\to \infty$, we have the desired inequality.
>     2. $\sup \{ k: x\in A_{k} \}=\max \{ k: x\in A_{k} \}=k_{0}$
>        Then, $\chi_{A_{j}}(x)=0$ for all $j>k_{0}$. Therefore, $$f(x)\geq \frac{1}{k_{0}}+\sum_{j=1}^{k_{0}-1} \frac{1}{j}\chi_{A_{j}}(x)= \sum_{j=1}^{\infty} \frac{1}{j}\chi_{A_{j}}(x)$$
> - ($\leq$): We have three cases:
> 	1. $f(x)=+\infty$. 
> 	   Then, $x\in A_{k}$ for all $k$. Therefore, $$\sum_{k=1}^{\infty} \frac{1}{k}\chi_{A_{k}}(x)=\sum_{k=1}^{\infty} \frac{1}{k}=+\infty$$
> 	 2. $f(x)=0$. 
> 	    Then, $x \notin A_{k}$ for all $k$. Therefore, $$\sum_{k=1}^{\infty} \frac{1}{k}\chi_{A_{k}}(x)=0$$
> 	 3. $0<f(x)<+\infty$ 
> 	     We have that for all $k_{0}>0$, $x\notin\bigcap_{k\geq k_{0}}^{}A_{k}$. Assume that there exists $k_{0}>0$, s.t. $$x\in \bigcap_{k\geq k_{0}}^{}A_{k}$$i.e. $\chi_{A_{k}}(x)=1$ for all $k\geq k_{0}$. Then, $$+\infty>f(x)\geq \sum_{k=k_{0}}^{\infty} \frac{1}{k}\chi_{A_{k}}(x)=\sum_{k=k_{0}}^{\infty} \frac{1}{k}=\infty$$which is a contradiction. Therefore, there exists $(k_{n})_{n}$ s.t. for all $n$, $x\notin A_{k_{n}}$. Then, $$0\leq f(x)-\sum_{k=1}^{k_{n}-1} \frac{1}{k}\chi_{A_{k}}(x)< \frac{1}{k_{n}}$$By taking $n \to \infty$, $f(x)-\sum_{k=1}^{\infty} \frac{1}{k}\chi_{A_{k}}(x)=0$
> 	     $$f(x)=\sum_{k=1}^{\infty} \frac{1}{k}\chi_{A_{k}}(x)$$

- **Remark**: Any $\mu$-measurable function $f:\Omega\to[0,+\infty]$ is the pointwise limit of a non-decreasing sequence of [[Simple Function|simple functions]] $f_{m}(x):=\sum_{k=1}^{m} \frac{1}{k}\chi_{A_{k}}(x)$ .
- **Remark**: Any $\mu$-measurable function $f:\Omega\to[-\infty,+\infty]$ through the approximation of $f=f^+ -f^-$ by [[Simple Function|simple functions]].
---
> [!lemma] Proposition 4
> Let $f:\Omega\to \mathbb{R}$ be a continuous function and $\mu$ a [[Borel measure]]. Then, $f$ is $\mu$-measurable.

> [!proof]-
> For any open set $U\subseteq \mathbb{R}$, $f^{-1}[U]=O\cap\Omega$ where $O$ is open. Therefore, $O\cap\Omega$ is $\mu$-measurable.
---
> [!lemma] Theorem 4 (Egoroff)
> Let $\Omega \subseteq \mathbb{R}^n$ be a $\mu$-measurable set with $\mu(\Omega)<+\infty$.  Further, let $f,f_{k}:\Omega\to \overline{\mathbb{R}}$ be $\mu$-measurable functions s.t. $\left| f(x) \right| <+\infty$ [[Almost Everywhere|$\mu$-a.e.]] and $\lim_{ k \to \infty }f_{k}(x)=f(x)$ $\mu$-a.e.
> 
> Then, for all $\delta>0$,  there exists a $\mu$-measurable set $A\subseteq \Omega$ s.t. 
> 1. $\mu(\Omega \backslash A)<\delta$ and 
> 2. $\lim_{ k \to \infty }\sup_{x\in A}\left| f_{k}(x)-f(x) \right|=0$, i.e. $f_{k}$ converges to $f$ uniformly in $A$.
> 
> If $\mu$ is [[Radon Measure|Radon]], it further holds that, for all $\delta>0$,  there exists a compact set $F\subseteq \Omega$ s.t. 
> 1. $\mu(\Omega \backslash F)<\delta$ and 
> 2. $\lim_{ k \to \infty }\sup_{x\in F}\left| f_{k}(x)-f(x) \right|=0$, i.e. $f_{k}$ converges to $f$ uniformly in $F$.

> [!proof]-
> The steps are as follows:
> 1. **Defining $C_{i,j}$**
> 	Let $\tilde{\Omega}:=\{ x\in \Omega:\left| f(x) \right|<+\infty,\lim_{ k \to \infty }f_{k}(x)=f(x) \}$. Then, by $\mu$-a.e., $\mu(\Omega \backslash \tilde{\Omega})=0$.
> 	
> 	Now, for fixed $\delta>0$ and all $i\geq 1$, we define: $$C_{i,j}:=\bigcup_{k=j}^{\infty}\left\{  x\in \tilde{\Omega}:\left| f_{k}(x)-f(x) \right| > \frac{1}{2^i}  \right\}=\tilde{\Omega}\cap \bigcup_{k=j}^{\infty}\left| f_{k}-f \right| ^{-1}\left( \frac{1}{2^i}, \infty\right)$$Then, it holds that:
> 	1.  $C_{i,j}$ is $\mu$-measurable.
> 	2. $C_{i,j+1} \subseteq C_{i,j}$ for all $i,j$.
> 	3. By $\lim_{ k \to \infty }f_{k}(x)=f(x)$, we have that $\bigcap_{j=1}^{\infty}C_{i,j}=\varnothing$ with $\mu(C_{i,1})\leq \mu(\Omega)<+\infty$.
>2. **Continuity from Below**
> 	Using [[Measure Space|continuity from below]],$$\lim_{ j \to \infty } \mu(C_{i,j})=\mu \left( \bigcap_{j=1}^{\infty}C_{i,j} \right) =0$$This means, for every $i$, there exists $N(i)$ s.t. $$\mu(C_{i,N(i)})< \frac{\delta}{2^{i+1}}$$
> 3. **Showing the uniform convergence**
> Now, let $A:=\tilde{\Omega} \backslash \bigcup_{i=1}^{\infty}C_{i,N(i)}$. Then, $$\mu(\Omega \backslash A)=\mu(\tilde{\Omega}\backslash A)+\underbrace{ \mu(\Omega\backslash  \tilde{\Omega}) }_{ =0 }= \mu \left( \bigcup_{i=1}^{\infty}C_{i,N(i)} \right) \leq \sum_{i=1}^{\infty}\mu(C_{i,N(i)})< \frac{\delta}{2}$$Moreover, for all $i\geq 1$, $k\ge N(i)$: $$\sup_{x\in A}\left| f_{k}(x)-f(x) \right| \leq \frac{1}{2^i}$$which implies the uniform convergence.
> 4. **When $\mu$ is Radon**:
>Further, if $\mu$ is Radon, there exists compact $F \subseteq A$ s.t. $\mu(A \backslash F)=\mu(A)-\mu(F)<\frac{\delta}{2}$. Then, $$\mu(\Omega \backslash F)=\mu(\Omega \backslash A)+\mu(A \backslash F)\leq\delta$$
> This concludes the proof. 

- **Remark**: $\mu(\Omega)<+\infty$ is necessary. Consider $\Omega=\mathbb{R}$, $\mu=\mathcal{L}^1$ and $f_{k}=\chi_{[-k,k]}$. Then, for every $\delta>0$ and $A \subseteq \mathbb{R}$, if $\mathcal{L}^1(\mathbb{R} \backslash A) <\delta$ and $\lim_{ k \to \infty }\sup_{x\in A}\left| f_{k}(x)-1 \right|=0$, then there exists $\overline{k}\geq 0$ s.t. for all $k\geq \overline{k}$ and $x\in A$: $$\left| f_{k}(x)-1 \right|< \frac{1}{2} $$which implies that $[-k,k]^c \subseteq A^c$. This is a contradiction as $\delta>\mathcal{L}^1(A^c)\geq \mathcal{L}^1[-k,k]^c=+\infty$.
---
> [!lemma] Theorem 5 (Lusin)
> Let $\mu$ be [[Radon Measure|Radon measure]]. For $\mu$-measurable $\Omega \subseteq\mathbb{R}^n$ with $\mu(\Omega)<+\infty$ and $\mu$-measurable $f:\Omega \to \overline{\mathbb{R}}$ with $\left| f\right|<+\infty$ $\mu$-a.e.
> 
> Then, for all $\delta>0$, there exists a compact set $K \subseteq \Omega$ s.t. 
> 1. $\mu(\Omega \backslash K)\leq \delta$ and 
> 2. $\left. f \right|_{K}$ is continuous

>[!proof]-
>Steps:
>1. **Defining $\tilde{\Omega}$**:
>   For each positive integer $i>0$,  let $\{ B_{ij} \}_{j}\subseteq \mathbb{R}$ be disjoint Borel sets s.t. $\mathbb{R}=\bigcup_{j=1}^{\infty}B_{ij}$ and $\text{diam } B_{ij}<1/i$. 
>   
>    Now, define $A_{ij}:=f^{-1}[B_{ij}]$. Then, $A_{ij}$ is measurable and disjoint. Let: $$\tilde{\Omega}:=\bigcup_{j=1}^{\infty}A_{ij}$$i.e. $\Omega=\tilde{\Omega}\cup f^{-1}[\{ -\infty,\infty \}]$. Since $\mu$ is Radon, there exists a compact set $K_{ij}\subseteq A_{ij}$ s.t. $$\mu(A_{ij} \backslash K_{ij})<\frac{\varepsilon}{2^{i+j}}$$
>  2. 
> Then, $$\begin{align}\mu \left( \tilde{\Omega} \backslash \bigcup_{j=1}^{\infty}K_{ij} \right) &=\mu \left( \bigcup_{j=1}^{\infty}A_{ij} \backslash \bigcup_{j=1}^{\infty}K_{ij} \right) \\&\leq \mu \left( \bigcup_{j=1}^{\infty}(A_{ij} \backslash K_{ij}) \right) \\&\leq \sum_{j=1}^{\infty} \mu(A_{ij}\backslash K_{ij})\\&<\sum_{j=1}^{\infty} \frac{\varepsilon}{2^{i+j}}= \frac{\varepsilon}{2^i}\end{align}$$
> Since $$\lim_{ n \to \infty } \mu\left( \tilde{\Omega} \backslash \bigcup_{j=1}^{n}K_{ij} \right)=\mu\left( \tilde{\Omega} \backslash \bigcup_{j=1}^{\infty}K_{ij} \right)<\frac{\varepsilon}{2^i}$$there exists $N(i)>0$ s.t. $$\mu \left( \tilde{\Omega} \backslash \bigcup_{j=1}^{N(i)}K_{ij} \right) < \frac{\varepsilon}{2^i}$$
> Let $D_{i}:= \bigcup_{j=1}^{N(i)}K_{ij}$. Then, $D_{i}$ is compact. We now define for all $i,j$, $b_{ij}\in B_{ij}$ and let $g_{i}:D_{i}\to \mathbb{R}$, where $g_{i}(x)=b_{ij}$ if $x\in K_{ij}$. Then, $g_{i}$ is continuous, as it is locally constant.
> 
> Furthermore, $\left| f(x)-g_{i}(x) \right|< \frac{1}{i}$ for all $x\in D_{i}$. Let $K = \bigcap_{i=1}^\infty D_{i}$. Then, $K$ is compact and $$\mu(\tilde{\Omega} \backslash K)=\mu \left( \bigcup_{i=1}^{\infty}(\tilde{\Omega} \backslash D_{i}) \right) \leq \sum_{i=1}^{\infty}\mu(\tilde{\Omega} \backslash D_{i})<\varepsilon$$ Moreover, $$\mu(\Omega \backslash K)\leq \mu(\tilde{\Omega} \backslash K)+\mu(f^{-1}[\{ -\infty,\infty \}]\backslash K)\leq \varepsilon+0$$
> As $\left| f(x)-g_{i}(x) \right|< \frac{1}{i}$ for all $x\in D_{i}$, $g_{i}(x)\to f(x)$ is uniformly convergent on $K$. Therefore, $f|_{K}$ is continuous.

- **Remark**: If $\mu(\Omega)=+\infty$, then we cannot guarantee than we can find a compact set $K$. However, if we find a closed set $C \subseteq \Omega$ s.t. $\mu(\Omega \backslash C)<\varepsilon$ then $f|_{C}$ is continuous.
- **Example**: Consider $\Omega:=[0,1]\subseteq \mathbb{R}$ and $f=\chi_{[0,1] \backslash \mathbb{Q}}$. Then, $f|_{[0,1]\backslash\mathbb{Q}}$ is continuous.
---