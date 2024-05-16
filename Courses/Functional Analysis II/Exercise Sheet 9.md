#Series #FunctionalAnalysis 

> [!def] Problem 1
> Let $F$ be a finite abelian group. Prove $\widehat{F}\cong F$.

Recall that we have $\widehat{G_{1}\times G_{2}}\cong \widehat{G_{1}}\times  \widehat{G_{2}}$ for abelian groups $G_{1},G_{2}$. Therefore, by the fundamental theorem of finitely generated abelian groups, it suffices to show that the statement holds for a cyclic group  $C_{n}=\braket{ a }$. We define: $$\begin{array}{cccc} {J:}&{C_{n}}&\to&{\widehat{C_{n}}}\\&{a^k} &\mapsto & {a^j\mapsto \exp(2\pi ijk /n)} \end{array}{}$$Then, one easily checks that $J(a^k)\in \widehat{C_{n}}$ and:$$J(a^ka^\ell)(a^j)=\exp\left( \frac{2\pi i(k+\ell)j}{n} \right)=\exp\left( \frac{2\pi ikj}{n} \right)\exp\left( \frac{2\pi i\ell j}{n} \right)=J(a^k)(a^j)J(a^\ell)(a^j)$$Further, if $J(a^k)(a^j)=1$ for all $j\in\{ 0,\dots,n-1 \}$, we have that $k=0$ and $\text{ker }J=\{ e \}$. For surjectivity, let $\chi\in \widehat{C_{n}}$. Then, we have that $\chi(a)^n=\chi(a^n)=1$. Therefore, $\chi(a)=\exp(2\pi i k /n)$ for some  $k\in\{ 0,1,\dots,n-1 \}$.  This shows the surjectivity as indeed we have for any $0\leq j<n$, $$\chi(a^j)=\chi(a)^j=\exp(2\pi i jk/n)=J(a^k)(a^j)$$Therefore, the statement holds for a cyclic group $C_{n}$ and this proves the statement.

---
> [!def] Problem 2
> For each $a\in \mathbb{R}$, define the additive character $\chi_{a}(t):=\exp(2\pi iat)$ for $t\in \mathbb{R}$. Prove that the map $$\begin{array}{cccc} {\Psi:}&{\mathbb{R}}&\to&{\widehat{\mathbb{R}}}\\&{a} &\mapsto & {\chi_{a}} \end{array}{}$$ is an isomorphism of topological groups.

We can easily see that $\chi_{a}\in \widehat{\mathbb{R}}$ as it is continuous and: $$\chi_{a}(t+s)=\exp(2\pi ia(t+s))=\chi_{a}(t)\chi_{a}(s)$$

Further, we have $\chi_{a+b}(t)=\exp(2\pi i(a+b)t)=\exp(2\pi iat)\exp(2\pi ibt)=\chi_{a}(t)\chi_{b}(t)$. Moreover, if $\chi_{a}=\widehat{e}$, then $\exp(2\pi iat)=1$ for all $t\in \mathbb{R}$ and $a=0$. 

