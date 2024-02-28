#Series #Analysis 

> [!definition] Problem 1: Inclusion between Lp spaces.
> For $L^p$ spaces:
> 1. is it true that if $f\in L^1(\mathbb{R}^n)$ then $f\in L^2(\mathbb{R}^n)$?
> 2. is it true that if $f\in \ell^1(\mathbb{N})$ then $f\in \ell^2(\mathbb{N})$?
> 3. Give an example of a function that is $L^{99}(0,1)$ but not $L^{100}(0,1)$. Could you find one also in $L^{100}(0,1)\backslash L^{99}(0,1)$?

We have:
1. Consider $f(x)= \frac{1}{\sqrt{ x }}\chi_{(0,1]}(x)$. Then, $$\left\| f \right\| _{1}=\int_{0}^{1}  \frac{1}{\sqrt{ x }} \, dx =2,\quad \left\| f \right\| _{2}^{2}=\int_{0}^{1} \frac{1}{x} \, dx=\infty$$
2. Yes. Assume that $\sum_{n=0}^{\infty}\left| f(n) \right|<+\infty$. Then, $\lim_{ n \to \infty }f(n)=0$ and there exists $N\geq 0$ s.t. $\left| f(n) \right|<1$ for all $N\geq n$. Therefore, $\left| f(n) \right|^{2}\leq \left| f(n) \right|$ and $$\sum_{n=0}^{\infty}\left| f(n) \right| ^{2}\leq\sum_{n=0}^{N}\left| f(n) \right| ^{2}+\sum_{n=0}^{\infty}\left| f(n) \right| <+\infty$$
3. Let $f(x)=x^{- 1/100}$. Then, $$\left\| f \right\|_{99}^{99}=\int_{0}^{1}  \frac{1}{x^{99/100}}  \, dx =100, \quad \left\| f \right\| _{100}^{100}=\int_{0}^{1} \frac{1}{x} \, dx =\infty$$$L^{100}(0,1) \backslash L^{99}(0,1)=\varnothing$ as $\mathcal{L}^1(0,1)=1<+\infty$ and $L^{100}(0,1)\subseteq L^{99}(0,1)$.
---
> [!definition] Problem 2: Exchanging limits and integrals.
> Consider
> 1. Recall that the DCT implies that a collection of measurable functions $f_{n}:\mathbb{R}\to \mathbb{C}$, satisfying $\left| f_{n} \right|\leq g$ for some $g\in L^1(\mathbb{R})$, also satisfies $$\lim_{ n \to \infty } \int_{\mathbb{R}}^{} f_{n}(x) \, dx =\int_{\mathbb{R}}^{} \left( \lim_{ n \to \infty } f_{n}(x) \right)  \, dx $$ whenever the pointwise limit $\lim_{ n \to \infty }f_{n}(x)$ exists a.e. Show, via a counterexample, that the hypothesis $\left| f_{n} \right|\leq g\in L^1(\mathbb{R})$ is necessary. 
> 2. Let $(f_{n})_{n\in\mathbb{N}}$ be a collection of non-negative measurable functions. Is it true that $$\sum_{n=1}^{\infty}\int_{\mathbb{R}}^{} f_{n}(x) \, dx =\int_{\mathbb{R}}^{}\sum_{n=1}^{\infty}f_{n}(x)  \, dx $$

We have:
1. Let $f_{n}=\chi_{[n,n+1]}$. Then, $\left| f_{n} \right|\leq 1$ where $1\notin L^1(\mathbb{R})$. It follows that:
	$$\lim_{ n \to \infty } \int_{n}^{n+1} 1 \, dx=1\neq 0= \int_{\mathbb{R}}^{} \left( \lim_{ n \to \infty } f_{n}(x) \right) \, dx  $$
2. We define $s_{n}:=\sum_{k=1}^{n}f_{k}$. Then, $(s_{n})_{n}$ is an increasing sequence of measurable functions. Therefore, using monotone convergence theorem: $$\int_{\Omega}^{}\sum_{k=1}^{\infty}f_{k} \, d\mu=\int_{\Omega}^{} \lim_{ n \to \infty } \sum_{k=1}^{n}f_{k} \, d\mu=\lim_{ n \to \infty } \int_{\Omega}^{} \sum_{k=1}^{n}f_{k} \, d\mu=\lim_{ n \to \infty } \sum_{k=1}^{n}\int_{\Omega}^{} f_{k} \, d\mu =\sum_{k=1}^{\infty}\int_{\Omega}^{} f_{k} \, d\mu  $$

