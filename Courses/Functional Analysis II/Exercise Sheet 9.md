#Series #FunctionalAnalysis 

> [!def] Problem 1
> Let $F$ be a finite abelian group. Prove $\widehat{F}\cong F$.

Recall that we have $\widehat{G_{1}\times G_{2}}\cong \widehat{G_{1}}\times  \widehat{G_{2}}$ for abelian groups $G_{1},G_{2}$. Therefore, by the fundamental theorem of finitely generated abelian groups, it suffices to show that the statement holds for a cyclic group  $C_{n}=\braket{ a }$. We define: $$\begin{array}{cccc} {J:}&{C_{n}}&\to&{\widehat{C_{n}}}\\&{a^k} &\mapsto & {a^j\mapsto \exp(2\pi ijk /n)} \end{array}{}$$Then, one easily checks that $J(a^k)\in \widehat{C_{n}}$ and:$$J(a^ka^\ell)(a^j)=\exp\left( \frac{2\pi i(k+\ell)j}{n} \right)=\exp\left( \frac{2\pi ikj}{n} \right)\exp\left( \frac{2\pi i\ell j}{n} \right)=J(a^k)(a^j)J(a^\ell)(a^j)$$Further, if $J(a^k)(a^j)=1$ for all $j\in\{ 0,\dots,n-1 \}$, we have that $k=0$ and $\text{ker }J=\{ e \}$. For surjectivity, let $\chi\in \widehat{C_{n}}$. Then, we have that $\chi(a)^n=\chi(a^n)=1$. Therefore, $\chi(a)=\exp(2\pi i k /n)$ for some  $k\in\{ 0,1,\dots,n-1 \}$.  This shows the surjectivity as indeed we have for any $0\leq j<n$, $$\chi(a^j)=\chi(a)^j=\exp(2\pi i jk/n)=J(a^k)(a^j)$$Therefore, the statement holds for a cyclic group $C_{n}$ and this proves the statement.

---
> [!def] Problem 2
> For each $a\in \mathbb{R}$, define the additive character $\chi_{a}(t):=\exp(2\pi iat)$ for $t\in \mathbb{R}$. Prove that the map $$\begin{array}{cccc} {\Psi:}&{\mathbb{R}}&\to&{\widehat{\mathbb{R}}}\\&{a} &\mapsto & {\chi_{a}} \end{array}{}$$ is an isomorphism of topological groups.

We can easily see that $\chi_{a}\in \widehat{\mathbb{R}}$ as it is continuous and: $$\chi_{a}(t+s)=\exp(2\pi ia(t+s))=\chi_{a}(t)\chi_{a}(s)$$

Further, we have $\chi_{a+b}(t)=\exp(2\pi i(a+b)t)=\exp(2\pi iat)\exp(2\pi ibt)=\chi_{a}(t)\chi_{b}(t)$. Moreover, if $\chi_{a}=\widehat{e}$, then $\exp(2\pi iat)=1$ for all $t\in \mathbb{R}$ and $a=0$. 

For surjectivity, let $\chi\in \widehat{\mathbb{R}}$. Then, clearly $\chi\in L^1_{\text{loc}}(\mathbb{R})$ and for $\varphi\in C^1_{0}(\mathbb{R})$, we have that $\varphi*\chi\in C^1(\mathbb{R})$. Therefore, we can see that: $$\chi'(t)=\lim_{ h \to 0 } \frac{\chi(t+h)-\chi(t)}{h}=\lim_{ h \to 0 } \frac{\chi(t)\chi(h)-\chi(t)}{h}=\chi(t)\chi'(0)$$It shows that $\chi(t)=\exp(\chi'(0)t)$ and $\Psi$ is surjective.

It is left to show that $\Psi$ is continuous. Let $\chi\in \widehat{\mathbb{R}}$, $f_{1},\dots,f_{n}\in L^1(\mathbb{R})$ and $\varepsilon>0$. Let further, $$U:=\mathcal{U}(\chi;f_{1},\dots,f_{n};\varepsilon)$$For $a\in \Psi^{-1}(U)$, 

