#Series #FunctionalAnalysis 

> [!def] Problem 1
> Let $F$ be a finite abelian group. Prove $\widehat{F}\cong F$.

Recall that we have $\widehat{G_{1}\times G_{2}}\cong \widehat{G_{1}}\times  \widehat{G_{2}}$ for abelian groups $G_{1},G_{2}$. Therefore, by the fundamental theorem of finitely generated abelian groups, it suffices to show that the statement holds for a cyclic group  $C_{n}=\braket{ a }$. We define: $$\begin{array}{cccc} {\Psi:}&{C_{n}}&\to&{\widehat{C_{n}}}\\&{a^k} &\mapsto & {a^j\mapsto \exp(2\pi ijk /n)} \end{array}{}$$Then, $\Psi(a^k)=\Psi(a)^k$, therefore, $\Psi(a^k)\in \widehat{C_{n}}$ and $\Psi$ is a group homomorphism. Further, if $\Psi(a^k)=1$, we have that $k=0$ and $\text{ker }\Psi=\{ e \}$. For surjectivity, let $\chi\in \widehat{C_{n}}$. Then, we have that $\chi(a)^n=\chi(a^n)=1$. Therefore, $\chi(a)=\exp(2\pi i k /n)$ for some  $k\in\{ 0,1,\dots,n-1 \}$.  This shows the surjectivity as indeed we have for any $0\leq j<n$, $\chi(a^j)=\chi(a)^j=\exp(2\pi i jk/n)=\Psi(a^k)(a^j)$.

---
> [!def] Problem 2
> For each $a\in \mathbb{R}$, define the additive character $\chi_{a}(t):=\exp(2\pi iat)$ for $t\in \mathbb{R}$. Prove that the map $$\begin{array}{cccc} {\Psi:}&{\mathbb{R}}&\to&{\widehat{\mathbb{R}}}\\&{a} &\mapsto & {\chi_{a}} \end{array}{}$$ is an isomorphism of topological groups.

We can easily see that $\chi_{a}\in \widehat{\mathbb{R}}$ as it is continuous and $\chi_{a}(t+s)=\exp(2\pi ia(t+s))=\chi_{a}(t)\chi_{a}(s)$.

