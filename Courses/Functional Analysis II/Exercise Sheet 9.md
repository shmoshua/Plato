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

Conversely, let $(a_{n})\subseteq \mathbb{R}$ s.t. $\chi_{a_{n}}\to \chi_{a}$ for some $a\in\mathbb{R}$. We have to show that $a_{n}\to a$. For $\chi_{[0,1]}\in L^1(\mathbb{R})$  and $\varepsilon>0$ we have $N\in \mathbb{N}$ s.t. $\chi_{a_{n}}\in \mathcal{U}(\chi_{a};\chi_{[0,1]};\varepsilon)$ for $n\geq N$. Then, $$\left| \int_\mathbb{R}\chi_{[0,1]}(x)\overline{\chi_{a_{n}}(x)-\chi_{a}(x)}  \, dx  \right|=\left| \int_{0}^{1} \chi_{a_{n}}(x)-\chi_{a}(x) \, dx  \right|<\varepsilon  $$



---
> [!def] Problem 3
> Deduce $\widehat{\mathbb{T}}\cong \mathbb{Z}$ from Exercise 2.

It suffices to show that $\widehat{\mathbb{R} / \mathbb{Z}}\cong \mathbb{Z}$. Let $\pi:\mathbb{R}\to \mathbb{R} / \mathbb{Z}$ be the canonical projection and $\widehat{\pi}:\widehat{\mathbb{R} / \mathbb{Z}}\to \widehat{\mathbb{R}},\chi\mapsto \chi \circ\pi$ the dual map. Consider the map $\Phi=\Psi ^{-1}\circ\widehat{\pi}$. Let $\chi\in \widehat{\mathbb{R} / \mathbb{Z}}$ and $a:=\Phi(\chi)$. Then, $\chi_{a}=\chi \circ\pi$ and by taking $x=1$, $\exp(2\pi i a)=\chi(1+\mathbb{Z})=0$. Therefore, $a\in \mathbb{Z}$ and $\text{Im } \Phi \subseteq \mathbb{Z}$. Therefore, $\Phi$ is a group homomorphism from $\widehat{\mathbb{R} /\mathbb{Z}}$ to $\mathbb{Z}$. 

Further, if $\Phi(\chi)=0$, then $\chi (\pi(x))=1$ for all $x\in \mathbb{R}$ and $\chi \equiv 1$. Similarly, for $n\in \mathbb{Z}$, we define $\chi\in \widehat{\mathbb{R}/\mathbb{Z}}$ as $\chi(x+\mathbb{Z})=\exp(2\pi inx)$. Then, $\chi$ is well-defined and $\chi\in \widehat{\mathbb{R} / \mathbb{Z}}$. Therefore, $\Phi$ is surjective and $\widehat{\mathbb{R} / \mathbb{Z}}\cong \mathbb{Z}$.

---
> [!def] Problem 4
> Let $F_{n}$ be a finite abelian group for all $n\geq 1$ and put $G:=\prod_{i\geq 1}^{}F_{n}$ with the product topology. Show that $$\widehat{G}\cong\bigoplus_{n\geq 1}F_{n} $$ as topological groups where the group on the right is equipped with the discrete topology. 

Let us define: $$\begin{array}{cccc} {\Psi:}&{\bigoplus_{n\geq 1}\widehat{F_{n}} }&\to&{\widehat{G}}\\&{(\chi_{n})_{n\geq 1}} &\mapsto & {(g_{n})_{n}\mapsto\prod_{n\geq 1}^{}\chi_{n}(g_{n})} \end{array}{}$$
1. **Showing that $\Psi$ is well-defined**:
   For $(\chi_{n})_{n}\in \bigoplus_{n\geq 1}\widehat{F_{n}}$, let $J:=\{ n\geq 1:\chi_{n}\not\equiv 1 \}$, which is finite by definition. Then,  $$\Psi((\chi_{n})_{n})((g_{n})_{n})=\prod_{n\geq 1}^{}\chi_{n}(g_{n})=\prod_{n\in J}^{}\chi_{n}(g_{n})$$and $\Psi((\chi_{n})_{n})$ is a homomorphism as $\chi_{n}$ are and is continuous as it is a finite product of continuous maps.
