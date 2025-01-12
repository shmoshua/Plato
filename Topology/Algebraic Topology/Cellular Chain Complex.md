#Definition #AlgebraicTopology 

> [!definition]
> Let $K$ be a [[CW-complex]]. The ***cellular chain complex*** of $K$ is a [[chain complex ]] $\mathcal{C}(K):=\{ C_{n}(K),d_{n} \}_{n\in \mathbb{Z}}$ where:
> 1. $C_{n}(K):=\bigoplus_{\sigma\in I_{n}}\mathbb{Z}\sigma\cong H_{n}(K^{(n)},K^{(n-1)})$ and
> 2. $d_{n}:C_{n}(K)\to C_{n-1}(K)$ where $d_{n}(\sigma):=\sum_{\tau\in I_{n-1}}^{}[\tau :\sigma]\tau$ for all $\sigma\in I_{n}$ and the ***incidence number*** $[\tau:\sigma]:=\deg(p_{\tau} \circ f_{\partial \sigma})$.
- **Related definition**: For a CW-complex $K$ and a subcomplex $A\subseteq K$, the ***relative cellular chain complex*** is defined as follows:
	1. $I^n_{K,A}:=\{ \sigma\in I^n_{K}:f_{\sigma}(B^n_{\sigma})\not\subseteq  A\}$
	2. $C_{n}(K,A):=\bigoplus_{\sigma\in I^n_{K,A}}\mathbb{Z}\sigma$
	3. $d_{n}:C_{n}(K,A)\to C_{n-1}(K,A)$ with $d_{n}(\sigma):=\sum_{\tau\in I^{n-1}_{K,A}}[\tau:\sigma]\tau$.
	4. $K^{(n)}_{A}:=K^{(n)}\cup A$.
---
##### Properties
> [!lemma] Proposition 1
> For a CW-complex $K$, 
> 1. $C_{n}(K)\cong H_{n}(K^{(n)},K^{(n-1)})$ is given by: $$\Psi:C_{n}(K)\to H_{n}(K^{(n)},K^{(n-1)}),\quad \sum_{\sigma\in I_{n}}^{}n_{\sigma}\cdot \sigma\mapsto \sum_{\sigma\in I_{n}}^{}n_{\sigma}\cdot (f_{\sigma})_{*}[I^n]$$and$$\Psi ^{-1}=\Phi:H_{n}(K^{(n)},K^{(n-1)})\to C_{n}(K),\quad \alpha\mapsto \sum_{\sigma\in I_{n}}^{}\phi_{n}((p_{\sigma})_{*}(\alpha))\cdot \sigma$$where:
> 	1. $\gamma_{n}:(I^n,\partial I^n)\to (S^n,*)$ s.t. $(\gamma_{n})_{*}:H_{n}(I^n,\partial I^n)\to H_{n}(S^n,*)$ is an isomorphism.
> 	2. $[I^n]\in H_{n}(I^n,\partial I^n)$, $[S^n]\in H_{n}(S^n,*),[\partial I^{n+1}]\in \tilde{H}_{n}(\partial I^{n+1})$ are generators with $(\gamma_{n})_{*}([I^n])=[S^n]$ and $\partial_{*}([I^{n+1}])=[\partial I^{n+1}]$. 
> 	3. $\phi_{n}:H_{n}(S^n,*)\to \mathbb{Z}$ is the unique isomorphism s.t. $\phi_{n}([S^n])=1$.
> 	4. $p_{\sigma}:(K^{(n)},K^{(n-1)})\to (S^n,*)$ s.t. $\gamma_{n}=p_{\sigma} \circ f_{\sigma}$.
> 2. $d_{n}=\Phi_{n-1} \circ \beta_{n}\circ\Psi_{n}$ for all $n$.
> 3. $\mathcal{C}(K)$ is a chain complex. 
> 4. $H_{n}(\mathcal{C}(K))\cong H_{n}(K)$ for all $n\in \mathbb{Z}$.

