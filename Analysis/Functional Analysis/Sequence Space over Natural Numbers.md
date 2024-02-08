#Definition #FunctionalAnalysis 

##### Properties
> [!lemma] Theorem 1
> The following subspace: $$C_{0}(\mathbb{N}):=\{ f:\mathbb{N}\to \mathbb{C}|\lim_{ n \to \infty } f(n)=0 \}$$does not admit a closed complement in $\ell^\infty(\mathbb{N})$.

> [!proof]-
> Let $R$ be the complement of $C_{0}(\mathbb{N})$ in $\ell^\infty(\mathbb{N})$. Assume $R$ is closed. Then, there is a bijection: $$\begin{array}{cccc} {\pi|_{R}:}&{R}&\to&{\ell^\infty(\mathbb{N}) /C_{0}(\mathbb{N})}\\&{r} &\mapsto & {r+C_{0}(\mathbb{N})} \end{array}{}$$Therefore, by the [[Bounded Linear Map|open mapping theorem]], $(\pi|_{R})^{-1}$ is a continuous bijection.
> 1. **Showing the existence of a countable set $\mathcal{D}\subseteq R^{*}$ with $\bigcap_{f\in \mathcal{D}}^{}\text{ker }f=(0)$**:
>    For every $n\geq 0$, we define: $$\begin{array}{cccc} {f_{n}:}&{\ell^\infty(\mathbb{N})}&\to&{\mathbb{C}}\\&{g} &\mapsto & {g(n)} \end{array}{}$$Then, $\left| f_{n}(g) \right|=\left| g(n) \right|\leq \left\| g \right\|_{\infty}$ and $f_{n}\in \ell^\infty(\mathbb{N})^{*}$. Further, $\bigcap_{n\geq 0}^{}\text{ker }f_{n}=(0)$. We can restrict each function to $R$ and get $\mathcal{D}:=\{ f_{n}|_{R}:n\geq 0 \}$.
> 2. **Showing for every countable set $\mathcal{D}\subseteq(\ell^\infty(\mathbb{N}) / C_{0}(\mathbb{N}))^{*}$ that $\bigcap_{f\in \mathcal{D}}^{}\text{ker }f\neq(0)$**:
>    From [[Infinitely Countable Sets|Lemma 1]], there exists $\mathcal{A}\subseteq \mathcal{P}(\mathbb{N})$ s.t. 
>    1. for all $U\in \mathcal{A}$, $U$ is infinite.
>    2. for all $U,V\in \mathcal{A}$, $U\cap V$ is finite.
>    3. $\mathcal{A}$ is uncountable.
>       
>    Then, for $U\in \mathcal{A}$, we define: $$f_{U}=\chi_{U}+C_{0}(\mathbb{N})\in \ell^\infty(\mathbb{N}) / C_{0}(\mathbb{N})$$
>    Let $\lambda\in(\ell^\infty(\mathbb{N}) / C_{0}(\mathbb{N}))^{*}$ and consider the set $C_{n}:=\{ U\in \mathcal{A}:\left| \lambda(f_{U}) \right|\geq 1 /n \}$. Let $U_{1},\dots,U_{m}\in C_{n}$. We define: $$f:=\sum_{i=1}^{m} \frac{\overline{\lambda(f_{U_{i}})}}{\left| \lambda(f_{U_{i}}) \right| }f_{U_{i}}$$Then, $\lambda(f)=\sum_{i=1}^{m}\left| \lambda(f_{U_{i}}) \right|\geq m / n$ and $\left| \lambda(f) \right|\leq \left\| \lambda \right\|\cdot\left\| f \right\|_{\ell^\infty(\mathbb{N}) / C_{0}(\mathbb{N})}$.
>    
>    We now define $F:=\bigcup_{i\neq j}^{}(U_{i}\cap U_{j})$. As $F$ is finite, $\chi_{F}\in C_{0}(\mathbb{N})$ and observe: 
>    1. $\tilde{f}:=\sum_{i=1}^{m} \frac{\overline{\lambda(f_{U_{i}})}}{\left| \lambda(f_{U_{i}}) \right| }\chi_{U_{i}}\in f+C_{0}(\mathbb{N})$
>    2. $\tilde{f}\cdot \chi_{F}\in C_{0}(\mathbb{N})$
>    
>    Therefore, $\tilde{f}-\chi_{F}\tilde{f}\in f+C_{0}(\mathbb{N})$ and $$\left\| \tilde{f}-\chi_{F}\tilde{f} \right\| _{\infty}=\sup_{{1\leq i\leq m}}\left| \frac{\overline{\lambda(f_{U_{i}})}}{\left| \lambda(f_{U_{i}}) \right| } \right| =1$$It follows that, $$\frac{m}{n}\leq\left| \lambda(f) \right| \leq \left\| \lambda \right\| \left\| f \right\| _{\ell^\infty(\mathbb{N}) / C_{0}(\mathbb{N})}\leq \left\| \lambda \right\| \left\| \tilde{f}-\chi_{F}\tilde{f} \right\| _{\infty}=\left\| \lambda \right\| $$It follows that $C_{n}$ is finite with $\left| C_{n} \right|\leq \left\| \lambda \right\|n$. 
> 3. **Showing that $R$ cannot be closed**:
> Let $\mathcal{D}\subseteq R^{*}$ be the countable set from Claim 1. Then, for $f\in \mathcal{D}$, $$f\circ (\pi|_{R})^{-1}\in (\ell^\infty(\mathbb{N})/C_{0}(\mathbb{N}))^{*}$$
> and $$\text{ker }f\circ (\pi|_{R})^{-1}=(\pi|_{R})^{-1}[\text{ker }f]$$
> Therefore, for $\{ f\circ(\pi|_{R})^{-1}:f\in \mathcal{D} \}\subseteq(\ell^\infty(\mathbb{N})/C_{0}(\mathbb{N}))^{*}$, it holds that: $$\bigcap_{f\in \mathcal{D}}^{}\text{ker }f\circ (\pi|_{R})^{-1}=\bigcap_{f\in \mathcal{D}}^{}(\pi|_{R})^{-1}[\text{ker }f]=(\pi|_{R})^{-1}[(0)]=(0)$$which is a contradiction to Part 2. 
---