2. **Showing that $\Psi$ is an isomorphism**:
   Let $\Psi((\chi_{n})_{n})\equiv 1$ for all $(g_{n})_{n}\in G$. For $n\geq 1$, consider $(g_{m})_{m}$ where $g_{m}=e_{F_{m}}$ for all $m\neq n$. Then,$$\Psi((\chi_{n})_{n})((g_{m})_{m})=\chi_{n}(g_{m})=1$$and $\chi_{n}\equiv 1$. Therefore, $\Psi$ is injective. 
   
   For surjectivity, let $\chi\in\widehat{G}$. Let $U:=\varphi\left( \left( -\frac{\pi}{2}, \frac{\pi}{2} \right) \right)\subseteq \mathbb{T}$ where: $$\begin{array}{cccc} {\varphi:}&{{(-\pi,\pi)}}&\to&{\mathbb{T} \backslash\{ -1 \}}\\&{t} &\mapsto & {\exp(it)} \end{array}{}$$As $\varphi$ is a homeomorphism, $U$ is an open neighborhood of $1$ and $\chi ^{-1}(U)$ is an open neighborhood of $(e_{F_{n}})_{n}$. Therefore, there exists a finite $J\subseteq \mathbb{N}$ and $e_{F_{j}}\in U_{j}\subseteq F_{j}$ open for all $j\in J$  s.t. $$\{ (g_{n})_{n}\in G:g_{j}\in U_{j},j\in J  \}\subseteq \chi ^{-1}(U)$$Consider $H:=\prod_{n\geq 1}^{}H_{n}$ where $H_{n}=\{ e_{F_{n}} \}$ for $n\in J$ and $H_{n}=F_{n}$ otherwise. Then, clearly $H\leq G$ and $H\subseteq\{ (g_{n})_{n}\in G:g_{j}\in U_{j},j\in J  \}$. Therefore,  $\chi (H)\subseteq U$.  
   
   We claim that $\chi(H)=\{ 1 \}$. Assume otherwise and let $g\in H$ s.t. $\chi(g)\neq 1$. Then using the homeomorphism above, as $-\pi /2<\varphi ^{-1}(\chi(g))<\pi /2$ there exists $k\in \mathbb{Z}$ s.t. $\pi /2\leq k \varphi ^{-1}(\chi(g))<\pi$. Then, $$\varphi(k\varphi ^{-1}(\chi(g)))=\exp(ik\varphi ^{-1}(\chi(g)))=\varphi(\varphi ^{-1}(\chi(g)))^k=\chi(g)^k=\chi(g^k)\notin U$$which is a contradiction as $g^k\in H$. Therefore, $\chi(H)=\{ 1 \}$.
   
   We now define the following embedding for $n\geq 1$: $$\begin{array}{cccc} {i_{n}:}&{F_{n}}&\to&{G}\\&{g} &\mapsto & {(e_{F_{1}},e_{F_{2}},\dots ,e_{F_{n-1}},g,e_{F_{n+1}},\dots)} \end{array}{}$$Then, one easily checks that $\chi \circ i_{n}\in \widehat{F_{n}}$ and for any $n\notin J$, $\chi (i_{n}(F_{n}))=\{ 1 \}$ as $i_{n}(F_{n})\leq H$. Thus, $(\chi \circ i_{n})_{n}\in \bigoplus_{n\geq 1}\widehat{F_{n}}$ and for $(g_{n})_{n}\in G$ and $h:=(h_{n})_{n}\in H$ defined as: $$h_{n}=\begin{cases}g_{n}&n\notin J\\e_{F_{n}}&n\in J\end{cases}$$we have: $$\Psi((\chi \circ  i_{n})_{n})((g_{n})_{n})=\prod_{n\in J}^{}\chi (i_{n}(g_{n}))=\chi\left( \prod_{n\in J}^{}i_{n}(g_{n}) \right)\chi(h)=\chi((g_{n})_{n})$$This proves that $\Psi$ is an isomorphism.
   