For surjectivity, let $\chi\in \widehat{\mathbb{R}}$. Then, clearly $\chi\in L^1_{\text{loc}}(\mathbb{R})$ and for $\varphi\in C^1_{0}(\mathbb{R})$, we have that $\varphi*\chi\in C^1(\mathbb{R})$. Therefore, we can see that: $$\chi'(t)=\lim_{ h \to 0 } \frac{\chi(t+h)-\chi(t)}{h}=\lim_{ h \to 0 } \frac{\chi(t)\chi(h)-\chi(t)}{h}=\chi(t)\chi'(0)$$It shows that $\chi(t)=C\exp(\chi'(0)t)$ and as $\chi(0)=1$, $C=1$. This shows that $\Psi$ is surjective.

It is left to show that $\Psi$ is a homeomorphism. Let $a_{n}\to a$ in $\mathbb{R}$. Then, for every $x\in \mathbb{R}$, $$\left| \chi_{a_{n}}(x)-\chi_{a}(x) \right|=\left| \exp(2\pi ia_{n}x)-\exp(2\pi iax) \right|  =\left| \int_{a}^{a_{n}} 2\pi ix\exp(2\pi itx) \, dt  \right| \leq 2\pi \left| x \right| \left| a_{n}-a \right| $$therefore, for any $\varphi\in C^\infty_{00}(\mathbb{R})$ and $\varepsilon>0$, there exists $N\in \mathbb{N}$ s.t. for all $n\geq N$:$$\left| \widehat{\varphi}(\chi_{a_{n}})-\widehat{\varphi}(\chi_{a}) \right|=\left| \int_{\mathbb{R}}^{} \varphi(x)\overline{\chi_{a_{n}}(x)-\chi_{a}(x)} \, dx  \right| \leq  \left| a_{n}-a \right| 2\pi\int_{\text{supp}(\varphi)}^{} \left| \varphi(x) \right| \left| x \right| \, dx < \frac{\varepsilon}{3} $$Consequently, for any $f\in L^1(\mathbb{R})$, there exists $\varphi\in C^\infty_{00}(\mathbb{R})$ s.t. for any $\chi\in \widehat{\mathbb{R}}$, $$\left| \widehat{f}(\chi)-\widehat{\varphi}(\chi) \right| \leq \int_{\mathbb{R}}^{} \left| f(x)-\varphi(x) \right|  \, dx=\|f-\varphi\|_{1}<\varepsilon /3 $$Therefore, for the same $\varphi$ there exists $N\in\mathbb{N}$ s.t. for all $n\geq N$:$$\left| \widehat{f}(\chi_{a_{n}})-\widehat{f}(\chi_{a}) \right| \leq\left| \widehat{f}(\chi_{a_{n}})-\widehat{\varphi}(\chi_{a_{n}}) \right|+\left| \widehat{\varphi}(\chi_{a_{n}})-\widehat{\varphi}(\chi_{a}) \right|+\left| \widehat{f}(\chi_{a})-\widehat{\varphi}(\chi_{a}) \right|<\varepsilon $$For $U:=\mathcal{U}(\chi_{a};f_{1},\dots,f_{n};\varepsilon)$, by taking the maximum $N$ over all $f_{i}\in L^1(\mathbb{R})$, there exists $N\in \mathbb{N}$ s.t. $\chi_{a_{n}}\in U$ for all $n\geq N$. This shows that $\lim_{ n \to \infty }\chi_{a_{n}}=\chi_{a}$ and $\Psi$ is continuous.

Conversely, let $(a_{n})\subseteq \mathbb{R}$ s.t. $\chi_{a_{n}}\to \chi_{a}$ for some $a\in\mathbb{R}$. We have to show that $a_{n}\to a$. 



---
> [!def] Problem 3
> Deduce $\widehat{\mathbb{T}}\cong \mathbb{Z}$ from Exercise 2.

It suffices to show that $\widehat{\mathbb{R} / \mathbb{Z}}\cong \mathbb{Z}$. Let $\pi:\mathbb{R}\to \mathbb{R} / \mathbb{Z}$ be the canonical projection and $\widehat{\pi}:\widehat{\mathbb{R} / \mathbb{Z}}\to \widehat{\mathbb{R}},\chi\mapsto \chi \circ\pi$ the dual map. Consider the map $\Phi=\Psi ^{-1}\circ\widehat{\pi}$. 

Consider the following map: $$\begin{array}{cccc} {\Phi:}&{\widehat{\mathbb{R} / \mathbb{Z}}}&\to&{\mathbb{R}}\\&{\chi} &\mapsto & {\Psi ^{-1}(\chi \circ \pi)} \end{array}{}$$
where $\pi$ is the canonical projection from $\mathbb{R}\to \mathbb{R} / \mathbb{Z}$. 