> [!proof]-
> We have:
> 1. We first notice that $\Psi$ is an isomorphism as it sends every generator to a generator. Hence, it suffices to show that $\Phi \circ\Psi=\text{id}$. By linearity, we can show that $\Phi(\Psi(\sigma))=\sigma$ for all $\sigma\in I_n$. We have: $$\begin{align}\Phi(\Psi(\sigma))=\Phi((f_{\sigma})_{*}[I^n])=\sum_{\tau\in I_{n}}^{}\phi_{n}((p_{\tau})_{*}(f_{\sigma})_{*}[I^n])\tau=\phi_{n}((p_{\sigma}\circ f_{\sigma})_{*}[I^n])\sigma=\phi_{n}([S^n])\sigma=\sigma\end{align}$$where for $\tau\neq\sigma$, $p_{\tau} \circ f_{\sigma}=*$ and $(p_{\tau}\circ f_{\sigma})_{*}=0$.
> 2. We have that for $\sigma\in I_{n}$: $$\begin{align}\Phi \circ \beta_{n}\circ \Psi(\sigma)&=\Phi \circ j_{n-1}\circ \partial_{n} \circ (f_{\sigma})_{*}[I^n]=\Phi \circ j_{n-1}\circ (f_{\partial\sigma})_{*}[\partial I^n]\\&=\sum_{\tau\in I_{n-1}}^{}\phi_{n-1}((p_{\sigma})_{*}\circ j_{n-1}\circ (f_{\partial\sigma})_{*}[\partial I^n])\tau\\&=\sum_{\tau\in I_{n-1}}^{}\phi_{n-1}((p_{\sigma}\circ f_{\partial\sigma})_{*}[\partial I^n])\tau\end{align}$$We conclude by noting that $\phi_{n-1}((p_{\sigma}\circ f_{\partial\sigma})_{*}[\partial I^n])=\deg(p_{\tau} \circ f_{\partial\sigma})$ by definition. 
> 3. Holds from the fact that $\beta_{n}\circ\beta_{n+1}=0$ from [[CW-Complex|Proposition 8]] and $\Psi \circ\Phi=\text{id}$.
> 4. We have that: $$H_{n}(\mathcal{C}(K))=\text{ker}(d_{n}) / \text{im}(d_{n+1})\cong \text{ker}(\beta_{n}) / \text{im}(\beta_{n+1})\cong H_{n}(K^{(n+1)})\cong H_{n}(K)$$
---
> [!lemma] Proposition 2
> Let $g:K\to L$ be a [[CW-Complex|cellular map]] between CW-complexes. Then, 
> 1. $g_{\text{cw}}:=\Phi^L \circ g_{*} \circ\Psi^K:C_{n}(K)\to C_{n}(L)$ is a [[Chain Complex|chain map]].
> 2. Let $g^H_{\text{cw}}:H_{p}(\mathcal{C}(K))\to H_{p}(\mathcal{C}(L))$. Then, $$\begin{CD}H_{p}(K)@>g_{*}>>H_{p}(L)\\@V\Theta^K VV@V\Theta^L VV\\H_{p}(\mathcal{C}(K))@>>g^H_{\text{cw}}>H_{p}(\mathcal{C}(L))\end{CD}$$commutes, where $\Theta^K:H_{p}(K)\to H_{p}(\mathcal{C}(K))$ and $\Theta^K:H_{p}(L)\to H_{p}(\mathcal{C}(L))$ are isomorphisms (from Proposition 1.4).
> 3. $g_{\text{cw}}(\sigma)=\sum_{\tau\in I^L_{n}}^{}\deg(g_{\sigma,\tau})\tau$ for all $\sigma\in I^K_{n}$ where $g_{\sigma,\tau}:S^n_{\sigma}\to S^n_{\tau}$ given by $g_{\sigma,\tau}:=\overline{p_{\tau}}\circ \overline{g}\circ \overline{f_{\sigma}}$ from the following diagram:$$\begin{CD}B^n_{\sigma}@>f_{\sigma}>> K^{(n)}@>g>>L^{(n)}@>p_{\tau}>> S^n_{\tau}\\@V\gamma_{n} VV@VVV@VVV@VV\text{id}V\\S^n_{\sigma}@>>\overline{f_{\sigma}}>K^{(n)} / K^{(n-1)}@>>\overline{g}>L^{(n)} / L^{(n-1)}@>>\overline{p_{\tau}}>S^n_{\tau}\end{CD}$$where the lower row is induced by the upper row by collapsing the boundary to a point.