Further, we have $\chi_{a+b}(t)=\exp(2\pi i(a+b)t)=\exp(2\pi iat)\exp(2\pi ibt)=\chi_{a}(t)\chi_{b}(t)$. Moreover, if $\chi_{a}=\widehat{e}$, then $\exp(2\pi iat)=1$ for all $t\in \mathbb{R}$ and $a=0$. Therefore, $\Psi$ is an injective group homomorphism. We will proceed as follows to show the rest:
1. **$\Psi$ is surjective**:
   let $\chi\in \widehat{\mathbb{R}}$. Then, clearly $\chi\in L^1_{\text{loc}}(\mathbb{R})$ and for $\varphi\in C^1_{0}(\mathbb{R})$, we have that $\varphi*\chi\in C^1(\mathbb{R})$. Therefore, $\chi$ is differentiable and we can see that: $$\chi'(t)=\lim_{ h \to 0 } \frac{\chi(t+h)-\chi(t)}{h}=\lim_{ h \to 0 } \frac{\chi(t)\chi(h)-\chi(t)}{h}=\chi(t)\chi'(0)$$It shows that $\chi(t)=C\exp(\chi'(0)t)$ and as $\chi(0)=1$, $C=1$. This shows that $\Psi$ is surjective.
2. **$\Psi$ is continuous**:
   As $\mathbb{R}$ is a topological group, we only need to show continuity at $0$. Let: $$N(r,\varepsilon):=\left\{  \chi_{a}\in \widehat{\mathbb{R}}:\left| (x,\chi_{a})-1 \right| <\varepsilon, \forall x\in B_{\leq r}(0) \right\}$$Then, $N(r,\varepsilon)$ forms a basis of the neighborhood of $1\in \widehat{\mathbb{R}}$. We have that $$\left| (x,\chi_{a})-1 \right| =\left| \int_{0}^{a} 2\pi ix \exp(2\pi itx) \, dx  \right| \leq 2\pi \left| x \right| \left| a \right| \leq 2\pi r \left| a \right| $$Therefore, $B_{<\varepsilon /2\pi r}(0)\subseteq \Psi ^{-1}(N(r,\varepsilon))$ and $\Psi$ is continuous at $0$.
3. **$\Psi ^{-1}$ is continuous**:
   Similarly, we show this at $1\in \widehat{\mathbb{R}}$. Let $\varphi:(-1,1)\to \mathbb{T} \backslash\{ -1 \},t\mapsto \exp(2\pi it)$. Then, as $\varphi$ is a homeomorphism, for any $r>0$ there exists $\varepsilon>0$ s.t. if $\left| \exp(2\pi ia)-1 \right|<\varepsilon$ for $-1\leq a\leq 1$ then $\left| a \right|<r$. Therefore, if $a\in \Psi ^{-1}(N(1,\varepsilon))$ then as $1\in B_{\leq 1}(0)$: $$\left| (1,\chi_{a})-1 \right| =\left| \exp(2\pi ia)-1 \right|<\varepsilon $$and $\left| a \right|<r$. It follows that $\Psi ^{-1}(N(1,\varepsilon))\subseteq B_{<r}(0)$ and $\Psi ^{-1}$ is continuous. 

---
> [!def] Problem 3
> Deduce $\widehat{\mathbb{T}}\cong \mathbb{Z}$ from Exercise 2.

It suffices to show that $\widehat{\mathbb{R} / \mathbb{Z}}\cong \mathbb{Z}$ as $\mathbb{R} / \mathbb{Z}\cong \mathbb{T}$. Let $n\in \mathbb{Z}$. Then, $\text{ker }\chi_{n}=\mathbb{Z}$ and $\chi_{n}$ can be factored into $\tilde{\chi}\circ\pi$ where $\pi:\mathbb{R}\to \mathbb{R} / \mathbb{Z}$ is the canonical projection and $\tilde{\chi}\in \widehat{\mathbb{R} / \mathbb{Z}}$. Conversely, for any $\gamma\in \widehat{\mathbb{R} / \mathbb{Z}}$, $\gamma \circ\pi$ is a continuous character on $\mathbb{R}$. Therefore, $\mathbb{Z}\cong \widehat{\mathbb{T}}$ as topological groups. 

---
> [!def] Problem 4
> Let $F_{n}$ be a finite abelian group for all $n\geq 1$ and put $G:=\prod_{i\geq 1}^{}F_{n}$ with the product topology. Show that $$\widehat{G}\cong\bigoplus_{n\geq 1}F_{n} $$ as topological groups where the group on the right is equipped with the discrete topology. 

Let us define: $$\begin{array}{cccc} {\Psi:}&{\bigoplus_{n\geq 1}\widehat{F_{n}} }&\to&{\widehat{G}}\\&{(\chi_{n})_{n\geq 1}} &\mapsto & {(g_{n})_{n}\mapsto\prod_{n\geq 1}^{}\chi_{n}(g_{n})} \end{array}{}$$
1. **$\Psi$ is well-defined**:
   For $(\chi_{n})_{n}\in \bigoplus_{n\geq 1}\widehat{F_{n}}$, let $J:=\{ n\geq 1:\chi_{n}\not\equiv 1 \}$, which is finite by definition. Then,  $$\Psi((\chi_{n})_{n})((g_{n})_{n})=\prod_{n\geq 1}^{}\chi_{n}(g_{n})=\prod_{n\in J}^{}\chi_{n}(g_{n})$$and $\Psi((\chi_{n})_{n})$ is a continuous character as a finite diagonal product of continuous characters.
2. **$\Psi$ is injective**:
   Let $\Psi((\chi_{n})_{n})\equiv 1$ for all $(g_{n})_{n}\in G$. For $n\geq 1$, consider the injection: $$i_{n}:F_{n}\hookrightarrow G,x\mapsto(e_{F_{1}},e_{F_{2}},\dots,e_{F_{n-1}},x,e_{F_{n+1}},\dots)$$Then, $\Psi((\chi_{n})_{n})(i_{n}(x))=\chi_{n}(x)=1$ for all $x\in F_{n}$ and $\chi_{n}=1$ for all $n\geq 1$. This proves that $\Psi$ is injective.
3. **There exists $1\in V\subseteq \mathbb{T}$ s.t. for any subgroup $H\leq \mathbb{T}$ with $H\subseteq V$ has $H=\{ 1 \}$**:
   Consider the homeomorphism: $$\varphi:(-\pi,\pi)\to \mathbb{T} \backslash\{ -1 \},t\mapsto \exp(it)$$Then, let $V:=\varphi((-\pi /2,\pi /2))\ni 1$ and $H$ a subgroup contained in $V$. Then, if $1\neq x\in H$, by the homeomorphism, there exists $k\in \mathbb{Z}$ s.t. $\pi /2\leq k\varphi ^{-1}(x)<\pi$. However, $$\varphi(k\varphi ^{-1}(x))=\exp(ik\varphi ^{-1}(x))=\varphi(\varphi ^{-1}(x))^k=x^k\in H$$and $H\not\subseteq V$, which is a contradiction.
4. **$\Psi$ is surjective**:
   Let $\chi\in \widehat{G}$ and $V$ from 3. Then, $\chi ^{-1}(V)$ is an open neighborhood of $(e_{F_{n}})_{n}$ and there exists a finite $J\subseteq \mathbb{N}$ and $e_{F_{j}}\subseteq V_{j}\subseteq F_{j}$ open for all $j\in J$ s.t. $$W:=\{ (g_{n})_{n}\in G:g_{j}\in V_{j},\forall j\in J  \}\subseteq \chi ^{-1}(V)$$
   Let $H:=\prod_{n\in J}^{}\{ e_{F_{n}} \}\times \prod_{n\notin J}^{}F_{n}$ be a subgroup of $G$. Then, as $H\subseteq W$, $\chi(H)\subseteq V$ and $\chi(H)$ is a subgroup of $\mathbb{T}$ as $\chi$ is a group homomorphism. Therefore, $\chi(H)=\{ 1 \}$.
   
   For $n\geq 1$, $\chi \circ i_{n}\in \widehat{F_{n}}$ and for any $n\notin J$, $\chi(i_{n}(F_{n}))=\{ 1 \}$ as $i_{n}(F_{n})\leq H$. Thus, $(\chi \circ i_{n})_{n}\in \bigoplus_{n\geq 1}\widehat{F_{n}}$. Moreover, for $(g_{n})_{n}\in G$ and $h:=(h_{n})_{n}\in H$ s.t. $h_{n}=g_{n}$ for $n\notin J$ and $h_{n}=e_{F_{n}}$ for $n\in J$, $h\in H$ and $\chi(h)=1$. Therefore, $$\Psi((\chi \circ  i_{n})_{n})((g_{n})_{n})=\prod_{n\in J}^{}\chi (i_{n}(g_{n}))=\chi\left( \prod_{n\in J}^{}i_{n}(g_{n}) \right)\chi(h)=\chi\left( h+\prod_{n\in J}^{}i_{n}(g_{n}) \right)=\chi((g_{n})_{n})$$
   
Lastly, notice that $\widehat{G}$ is discrete as $G$ is compact by Tychonoff. This shows that $\Psi$ is a homeomorphism.

---
> [!def] Problem 5
> Let $\chi:\mathbb{Q}_{p}\to \mathbb{T}$ be the continuous character constructed in the lecture (with $\text{ker}(\chi)=\mathbb{Z}_{p}$). For each $a\in \mathbb{Q}_{p}$, define $\chi_{a}(t):=\chi(at)$ for each $t\in \mathbb{Q}_{p}$. Show that the map $$\begin{array}{cccc} {\Psi:}&{\mathbb{Q}_{p}}&\to&{\widehat{\mathbb{Q}_{p}}}\\&{a} &\mapsto & {\chi_{a}} \end{array}{}$$ is an isomorphism of topological groups.

We first show that $\widehat{\mathbb{Q}_{p} / \mathbb{Z}_{p}}\cong \mathbb{Z}_{p}$. For $n\geq 1$,  let $A_{-n}:=\{ x\in \mathbb{Q}_{p} /\mathbb{Z}_{p}:p^nx=0 \}$. 
1. **Claim: $\mathbb{Q}_{p} / \mathbb{Z}_{p}=\bigcup_{n\geq 1}^{}A_{-n}$**. 
   Indeed, for $x\in \mathbb{Q}_{p}$, take $N(x):=\max\{ -v_{p}(x),1 \}$.
   - if $x\neq 0$, then $p^{N(x)}(x+\mathbb{Z}_{p})=p^{N(x)}(p^{v_{p}(x)}u+\mathbb{Z}_{p})=\mathbb{Z}_{p}$. Hence $x+\mathbb{Z}_{p}\in A_{-N(x)}$. 
   - If $x=0$, $px=0$ and $x+\mathbb{Z}_{p}\in A_{-N(x)}$ 
     
    The other inclusion is given by the definition of $A_{-n}$. 

Now, recall the surjective homomorphism $J:\mathbb{Q}_{p}\to \{ z\in \mathbb{T}| \exists n\geq 1:z^{p^n}=1 \}$ with $\text{ker }J=\mathbb{Z}_{p}$, i.e. we can factor it to $J=\tilde{J}\circ\pi$ where $\pi$ is the canonical projection and $\tilde{J}$ the isomorphism. Consider the map: $$\begin{array}{cccc} {\Phi:}&{\mathbb{Z}_{p}}&\to&{\widehat{\mathbb{Q}_{p} / \mathbb{Z}_{p}}},&{a} &\mapsto & {(x+\mathbb{Z}_{p}\mapsto J(ax))} \end{array}{}$$ Then, as $\mathbb{Q}_{p} / \mathbb{Z}_{p}$ is discrete, $\Phi(a)$ is a continuous group homomorphism. Further, $$\Phi(a+b)(x)=J((a+b)x)=J(ax+bx)=J(ax)J(bx)=\Phi(a)(x)\Phi(b)(x)$$Therefore, $\Phi$ is a group homomorphism. Further, $\Phi$ is injective as if $\Phi(a)(x)=1$ for all $x\in\mathbb{Q}_{p} / \mathbb{Z}_{p}$, then $ax\in \text{ker }J=\mathbb{Z}_{p}$ for all $x\in \mathbb{Q}_{p}$ and $a=0$. 

Let $\gamma\in \widehat{\mathbb{Q}_{p} / \mathbb{Z}_{p}}$. One easily sees that $\gamma|_{A_{-n}}\in \widehat{A_{-n}}$. Further, $\tilde{J}^{-1}(\exp(2\pi im / p^n))\in A_{-n}$ for any $m\in \mathbb{Z}$:$$p^n\tilde{J}^{-1}(\exp(2\pi i m / p^n))=\tilde{J}^{-1}(\exp(2\pi i m))=\tilde{J}^{-1}(1)=0$$Therefore, for $\phi_{n}:\mathbb{Z} / p^n \mathbb{Z} \to \mathbb{T}, m+p^n\mathbb{Z} \mapsto\gamma(\tilde{J}^{-1}(\exp(2\pi i m /p^n)))$ is a well-defined function and $\phi_{n}\in \widehat{\mathbb{Z} / p^n \mathbb{Z}}$, i.e. there exists $a_{n}\in \mathbb{Z} / p^n \mathbb{Z}$ s.t. $\phi_{n}(m)=\exp(2\pi ia_{n}m /p^n)$ for all $m\in \mathbb{Z} / p^n \mathbb{Z}$. We claim that $a:=(a_{n})_{n}\in \mathbb{Z}_{p}$ and $\Phi(a)=\gamma$. 
1. **Claim: $a\in \mathbb{Z}_{p}$**
   For $0\leq m<p^n$, $$\exp(2\pi ia_{n+1}m /p^n)=\phi_{n+1}(pm)=\gamma(\tilde{J}^{-1}(\exp(2\pi im /p^n)))=\phi_{n}(m)=\exp(2\pi ia_{n} m / p^n)$$Therefore, $\exp(2\pi i(a_{n+1}-a_{n}) m / p^n)=1$ for all $m\in \mathbb{Z} / p^n \mathbb{Z}$ which implies that $a_{n+1}-a_{n}\in p^n\mathbb{Z}$.
2. **Claim $\Phi(a)=\gamma$**:
   Let $x\in \mathbb{Q}_{p}$. As $x+\mathbb{Z}_{p}\in A_{-N(x)}$, there exists $m\in \mathbb{Z} / p^{N(x)}\mathbb{Z}$ s.t. $J(x)=\exp(2\pi i m / p^{N(x)})$, as  $J(x)^{p^{N(x)}}=\tilde{J}(x+\mathbb{Z}_{p})^{p^{N(x)}}=\tilde{J}(p^{N(x)}(x+\mathbb{Z}_{p}))=\tilde{J}(0)=1$. Furthermore, by the definition of $N(x)$, $(a-a_{N(x)})x\in \mathbb{Z}_{p}$ and $\pi(ax)=\pi(a_{N(x)}x)$. Hence, $$\Phi(a)(x+\mathbb{Z}_{p})=J(ax)=\tilde{J}(\pi(ax))=\tilde{J}(\pi(a_{N(x)}x))=\tilde{J}(a_{N(x)}\pi(x))=\tilde{J}(\pi(x))^{a_{N(x)}}=J(x)^{a_{N(x)}}$$ Therefore, $$\Phi(a)(x+\mathbb{Z}_{p})=J(x)^{a_{N(x)}}=\exp(2\pi i a_{N(x)}m /p^{N(x)})=\phi_{N(x)}(m)=\gamma(\tilde{J}^{-1}(\exp 2\pi i m / p^{N(x)}))=\gamma(x+\mathbb{Z}_{p})$$

This proves that $\widehat{\mathbb{Q}_{p} / \mathbb{Z}_{p}}\cong \mathbb{Z}_{p}$. Now let's prove that $\Psi$ is a topological group isomorphism.

1. **$\Psi$ is a group homomorphism**:
We have that $\chi_{a}=\chi \circ L_{a}$ hence continuous and $\chi_{a}(s+t)=\chi(as+at)=\chi(as)\chi(at)=\chi_{a}(s)\chi_{a}(t)$. Thus, $\chi_{a}\in \widehat{\mathbb{Q}_{p}}$ for any $a\in\mathbb{Q}_{p}$. Further, $$\Psi(a+b)(t)=\chi_{a+b}(t)=\chi((a+b)t)=\chi(at)\chi(bt)=\Psi_{a}(t)\Psi_{b}(t)$$shows that $\Psi$ is a group homomorphism. 
2. **$\Psi$ is bijective**:
   Let $\chi_{a}\equiv 1$. Then, $\chi(at)=1$ for all $t\in\mathbb{Q}_{p}$, i.e. $at\in \mathbb{Z}_{p}$ for all $t\in \mathbb{Q}_{p}$. Therefore, $a=0$ and $\Psi$ is injective. 
   
   For surjectivity, let $\gamma\in \widehat{\mathbb{Q}_{p}}$. Let $V:=\varphi\left( \left( -\frac{\pi}{2}, \frac{\pi}{2} \right) \right)$ as in the previous exercise. Then, $\gamma ^{-1}(U)$ is an open neighborhood of $0$ and as $\{ p^n \mathbb{Z}_{p} :n\geq 0\}$ form the fundamental system of open neighborhoods of $0$ in $\mathbb{Q}_{p}$, there exists $n\geq 0$ s.t. $\gamma(p^n\mathbb{Z}_{p})\subseteq U$. As $p^n \mathbb{Z}_{p}\leq \mathbb{Q}_{p}$, similarly as above, $\gamma(p^n\mathbb{Z}_{p})=\{ 1 \}$. Therefore, $\tilde{\gamma}:\mathbb{Q}_{p}\to \mathbb{T},x\mapsto\gamma(p^nx)$ has $\mathbb{Z}_{p}\leq\text{ker }\tilde{\gamma}$ and can be factored into $\tilde{\gamma}=\varphi\circ\pi$ where $\pi:\mathbb{Q}_{p}\to \mathbb{Q}_{p} / \mathbb{Z}_{p}$ is the canonical projection and $\varphi\in \widehat{\mathbb{Q}_{p} / \mathbb{Z}_{p}}$. Let $b\in \mathbb{Z}_{p}$ s.t. $\Phi(b)=\varphi$ and $a:=p^{-n}b\in \mathbb{Q}_{p}$. Then, $$\Psi(a)(t)=\chi(at)=J(at)=J(bp^{-n}t)=\Phi(b)(\pi(p^{-n}t))=\varphi(\pi(p^{-n}t))=\tilde{\gamma}(p^{-n}t)=\gamma(t)$$ 
3. **$\Psi$ is a homeomorphism**:
   As $\mathbb{Q}_{p}$ and $\widehat{\mathbb{Q}_{p}}$ are both topological groups, we only need to show continuity of $\Psi$ only at $0$ and vice versa ($\Psi ^{-1}$ at $1$).
   
   For $\varepsilon>0$ and $k\in \mathbb{Z}$, let $N(k,\varepsilon):=\{ \chi\in \widehat{\mathbb{Q}_{p}}:\left| (x,\chi)-1 \right|<\varepsilon,x\in p^k\mathbb{Z}_{p} \}$. Then, the family$\{ N(k,\varepsilon): k\in \mathbb{Z},\varepsilon>0 \}$ forms a basis of neighborhoods of $\widehat{e}\in \widehat{\mathbb{Q}_{p}}$: Indeed, for any compact neighborhood $K$ of $0$ in $\mathbb{Q}_{p}$, there exists $k\in \mathbb{Z}$ s.t. $p^k \mathbb{Z}_{p}\subseteq K$. 
   
   Let $\varepsilon\leq1$. We have $\Psi(1)(p^k\mathbb{Z}_{p})=J(p^k\mathbb{Z}_{p})=\{ 1 \}$ if $k\geq 0$ and $\Psi(1)(p^k\mathbb{Z}_{p})=\{ \exp(2\pi i xp^k): x\in \mathbb{Z} \}$ if $k<0$. Therefore, $\Psi(1)(p^k\mathbb{Z}_{p})\subseteq B_{<\varepsilon}(1)$ if and only if $k\geq 0$. It follows that $\Psi(a)\in N(k,\varepsilon)$ if and only if $v_{p}(a)+k\geq 0$. We can conclude that $\Psi ^{-1}(N(k,\varepsilon))=p^{-k}\mathbb{Z}_{p}$. As $p^{-k}\mathbb{Z}_{p}$ also form a basis of open neighborhoods of $0$, $\Psi$ is a homeomorphism.
---
> [!def] Problem 6
> Let $K_{j}\leq G_{j}$ be a compact subgroup in a LCH group $G_{j}$ indexed by $j\in J$. Show that the restricted product $\prod_{j\in J}'^{}G_{j}$ is a locally compact Hausdorff space.

Let $(g_{j})_{j\in J}\in \prod_{j\in J}'^{}G_{j}$. Then, by definition $g_{j}\in K_{j}$ for all but finitely many. We define the compact neighborhood $\prod_{j\in J}^{}A_{j}$ where $A_{j}=K_{j}$ if $g_{j}\in K_{j}$ and if $g_{j}\notin K_{j}$, then $A_{j}$ is the compact neighborhood of $g_{j}$, which exists as $G_{j}$ is LCH. It follows that $\prod_{j\in J}^{}A_{j}$ is compact by Tychonoff and the restricted product is locally compact Hausdorff.

---
> [!def] Problem 7
> For the adeles $\mathbb{A}_{\mathbb{Q}}$, 
> 1. Prove that the multiplication map $\mathbb{A}_{\mathbb{Q}}\times \mathbb{A}_{\mathbb{Q}}\to \mathbb{A}_{\mathbb{Q}},(x,y)\mapsto xy$ is continuous.
> 2. Consider the diagonal map $\Delta:\mathbb{Q}\to \mathbb{A}_{\mathbb{Q}},x\mapsto(x,x)$. Prove that the image of $\Delta$ is a discrete, closed subgroup of $\mathbb{A}_{\mathbb{Q}}$.
> 3. Prove that the quotient $\mathbb{A}_{\mathbb{Q}} / \Delta(\mathbb{Q})$ is compact.

We have:
1. Firstly, notice that the multiplication is well-defined as multiplication is closed under $\mathbb{Z}_{p}$. Therefore, for $x,y\in \mathbb{A}_{\mathbb{Q}}$, $xy$ only has finitely many terms in $\mathbb{Q}_{p}$ and hence contained in the restricted product. 
   
   Now, as the topology on the restricted product is finer than the subset topology of the product, it suffices to show that multiplication is continuous on the product space $\mathbb{R}\times \prod_{p}^{}\mathbb{Q}_{p}$. This holds trivially as multiplication in $\mathbb{R}$ or each $\mathbb{Q}_{p}$ is continuous as a normed vector space. Hence, the restriction onto $\mathbb{A}_{\mathbb{Q}}\times \mathbb{A}_{\mathbb{Q}}$ is continuous.
2. Let $x\in \mathbb{Q}$. If $x\in \mathbb{Z}$, then $x\in \mathbb{Z}_{p}$ for all prime $p$. If $x\in \mathbb{Q} \backslash \mathbb{Z}$, let $x= m/n$ for $m,n\in \mathbb{Z}$ relatively prime and $J$ the set of primes that appear in the prime decomposition of $n$. Then, $J$ is finite. For any prime $p$ not in $J$, as it does not divide $n$, $n$ is invertible in $\mathbb{Z}_{p}$ and $x\in \mathbb{Z}_{p}$. For $p\in J$, $v_{p}(m)=0$ and $v_{p}(n)\geq 1$. Hence, $v_{p}(x)\leq 1$ and $x\in \mathbb{Q}_{p} \backslash \mathbb{Z}_{p}$. Therefore, the diagonal embedding $\mathbb{Q}\hookrightarrow \mathbb{A}_{\mathbb{Q}}$ is well-defined.  
   
   To show that $\Delta(\mathbb{Q})$ is discrete, we claim that $\{ (x,x) \}=\Delta(\mathbb{Q})\cap \left(  B_{<1/n}(x)\times\prod_{p\in J}^{}\mathbb{Q}_{p} \backslash \mathbb{Z}_{p}\times \prod_{p\notin J}^{}\mathbb{Z}_{p} \right)$which proves that $\{ (x,x) \}$ is open in $\Delta(\mathbb{Q})$. One inclusion is clear from above. Let $y\in\mathbb{Q}$ s.t. $(y,y)\in  B_{<1/n}(x)\times\prod_{p\in J}^{}\mathbb{Q}_{p} \backslash \mathbb{Z}_{p}\times \prod_{p\notin J}^{}\mathbb{Z}_{p}$. Then, from above, $y$ needs to have the same prime factorization of the denominator as $x$ and $y=m' / n$ for $m',n$ coprime. However, as $y\in B_{<1 / n}(x)$, $x=y$. 
   
   Notice that $\mathbb{R}\times \prod_{p}^{}\mathbb{Q}_{p}$ is Hausdorff as a product of Hausdorff spaces. Therefore, $\mathbb{A}_{\mathbb{Q}}$ is Hausdorff with the subspace topology and as the restricted product topology refines the subspace topology, $\mathbb{A}_{\mathbb{Q}}$ is Hausdorff. This proves that $\Delta(\mathbb{Q})$ is closed as a discrete subgroup of a Hausdorff space.
3. Let $\pi :\mathbb{A}_{\mathbb{Q}}\to \mathbb{A}_{\mathbb{Q}} / \Delta(\mathbb{Q})$ be the canonical projection. We will show that for: $$W:=B_{\leq 1}(0)\times \prod_{p}^{}\mathbb{Z}_{p}$$$\pi(W)=\mathbb{A}_{\mathbb{Q}} / \Delta(\mathbb{Q})$. Then, as $W$ is compact by Tychonoff, so is $\mathbb{A}_{\mathbb{Q}} / \Delta(\mathbb{Q})$ as a continuous image of a compact set. 
   
   Let $x\in \mathbb{A}_{\mathbb{Q}}$. We need to show that $x=a+\Delta(b)$ where $a\in W$ and $b\in \mathbb{Q}$. Let $x_{p}$ denote the element of $x$ in $\mathbb{Q}_{p}$. Similarly, $x_{\mathbb{R}}\in \mathbb{R}$. Further, let $J$ denote the finite set of primes $p$ for which $x_{p}\notin \mathbb{Z}_{p}$. For $p\in J$, $x_{p}=p^{-n_{p}}u_{p}$ where $n_{p}\in \mathbb{Z}$ and $u_{p}\in \mathbb{Z}_{p}$. We then decompose $u_{p}$ as $u_{p}=q_{p}\cdot p^{n_{p}}+r_{p}$ where $q_{p}\in \mathbb{Z}_{p}$ and $r_{p}\in \mathbb{Z}$ with $0\leq r_{p}<p^{n_{p}}$. Let us define: $$\beta:=\sum_{p\in J}^{} \frac{r_{p}}{p^{n_{p}}}\in \mathbb{Q}$$Then, for $p\notin J$, $v_{p}(x_{p}-\beta)\geq\min\{ v_{p}(x_{p}),v_{p}(\beta) \}\geq 0$ and $x_{p}-\beta\in \mathbb{Z}_{p}$. For $p\in J$, $$v_{p}(x_{p}-\beta)=v_{p}\left( q_{p}+\frac{r_{p}}{p^{n_{p}}}-\sum_{p'\in J}^{}\frac{r_{p'}}{p'^{n_{p'}}} \right)=v_{p}\left( q_{p}-\sum_{p'\in J\backslash\{ p \}}^{} \frac{r_{p'}}{p'^{n_{p'}}} \right)\geq 0  $$Let $n\in \mathbb{Z}$ s.t. $\left| x_{\mathbb{R}}-\beta-n \right|<1$. By defining $b:=\beta+n$, we have a rational number $\mathbb{Q}$ s.t. $x-\Delta(b)\in W$. This proves the statement.
