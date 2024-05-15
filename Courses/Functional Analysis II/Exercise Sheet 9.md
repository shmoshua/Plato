#Series #FunctionalAnalysis 

> [!def] Problem 1
> Let $F$ be a finite abelian group. Prove $\widehat{F}\cong F$.

Recall that we have $\widehat{G_{1}\times G_{2}}\cong \widehat{G_{1}}\times  \widehat{G_{2}}$ for abelian groups $G_{1},G_{2}$. Therefore, by the fundamental theorem of finitely generated abelian groups, it suffices to show that the statement holds for a cyclic group  $C_{n}=\braket{ a }$. We define: $$\begin{array}{cccc} {J:}&{C_{n}}&\to&{\widehat{C_{n}}}\\&{a^k} &\mapsto & {a^j\mapsto \exp(2\pi ijk /n)} \end{array}{}$$Then, $$J(a^ka^\ell)(a^j)=\exp\left( \frac{2\pi i(k+\ell)j}{n} \right)=\exp\left( \frac{2\pi ikj}{n} \right)\exp\left( \frac{2\pi i\ell j}{n} \right)=J(a^k)(a^j)J(a^\ell)(a^j)$$Further, if $J(a^k)(a^j)=1$ for all $j\in\{ 0,\dots,n-1 \}$, we have that $k=0$ and $\text{ker }J=\{ e \}$. For surjectivity, let $\chi\in \widehat{C_{n}}$. Then, we have that $\chi(a)^n=\chi(a^n)=1$. Therefore, $\chi(a)=\exp(2\pi i k /n)$ for some  $k\in\{ 0,1,\dots,n-1 \}$.  This shows the surjectivity as indeed we have for any $0\leq j<n$, $$\chi(a^j)=\chi(a)^j=\exp(2\pi i jk/n)=J(a^k)(a^j)$$Therefore, the statement holds for a cyclic group $C_{n}$ and this proves the statement.

---
> [!def] Problem 2
> For each $a\in \mathbb{R}$, define the additive character $\chi_{a}(t):=\exp(2\pi iat)$ for $t\in \mathbb{R}$. Prove that the map $$\begin{array}{cccc} {\Psi:}&{\mathbb{R}}&\to&{\widehat{\mathbb{R}}}\\&{a} &\mapsto & {\chi_{a}} \end{array}{}$$ is an isomorphism of topological groups.

We first show that $\Psi$ is continuous. 