> [!proof]-
> We have that:
> 
> 1. To show that $g_{\text{cw}}$ is a chain map, let $\alpha\in C_{n}(K)$. Then, $$d_{n}^L\circ g_{\text{cw}}=\Phi_{n-1}^L \circ  \beta_{n}^L \circ  \Psi^L_{n}\circ \Phi^L_{n}\circ  g_{*}\circ \Psi^K_{n}=\Phi_{n-1}^L \circ  \beta_{n}^L \circ  g_{*}\circ \Psi^K_{n}$$and $$g_{\text{cw}}\circ d_{n}^K=\Phi^L_{n-1}\circ g_{*}\circ \Psi^K_{n-1}\circ \Phi^K_{n-1}\circ \beta^K_{n}\circ \Psi^K_{n}=\Phi^L_{n-1}\circ g_{*}\circ  \beta^K_{n}\circ \Psi^K_{n}$$Hence, it suffices to show that $g_{*}\circ  \beta^K_{n}=\beta_{n}^L \circ  g_{*}$. This holds by noting that: $$\begin{CD}H_{n}(K^{(n)},K^{(n-1)})@>\partial_{n}>>H_{n-1}(K^{(n-1)})@>j_{n-1}>>H_{n-1}(K^{(n-1)},K^{(n-2)})\\@Vg_{*}VV@Vg_{*}VV@Vg_{*}VV\\H_{n}(L^{(n)},L^{(n-1)})@>\partial_{n}>>H_{n-1}(L^{(n-1)})@>j_{n-1}>>H_{n-1}(L^{(n-1)},L^{(n-2)})\end{CD}$$commute where the first square by naturality of $\partial_{*}$ and the second as $g\circ j=j\circ g$. This concludes the proof.
> 2. We have that:
>    $$\begin{CD}H_{p}(K)@>g_{*}>>H_{p}(L)\\@V\cong VV@V\cong VV\\ \text{ker }\beta_{p}^K / \text{im }\beta_{p+1}^K@>g_{*}>>\text{ker }\beta_{p}^L / \text{im }\beta_{p+1}^L\\@V\cong VV@V\cong VV\\H_{p}(\mathcal{C}(K))@>>g^H_{\text{cw}}>H_{p}(\mathcal{C}(L))\end{CD}$$
> 3. We have that: $$\begin{align}g_{\text{cw}}(\sigma)&=\Phi^L\circ g_{*}\circ \Psi^K(\sigma)\\&=\Phi^L\circ g_{*}\circ (f_{\sigma})_{*}[I^n]\\&=\sum_{\tau\in I^L_{n}}\phi_{n}((p_{\tau}\circ  g \circ  f_{\sigma})_{*}[I^n])\tau\\&=\sum_{\tau\in I^L_{n}}\phi_{n}((g_{\sigma,\tau}\circ \gamma_{n})_{*}[I^n])\tau\\&=\sum_{\tau\in I^L_{n}}\phi_{n}((g_{\sigma,\tau})_{*}[S^n])\tau\\&=\sum_{\tau \in I^L_{n}}^{}\deg(g_{\sigma,\tau})\tau\end{align}$$
---
> [!lemma] Theorem 3 (Cellular Approximation)
> Let $K,Y$ be CW-complexes and $N\subseteq K$ a subcomplex. 
> 1. If $\phi:K\to Y$ is a continuous map s.t. $\phi|_{N}$ is cellular, then $\phi \sim \psi$ relative to $N$ where $\psi:K\to Y$ is a cellular map.
---
> [!lemma] Theorem 4 (Relative Chain Complex)
> Let $K$ be a CW-complex and $A\subseteq K$ its subcomplex. Then, 
> 1. $C_{n}(K,A)\cong H_{n}(K^{(n)}_{A},K^{(n-1)}_{A})$
> 2. $K^{(n)}_{A} / K^{(n-1)}_{A}\cong \bigvee_{\sigma\in I^n_{K,A}}S^n_{\sigma}$
> 3. $H_{p}(K^{(n)}_{A},A)=0$ for all $p>n$.
> 4. For another CW-complex $L$ and $B\subseteq L$ subcomplex, for a cellular map $g:(K,A)\to(L,B)$, i.e. $g$ and $g|_{A}:A\to B$ are cellular, $g_{\text{cw}}:C_{n}(K,A)\to C_{n}(L,B)$.
 