---
> [!def] Problem 8
> Show that for every $x\in \mathbb{Q}_{p}$ there exist unique $a_{n}\in \{ 0,\dots,p-1 \}$ for $n\geq v_{p}(x)$ such that $$x=\sum_{n\geq v_{p}(x)}^{}a_{n}p^n$$
   
Let $x=0$. Then, $v_{p}(x)=\infty$ and the statement holds trivially. Consider $x\neq 0$, written as $x=p^{v_{p}(x)}u$ with $u\in \mathbb{Z}_{p}$. Then, we define $b_{0}:=u_{0}$ and $b_{n}:=((u_{n+1}-u_{n})/p^n) {\mod p}$ for $n\geq 1$. One sees that $b_{n}\in\mathbb{Z}$ as $u_{n+1}\equiv_{p^n}u_{n}$ and $0\leq b_{n}<p$. Let's show that $u=\sum_{n\geq 0}^{}b_{n}p^n$. For any $m\geq 1$, we have $$\left( \sum_{n\geq 0}b_{n}p^n \right)_{m}=\sum_{n=0}^{m-1}(b_{n})_{m-n}p^n=\sum_{n=0}^{m-1}b_{n}p^n=u_{0}+\sum_{n=1}^{m-1}(u_{n+1}-u_{n})=u_{m}$$By defining $a_{n}:=b_{n-v_{p}(x)}$we have: $$x=p^{v_{p}(x)}u=\sum_{n\geq 0}^{}b_{n}p^{n+v_{p}(x)}=\sum_{n\geq v_{p}(x)}^{}a_{n}p^n$$