Lastly, notice that $\widehat{G}$ is discrete as $G$ is compact by Tychonoff. This shows that $\Psi$ is a homeomorphism.

---
> [!def] Problem 5
> Let $\chi:\mathbb{Q}_{p}\to \mathbb{T}$ be the continuous character constructed in the lecture (with $\text{ker}(\chi)=\mathbb{Z}_{p}$). For each $a\in \mathbb{Q}_{p}$, define $\chi_{a}(t):=\chi(at)$ for each $t\in \mathbb{Q}_{p}$. Show that the map $$\begin{array}{cccc} {\Psi:}&{\mathbb{Q}_{p}}&\to&{\widehat{\mathbb{Q}_{p}}}\\&{a} &\mapsto & {\chi_{a}} \end{array}{}$$ is an isomorphism of topological groups.

We have that $\chi_{a}=\chi \circ L_{a}$ hence continuous and $\chi_{a}(s+t)=\chi(as+at)=\chi(as)\chi(at)=\chi_{a}(s)\chi_{a}(t)$. Thus, $\chi_{a}\in \widehat{\mathbb{Q}_{p}}$ for any $a\in\mathbb{Q}_{p}$. Further, $$\Psi(a+b)(t)=\chi_{a+b}(t)=\chi((a+b)t)=\chi(at)\chi(bt)=\Psi_{a}(t)\Psi_{b}(t)$$shows that $\Psi$ is a group homomorphism. 

Let $\chi_{a}\equiv 1$. Then, $\chi(at)=1$ for all $t\in\mathbb{Q}_{p}$, i.e. $at\in \mathbb{Z}_{p}$ for all $t\in \mathbb{Q}_{p}$. Therefore, $a=0$ and $\Psi$ is injective. 
   
For surjectivity, let $\chi\in \widehat{\mathbb{Q}_{p}}$. Let $U:=\varphi\left( \left( -\frac{\pi}{2}, \frac{\pi}{2} \right) \right)$ as in the previous exercise. Then, $\chi ^{-1}(U)$ is an open neighborhood of $0$ and as $\{ p^n \mathbb{Z}_{p} :n\geq 0\}$ form the fundamental system of open neighborhoods of $0$ in $\mathbb{Q}_{p}$, there exists $n\geq 0$ s.t. $\chi(p^n\mathbb{Z}_{p})\subseteq U$. As $p^n \mathbb{Z}_{p}\leq \mathbb{Q}_{p}$, similarly as above, $\chi(p^n\mathbb{Z}_{p})=\{ 1 \}$. Therefore, $\tilde{\chi}:\mathbb{Q}_{p}\to \mathbb{T},x\mapsto\chi(p^nx)$ has $\mathbb{Z}_{p}\leq\text{ker }\tilde{\chi}$ and $\tilde{\chi}=\gamma\circ\pi$ where $\pi:\mathbb{Q}_{p}\to \mathbb{Q}_{p} / \mathbb{Z}_{p}$ is the canonical projection and $\gamma\in \widehat{\mathbb{Q}_{p} / \mathbb{Z}_{p}}$. 

We define for $n\geq 1$, the following $A_{-n}:=\{ x\in \mathbb{Q}_{p} /\mathbb{Z}_{p}:p^nx=0 \}\leq \mathbb{Q}_{p} / \mathbb{Z}_{p}$. Then, we claim that $A_{-n}\cong \mathbb{Z} /p^n \mathbb{Z}$. Let $J:\{ z\in \mathbb{C}:z^{p^n}=1 \}\to\mathbb{Q}_{p} / \mathbb{Z}_{p}$ be the isomorphism. Then, consider $P_{n}$ as the $p^n$-th roots of unity. Clearly, we have that for $z\in P_{n}$, $p^nJ(z)=J(z^{p^n})=J(1)=0$. 

Consider the map: $$\begin{array}{cccc} {\Phi:}&{\mathbb{Z} /p^n \mathbb{Z}}&\to&{\widehat{A_{-n}}}\\&{s} &\mapsto & {x\mapsto} \end{array}{}$$ Let $\gamma\in \widehat{A_{-n}}$. Then, 