> [!proof]-
> We have that:
> 1. Analogous to the non-relative case.
> 2. By induction over $n$. 
> 	1. If $n=0$, then for all $p>0$, $K^{(0)}_{A}$ is given by $A$ with discrete points. Hence, $H_{p}(K^{(0)}_{A},A)\cong H_{p}(K^{(0)} \backslash A,\varnothing)=H_{p}(K^{(0)} \backslash A)=0$.
> 	2. If $n\geq 1$, for $p>n$, 
---
##### Examples
> [!h] Example 1 (RP2)
> We have that: 
> 1. $H_{0}(\mathbb{R}\mathbb{P}^2)\cong \mathbb{Z}$
> 2. $H_{1}(\mathbb{R}\mathbb{P}^{2})\cong \mathbb{Z} / 2\mathbb{Z}$
> 3. $H_{n}(\mathbb{R}\mathbb{P}^2)=0$ for all $n\geq 0$
> 4.  If $n$ is even:
>    $$H_{p}(\mathbb{R}\mathbb{P}^n)\cong \begin{cases}\mathbb{Z}&p=0\\\mathbb{Z} / 2\mathbb{Z}& 0< p<n, p\text{ even}\\0&\text{ otherwise}\end{cases}$$
>    If $n$ is odd,
> 	$$H_{p}(\mathbb{R}\mathbb{P}^n)\cong \begin{cases}\mathbb{Z}&p=0,n\\\mathbb{Z} / 2\mathbb{Z}& 0< p<n, p\text{ even}\\0&\text{ otherwise}\end{cases}$$

> [!proof]-
> We can represent $\mathbb{R}\mathbb{P}^{2}$ as a CW complex with 3 cells. Namely, 
> 1. one $0$-cell $\sigma_{0}$,
> 2. one $1$-cell $\sigma_{1}$, a loop at $\sigma_{0}$,
> 3. one $2$-cell $\sigma_{2}$ where the nodes are mapped to $\sigma_{0}$ and the edges are mapped to $\sigma_{1}$. 
>    .
> 	```tikz
> 	\usepackage{tikz}
> 	\usetikzlibrary{calc, arrows, decorations.markings}
> 	\begin{document}
> 	\begin{tikzpicture}[scale=1.5, line width=1pt,
> 	double_arrow/.style={postaction={decorate}, decoration={markings, mark=at position 0.53 with {\arrow{>>}}}}, 
> 	single_arrow/.style={postaction={decorate}, decoration={markings, mark=at position 0.53 with {\arrow{>}}}}]
> 	\tikzset{dot/.style = {shape=circle, fill,draw, inner sep=0pt, minimum size=5pt}}
> 	\draw[single_arrow] (0,0) -- (2,0);
> 	\draw[double_arrow] (2,0) -- (2,-2);
> 	\draw[single_arrow] (2,-2) -- (0,-2);
> 	\draw[double_arrow] (0,-2) -- (0,0);
> 	\node[dot] (da) at (0,-2) {};
> 	\node[dot] (da) at (2,0) {};
> 	\end{tikzpicture}
> 	\end{document}
> 	 ```
>
>Then, we have that $0\to C_{2}(K)\to C_{1}(K)\to C_{0}(K)\to 0$ where:
>1. $d\sigma_{0}=0$,
>2. $d\sigma_{1}=0$ as $[\sigma_{0}:\sigma_{1}]=0$ as $p_{\sigma_{0}}\circ f_{\partial\sigma_{1}}$ is a constant map.
>3. $d\sigma_{2}=\pm 2\sigma_{1}$ and we have that $p_{\sigma_{1}}\circ f_{\partial\sigma_{2}}:S^1\to S^1, z\mapsto z^2$ or $p_{\sigma_{1}}\circ f_{\partial\sigma_{2}}:S^1\to S^1, z\mapsto z^{-2}$, depending on which direction we wrap the boundary to the 1-cell. Hence, $$[\sigma_{1}:\sigma_{2}]=\deg(p_{\sigma_{1}}\circ f_{\partial\sigma_{2}})=\pm2$$. 
>   
>    This proves the statement.
> 4. [[Real Projective Space]]
---

> [!h] Example 2 (CPn)
> We have that:
> 1. $H_{p}(\mathbb{C}\mathbb{P}^n)\cong \begin{cases}\mathbb{Z}&0\leq p\leq 2n, p\text{ even}\\0&\text{otherwise}\end{cases}$