---
> [!definition] Problem 3: Completeness and Cauchy sequences
> Consider:
> 1. Is it true that a Cauchy sequence (say, in a metric space) can have at most one limit?
> 2. Is it true that the interval $(0,1)\subseteq \mathbb{R}$ is complete?
> 3. Consider the sequence of functions $f_{n}:(0,+\infty)\to \mathbb{R}$ defined by $$f_{n}(x)=\frac{\tanh(x)}{x}\chi_{(0,n)}(x)$$Determine the pointwise limit $f$ and discuss the convergence $f_{n}\to f$ in $L_2$. Is the limit also in $L_{1}$? What can we deduce about the completeness of $L_{1}$ with respect to $\|\cdot\|_{2}$?
> 4. Can you build a sequence of functions $\{ f_{k} \}_{k}\subseteq L^2(\mathbb{R})$ s.t. $$\int_{\mathbb{R}}^{} \left| f_{k}(x)-1 \right| ^{2} \, dx \xrightarrow{k\to \infty}0$$

We have:
1. Let $(x_{n})\subseteq X$ be a Cauchy sequence and $\{ x_{k_{n}} \}$ and $\{ x_{p_{n}} \}$ be two subsequences s.t. $x_{k_{n}}\xrightarrow{n\to \infty}x$ and $x_{p_{n}}\xrightarrow{n\to \infty}y$. Let $\varepsilon>0$. Then, there exists $N_{1},N_{2},N_{3}\geq 0$ s.t.$$\left| x-y \right| \leq \left| x-x_{k_{n}} \right| +\left| x_{k_{n}}-x_{p_{n}} \right| +\left| x_{p_{n}}-y \right|\leq \frac{\varepsilon}{3}+\frac{\varepsilon}{3}+\frac{\varepsilon}{3}=\varepsilon $$for all $n\geq \text{max}\{ N_{1},N_{2},N_{3} \}$. Therefore, $x=y$.
2. $\left( \frac{1}{n} \right)_{n}$ is a Cauchy sequence, but $\lim_{ n \to \infty } \frac{1}{n}=0$ is not in $(0,1)$.
3. $f_{n}$ converges to $f(x)= \tanh(x) /x$ pointwise. Further, as $f$ is a decreasing function, for every $\varepsilon>0$, there exists $x_{0}$ s.t. $f(x)\leq \varepsilon$ for all $x\geq x_{0}$. Therefore, $f_{n}\xrightarrow{\mu} f$. Further, $$\lim_{ n \to \infty } \left\| f_{n} \right\| _{2}^2=\lim_{ n \to \infty } \int_{0}^{n}\frac{\tanh(x)^{2}}{x^{2}}  \, dx =\int_{0}^{\infty} \frac{\tanh(x)^{2}}{x^{2}}   \, dx=\left\| f \right\| _{2}^2 $$This shows that $f_{n}\xrightarrow{L^2}f$. However, $f\notin L^1(0,\infty)$. Therefore, $L^1$ is not complete w.r.t. the $\|\cdot\|_{2}$ norm as $f_{n}$ is a Cauchy sequence.
4. Assume we have $\{ f_{k} \}\subseteq L^2(\mathbb{R})$ s.t. $\lim_{ k \to \infty } \left\| f_{k}-1 \right\|_{2}=0$. Then, $$\left\| 1 \right\| _{2}\leq \left\| f_{k} \right\|_{2} +\left\| f_{k}-1 \right\|_{2} <+\infty$$which is a contradiction as $1\notin  L^2(\mathbb{R})$.
---
> [!definition] Problem 4: Approximability in normed spaces
> Determine whether the following statements are true or false and justify your answer.
> 1. $L^1([0,1])\subseteq \overline{C([0,1])}^{L^1}$
> 2. $L^\infty([0,1])\subseteq \overline{C([0,1])}^{L^\infty}$
> 3. $L^1([0,1])\subseteq \overline{S([0,1])}^{L^1}$
> 4. $L^\infty([0,1])\subseteq \overline{S([0,1])}^{L^\infty}$
> 5. $L^\infty([0,1])\subseteq \overline{C([0,1])}^{L^1}$
> 6. $C((0,1))\subseteq \overline{C_{c}((0,1))}^{L^\infty}$