---
> [!def] Problem 9
> Define the map $\chi:\mathbb{A}_{\mathbb{Q}}\to \mathbb{T}$ by: $$\chi(x_{\infty},x_{p}):=e^{2\pi i\{ x_{\infty} \}}\prod_{p}^{}e^{2\pi i\{ x_{p} \}}$$
> 1. Prove that $\chi$ is a continuous character on $\mathbb{A}_{\mathbb{Q}}$.
> 2. Define the character $\chi_{a}(x):=\chi(ax)$ for all $a,x\in \mathbb{A}_{\mathbb{Q}}$. Show that the map $$\mathbb{A}_{\mathbb{Q}}\to \widehat{\mathbb{A}_{\mathbb{Q}}},a\mapsto \chi_{a}$$ is an isomorphism of topological groups.

We have:
1. As the projections $\pi_{\infty}$ and $\pi_{p}$ are continuous from $\mathbb{R}\times \prod_{p}^{}\mathbb{Q}_{p}$ and the restricted product topology refines the subspace topology, the projections from $\mathbb{A}_{\mathbb{Q}}$ into the respective spaces are continuous. Further, as $\{ x_{p} \}=0$ for almost every $p$, the function is well-defined. Therefore, $\chi$ is a continuous character as it is a finite product of continuous characters.
2. As we have seen that $\chi_{a}\in \widehat{\mathbb{R}}$ and $\chi_{a}\in \widehat{\mathbb{Q}_{p}}$ for any prime $p$, from 1, $\chi_{a}:\mathbb{A}_{\mathbb{Q}}\to \mathbb{T}$ is a continuous character. For the same reason $\Psi:\mathbb{A}_{\mathbb{Q}}\to \widehat{\mathbb{A}_{\mathbb{Q}}},a\mapsto \chi_{a}$ defines an injective homomorphism.
   
   For the surjectivity, let $\gamma\in \widehat{\mathbb{A}_{\mathbb{Q}}}$. Then, as $\mathbb{A}_{\mathbb{Q}}=\mathbb{R}\times \prod_{p}'^{}\mathbb{Q}_{p}$, $\gamma$ is a product of $\gamma_{\infty}$ and $\tilde{\gamma}$ where $\gamma_{\infty}\in \widehat{\mathbb{R}}$ and $\tilde{\gamma}\in \widehat{\prod_{p}'\mathbb{Q}_{p}}$. As $\mathbb{R}\cong\widehat{\mathbb{R}}$, there exists $a_{\infty}\in \mathbb{R}$ s.t. $\gamma_{\infty}(x_{\infty})=\exp(2\pi ia_{\infty}x_{\infty})$. Further, considering the injection $i_{p}:\mathbb{Q}_{p}\to\prod_{p}'^{}\mathbb{Q}_{p}$ with $x_{p}\mapsto(0,0,\dots,x_{p},\dots)$, $\tilde{\gamma}\circ i_{p}\in \widehat{\mathbb{Q}_{p}}$. From above, there exists $a_{p}\in \mathbb{Q}_{p}$ s.t. $\tilde{\gamma}\circ i_{p}=\exp(2\pi i\{ a_{p}x_{p} \})$. 
   
   We claim that $(a_{\infty},a_{p})\in \mathbb{A}_{\mathbb{Q}}$. Let $U\subseteq  \mathbb{T}$ be the open neighborhood around $1$ s.t. for any subgroup $H\subseteq U$ of $\mathbb{T}$ has that $H=\{ 1 \}$. Then, as $\tilde{\gamma} ^{-1}(U)$ is open in $\mathbb{A}_{\mathbb{Q}}$, there exists $J$ finite s.t. $$\tilde{\gamma}\left( \prod_{p\in J}^{}V_{p}\times \prod_{p\notin J}^{}\mathbb{Z}_{p} \right)\subseteq U$$where $V_{p}$ are open in $\mathbb{Q}_{p}$. Therefore, $\tilde{\gamma}\left( \prod_{p\in J}^{}\{ 0 \}\times \prod_{p\notin J}^{}\mathbb{Z}_{p} \right)=\{ 1 \}$. Then, $a_{p}\in \mathbb{Z}_{p}$ for all $p\notin J$ as $\tilde{\gamma}(i_{p}(1))=\exp(2\pi i\{ a_{p} \})= 1$. 
   
   Let $(x_{\infty},x_{p})\in\mathbb{A}_{\mathbb{Q}}$ with $L$ as the set of primes $p$ for which $x_{p}\notin \mathbb{Z}_{p}$. Further, let $y\in \prod_{p}'^{}\mathbb{Q}_{p}$ where $y_{p}=0$ if $p\in J\cup L$ and $y_{p}=x_{p}$ otherwise. As $x_{p}\in \mathbb{Z}_{p}$ for all $p\notin L$, $\tilde{\gamma}(y)=1$. Then, $$\begin{align}\chi_{a}(x_{\infty},x_{p})=e^{2\pi ia_{\infty}x_{\infty}}\prod_{p\in J\cup L}^{}e^{2\pi i\{ a_{p}x_{p} \}}&=\gamma_{\infty}(x_{\infty})\tilde{\gamma}(y)\prod_{p\in J \cup L}^{}\tilde{\gamma}(i_{p}(x_{p}))\\&=\gamma_{\infty}(x_{\infty})\tilde{\gamma}\left( y+\sum_{p\in J\cup L}^{}i_{p}(x_{p}) \right)=\gamma(x_{\infty},x_{p})\end{align}$$ This shows the surjectivity.
   
   To show that $\Psi$ is a homeomorphism, we show that $\Psi$ and $\Psi ^{-1}$ are continuous at $0$ and $1$ respectively. Let $J$ be a finite set of primes and $$K:=B_{\leq \frac{1}{k_{\infty}}}(0)\times \prod_{p\in J}^{}p^{k_{p}}\mathbb{Z}_{p}\times \prod_{p\notin J}^{}\mathbb{Z}_{p}$$where $k_{\infty},k_{p}\geq 1$. Consider $N(K,\varepsilon):=\{ \chi_{a}\in \widehat{\mathbb{A}_{\mathbb{Q}}}:\left| (x,\chi _{a})-1 \right|<\varepsilon,\forall x\in K \}$. For $x\in K$, $$(x,\chi_{a})=\exp(2\pi i a_{\infty}x_{\infty})\prod_{p\in J}^{}\exp(2\pi i \{ a_{p}x_{p} \})$$As this is a finite product, we can instead consider $A:=\mathbb{R}\times \prod_{p\in J}^{}\mathbb{Q}_{p}$ with the product topology and with the surjection $\pi:\mathbb{A}_{\mathbb{Q}}\to A$, $\pi ^{-1}(K)$ is compact. From the previous results, we have that: $$\Psi_{A}:A\to \widehat{A},a\mapsto \chi_{a}$$ is a topological group isomorphism. Further, for $a:=(a_{\infty},a_{p})\in \mathbb{A}_{\mathbb{Q}}$, $a\in \Psi ^{-1}(N(K,\varepsilon))$ if and only if $\pi(a)\in \Psi_{A}^{-1}(N_{A}(\pi(K),\varepsilon))$. Consequently, $\Psi ^{-1}(N(K,\varepsilon))=\mathbb{A}_{\mathbb{Q}}\cap \left( \Psi_{A}^{-1}(N_{A}(\pi(K),\varepsilon))\times \prod_{p\notin J}^{}\mathbb{Q}_{p} \right)$ which is open. 
   
   Conversely, let 
   
---