> [!proof]-
> We have that:
> 1. From [[CW-Complex|Example 1]], there is one cell in each odd dimension up to $2n$ and no odd cells. Hence, $$0\to C_{2n}(K)\to 0 \to C_{2n-2}(K) \to 0 \to \dots$$In any case $d=0$ for all $p\in \mathbb{Z}$ and the statement follows.
---
> [!h] Example 3 (Torus)
> We have that: 
> 1. $H_{p}(\mathbb{T}^2)\cong \begin{cases}\mathbb{Z}&p=0,2\\\mathbb{Z}^2&p=1\\0&\text{ otherwise}\end{cases}$
> 2.  $H_{p}(\mathbb{T}^3)\cong \begin{cases}\mathbb{Z}&p=0,3\\\mathbb{Z}^3&p=1,2\\0&\text{ otherwise}\end{cases}$

> [!proof]-
> We have that:
> 1. $\mathbb{T}^2$ has the following CW-structure. 
> 	1. one $0$-cell $x$.
> 	2. two $1$-cells $a,b$. 
> 	3. one $2$-cell $\sigma$, where the attaching map is given as $aba^{-1}b^{-1}$. 
> 	
> 	Then, we have that $d(a)=d(b)=0$ and $p_{a}\circ f_{\partial \sigma}$ is given by $a*\varepsilon_{x} * a^{-1} * x\cong x$. Therefore, $\deg(p_{a}\circ f_{\partial \sigma})=\deg(\varepsilon_{x})=0$. Hence, it follows that: $$0\to \mathbb{Z}\xrightarrow{0}\mathbb{Z}^{2} \xrightarrow{0} \mathbb{Z} \to 0$$and we have the statement.
> 2. $\mathbb{T}^3$ is also given by the following CW-structure: 
> 	1. one $0$-cell $a$,
> 	2. three $1$-cells $b_{1},b_{2},b_{3}$,
> 	3. three $2$-cells $c_{1},c_{2},c_{3}$,
> 	4. one $3$-cell $d$. 
> 	
> 	Then, similarly, we have that $d(b_{1})=d(b_{2})=d(b_{3})=0$ and $d(c_{1})=d(c_{2})=d(c_{3})=0$ by 1. Lastly, for the same reason we have that $[c_{i}:d] = 0$. Hence, we have: $$0\to \mathbb{Z}\xrightarrow{0} \mathbb{Z}^3\xrightarrow{0} \mathbb{Z}^3\xrightarrow{0}  mathbb{Z}\to 0$$
---
> [!h] Example 4
> Let $X$ be the union of $S^2 \subseteq \mathbb{R}^3$ and the line segment between north and south poles. Then, 
> 1. $H_{p}(X)\cong \begin{cases}\mathbb{Z}&p=0,1,2\\0& \text{otherwise}\end{cases}$

> [!proof]-
> As a CW-complex, we have:
> 1. two $0$-cells $a_{1},a_{2}$.
> 2. three $1$-cells $b_{1},b_{2},b_{3}$ all from $a_{1}$ to $a_{2}$,
> 3. two $2$-cells $c_{1},c_{2}$ where $f_{\partial c_{1}}=b_{1}b_{2}^{-1}$ and $f_{\partial c_{2}}=b_{2}b_{1}^{-1}$.
> 
> Then, we have that $0\to \mathbb{Z}^2\to \mathbb{Z}^3\to \mathbb{Z}^2 \to 0$ where: 
> 1. $d(b_{i})=(a_{1},a_{2})$
> 2. $[b_{1}:c_{1}]=1$, $[b_{2}:c_{1}]=1$, $[b_{3}:c_{1}]= 0$. Hence, $$d(c_{1})=(1,1,0)$$and we have that: $$\begin{array}{ccccc}0&\to &\mathbb{Z}^{2}&\to& \mathbb{Z}^3 &\to &\mathbb{Z}^2 &\to &0\\&&(x,y)&\mapsto &(x+y,x+y,0)\\&&&&(x,y,z)&\mapsto&(x+y+z,x+y+z)\end{array}$$
> 
> Similarly, we also see that $X=S^2 \lor S^1$ and therefore, $$\tilde{H}_{p}(X)\cong \tilde{H}_{p}(S^2 \lor S^1)\cong \tilde{H}_{p}(S^2)\oplus \tilde{H}_{p}(S^1)$$and we have that: $$\tilde{H}_{p}(X)\cong \begin{cases}0&p=0\\\mathbb{Z}&p=1,2\end{cases}$$This shows the above statement.