We have:
1. **$C([0,1])$ is dense in $L^1([0,1])$**:
   Let $f\in L^1([0,1])$ and $\varepsilon>0$. Then, choose $N$ s.t. $$\left\| f-f\chi_{f^{-1}([-N,N])} \right\| \leq \varepsilon$$Let $f_{\varepsilon}:=f\chi_{f^{-1}([-N,N])}$. By Lusin's theorem, there exists a compact set $K$ s.t. $\mu([0,1] \backslash K)\leq \varepsilon /2N$ and $f_{\varepsilon}|_{K}$ is continuous. As $K$ is closed, using Tietze's extension theorem, we can extend $f_{\varepsilon}|_{K_{\varepsilon}}$ to $g_{\varepsilon}$ that is continuous on $[0,1]$ and still bounded by $N$. Therefore, $$\begin{align}\left\| f-g_{\varepsilon} \right\|_{1} &\leq \left\| f-f_{\varepsilon} \right\|_{1}+\left\| f_{\varepsilon}-g_{\varepsilon} \right\| _{1}\\&\leq \varepsilon+\int_{[0,1] \backslash K}^{} \left| f_{\varepsilon}-g_{\varepsilon} \right|  \, dx  \\&\leq \varepsilon+\mu([0,1 ]\backslash K)\cdot  2N\\&\leq 2\varepsilon  \end{align}$$
2. **$C([0,1])$ is not dense in $L^\infty([0,1])$**:
	Consider $f=\chi_{[1 / 2,1]}$. For any continuous function $g\in C([0,1])$, if $\left\| f-g \right\|_{\infty}< \frac{1}{3}$, then for $x<1 /2$, $g< \frac{1}{3}$ $\mu$-a.e. and for $x\geq 1 / 2$, $g > 2 / 3$ $\mu$-a.e. However, by intermediate value theorem and continuity, $g^{-1}\left( \left( \frac{1}{3}, \frac{2}{3} \right) \right)$ is an non-empty open set, which has non-zero measure. This is a contradiction.
3. **$S([0,1])$ is dense in $L^1([0,1])$**:
	For $f\in L^1([0,1])$ let $f=f^+-f^-$ with $f^+:=f\cdot \chi_{f^{-1}([0,+\infty))}$ and $f^-:=-f\cdot \chi_{f^{-1}((-\infty,0])}$ Then, both functions are non-negative. Let $\varepsilon>0$. Then, there exists step functions $g^+,g^-\in S([0,1])$ s.t. $$\left\| f^\pm- g^\pm \right\|_{1} < \varepsilon $$ Therefore, $\left\| f-g \right\|_{1}\leq \left\| f^+ -g^+ \right\|_{1}+\left\| f^- -g^- \right\|_{1}<2\varepsilon$. 
4. **$S([0,1])$ is not dense in $L^\infty([0,1])$**:
	Consider $f=\sum_{n=1}^{\infty}\chi_{\left[  \frac{1}{2n-1}, \frac{1}{2n} \right]}$. Then, $f\in L^\infty([0,1])$. But for any step function $g$, $\left\| f-g \right\|_{\infty}> \frac{1}{2}$.
5. **$C([0,1])$ is dense in $(L^\infty([0,1]),\|\cdot\|_{1})$**: 
	   As $\mu([0,1])=1$, $L^\infty([0,1])\subseteq L^1([0,1])\subseteq \overline{C([0,1])}^{L^1}$. 
6. **$C_{c}((0,1))$ is dense in $C((0,1))$ w.r.t the sup norm**:
		$C_{c}((0,1))$ is dense in $C_{0}((0,1))$, the space of functions on $(0,1)$ that vanish at infinity, w.r.t. the sup norm. However, as $(0,1)$ is bounded, $C_{0}((0,1))=C((0,1))$.
---