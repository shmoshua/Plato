#Definition #AlgebraicTopology 

> [!definition]
> A ***homology theory*** $H$ is a functor that assigns:
> 1. to every pair of a [[topological space]] $X$ and its subspace $A\subseteq X$ and $p\in \mathbb{Z}$, a graded abelian group $H_{p}(X,A)$ and a homomorphism $\partial_{*}: H_{p}(X,A)\to H_{p-1}(A,\varnothing)$ and:
> 2. to every continuous map $f:(X,A)\to(Y,B)$ and $p\in \mathbb{Z}$ a homomorphism $f_{*}:H_{p}(X,A)\to H_{p}(Y,B)$ s.t. we have that:
> 	1. $(g\circ f)_{*}=g_{*}\circ f_{*}$ for all continuous $f:(X,A)\to(Y,B)$ and $g:(Y,B)\to(Z,C)$,
> 	2. $(\text{id}_{(X,A)})_{*}=\text{id}_{H_{p}(X,A)}$
> 	3. the following diagram commutes: $$\begin{CD}H_{p}(X,A)@>\partial_{*}>>H_{p-1}(A,\varnothing)\\@Vf_{*}VV@V(f|_{A})_{*}VV\\H_{p}(Y,B)@>\partial_{*}>>H_{p-1}(B,\varnothing)\end{CD}$$
> 
> s.t. the following axioms hold:
> 1. **(Homotopy invariance)**: if $f,g:(X,A)\to(Y,B)$ are [[Homotopy|homotopic]], then $f_{*}=g_{*}$.
> 2. **(Exactness)**: the following sequence is [[Exact Sequence|exact]]:$$\cdots \to H_{p}(A,\varnothing)\xrightarrow{i_{*}}H_{p}(X,\varnothing)\xrightarrow{j_{*}}H_{p}(X,A)\xrightarrow{\partial_{*}}H_{p-1}(A,\varnothing)\to\cdots$$where $i:(A,\varnothing)\to(X,\varnothing)$ and $j:(X,\varnothing)\to(X,A)$ are standard inclusions.
> 3. **(Excision)**: For $(X,A)$ and an open set $U\subseteq X$ with $\overline{U}\subseteq A^\circ$, $$k_{*}:H_{p}(X\backslash U,A\backslash U)\to H_{p}(X , A),\quad \forall p\in \mathbb{Z}$$is an isomorphism where $k:(X \backslash U,A\backslash U)\to(X,A)$ is the standard inclusion.
> 4. **(Dimensions)**: For all $p\neq 0$ and a point space $X$, $H_{p}(X, \varnothing)=0$.
> 5. **(Additivity)**: For $X=\bigsqcup_{\alpha\in I}^{}X_{\alpha}$ and the inclusion $i_{\alpha}: X_{\alpha}\to X$, it holds that: $$\oplus(i_{\alpha})_{*}:\bigoplus _{\alpha\in I} H_{p}(X_{\alpha},\varnothing)\to H_{p}(X),\quad (c_{\alpha})_{\alpha\in I}\mapsto \sum_{\alpha\in I}^{}(i_{\alpha})_{*}(c_{\alpha}) $$is an isomorphism for all $p\in \mathbb{Z}$.

^da2d12

- **Related definition**: $H_{p}(X):=H_{p}(X , \varnothing)$ for all topological space $X$. ^3d68da
- **Related definition**: $G:=H_{0}(X)$ where $X$ is a point space is known as the ***coefficients group*** of $H$. ^cd0ebd
- **Related definition**: The ***reduced homology*** $\tilde{H}$ is defined as:
	1.  For $X\neq \varnothing$ and $p\in \mathbb{Z}$, $\tilde{H}_{p}(X):=\text{ker }\varepsilon_{*}$ where $P$ is a point space and $\varepsilon:X\to P$ is the constant map.
	2. For a pair $(X,A)$, $\tilde{H}_{p}(X,A):=H_{p}(X,A)$ for all $p\in \mathbb{Z}$.
	3. For $X=\varnothing$, $\tilde{H}_{p}(\varnothing)=\begin{cases}G&p=-1\\0&p\neq-1\end{cases}$
- **Remark**: $\tilde{H}_{p}(X,\varnothing)\neq \tilde{H}_{p}(X)$ in general and $\tilde{H}_{p}(\varnothing,\varnothing)=H_{p}(\varnothing,\varnothing)=H_{p}(\varnothing)=0$ (cf. Lemma 1)
---
##### Properties
> [!lemma] Lemma 1
> Let $H$ be a homology theory. Then,
> 1. $H_{p}(\varnothing)=0$ for all $p\in \mathbb{Z}$.
> 3. $H_{p}(X,X)=0$ for all $p\in \mathbb{Z}$
> 4. For a [[Homotopy|homotopy equivalence]] $f:(X,A)\to(Y,B)$, $f_{*}$ is an isomorphism.

^d375b2

> [!proof]-
> We have that:
> 1. Let $Y=\varnothing$. Then, $H_{p}(X)\oplus H_{p}(\varnothing) \cong H_{p}(X)$. Hence, $H_{p}(\varnothing)=0$.
> 2. We have an exact sequence: $$\cdots \to H_{p+1}(X,\varnothing)\xrightarrow{\partial_{*}} H_{p}(X,\varnothing)\xrightarrow{\text{id}} H_{p}(X,\varnothing)\xrightarrow{j_{*}} H_{p}(X,X)\to H_{p-1}(X,\varnothing)\to\cdots$$Hence, $H_{p}(X,\varnothing)=\text{ker }j_{*}$ and $j_{*} = 0$. However, we also have that: $\text{im}(\partial_{*})=\text{ker }\text{id} = 0$. Hence, $\partial_{*}=0$. Now, we have that $$H_{p}(X,X)=\text{ker }\partial_{*} =\text{im }j_{*}=0$$
> 3. Let $g:(Y,B)\to(X,A)$ be the homology inverse of $f$. Then, $$g_{*} \circ  f_{*} = (g\circ f)_{*}=\text{id}_{*}=\text{id}_{H_{p}(X,A)}$$$$f_{*} \circ  g_{*} = (f\circ g)_{*}=\text{id}_{*}=\text{id}_{H_{p}(Y,B)}$$

^525ab9

---
> [!lemma] Theorem 2 (Reduced Homology)
> Let $\tilde{H}_{p}(X)$ be the reduced homology given by $\text{ker }\varepsilon_{*}$ where $\varepsilon:X\to P$ for the point space $P$. Then,
> 1. $H_{p}(X)=\tilde{H}_{p}(X)$ for $p\neq 0$.
> 2. $H_{0}(X)\cong \tilde{H}_{0}(X)\oplus G$
> 3. for $f:X\to Y$, $f_{*}(\tilde{H}_{0}(X))\subseteq \tilde{H}_{0}(Y)$.
> 4. there exists $\tilde{i}_{*},\tilde{j_{*}}$ s.t. the following sequence is exact: $$\cdots \to \tilde{H}_{p}(A)\xrightarrow{\tilde{i}_{*}}\tilde{H}_{p}(X)\xrightarrow{\tilde{j}_{*}}\tilde{H}_{p}(X,A)\xrightarrow{\tilde{\partial}_{*}} \tilde{H}_{p-1}(A)\to\cdots$$

> [!proof]- Proof (Incomplete)
> We have that:
> 1. Follows from the fact that $\varepsilon_{*}$ is the zero map for $p\neq 0$. 
> 2. Let $i:P\to X$. Then, $\varepsilon \circ i=\text{id}_{P}$ and $\varepsilon_{*}\circ i_{*} = \text{id}_{H_{p}(P)}$. This shows that $\varepsilon_{*}$ is surjective and: $$0\to \tilde{H}_{p}(X)\to H_{p}(X)\xrightarrow{\varepsilon_{*}}H_{p}(P)\to 0$$defines a SES. As $i_{*}$ is the right inverse of $\varepsilon_{*}$, by [[Split Exact Sequence|Proposition 1]], the SES is split. Therefore, $$H_{p}(X)\cong \tilde{H}_{p}(X)\oplus H_{p}(P)$$and we have our statement when $p=0$.
> 3. We have that for $x\in \tilde{H}_{0}(X)$, $\varepsilon_{*}(f_{*}(x))=\varepsilon_{*}(x)=0$
> 4. We first show it for $A\neq \varnothing$. As we only need to check the parts of the sequence with $\tilde{H}\neq H$, we have that we need to show: $$H_{1}(X,A)\xrightarrow{\partial_{*}}\tilde{H}_{0}(A)\xrightarrow{\tilde{i}_{*}}\tilde{H}_{0}(X)\xrightarrow{\tilde{j}_{*}}{H}_{0}(X,A)\xrightarrow{\partial_{*}} {H}_{-1}(A)$$is exact.
>    
>    We first show that these maps are well-defined: Let $P$ be a point space and consider $\varepsilon:(X,A)\to(P,P)$. Now, we have that: $$\begin{CD}
>    H_{1}(X,A)@>\partial_{*}>> H_{0}(A)@>i_{*}>> H_{0}(X)@>j_{*}>>H_{0}(X,A)\\@V\varepsilon_{*}VV@V\varepsilon_{*}VV@V\varepsilon_{*}VV@V\varepsilon_{*}VV\\H_{1}(P,P)=0@>>>H_{0}(P)@>>\text{id}>H_{0}(P)@>>>H_{0}(P,P)=0\end{CD}$$
>    
>    1. **Claim 1**: $\partial_{*}(H_{1}(X,A))\subseteq \tilde{H}_{0}(A)$.
>       From the first square, we get that $\varepsilon_{*} \circ \partial_{*} = 0$. Hence, $$\partial_{*}(H_{1}(X,A))\subseteq \text{ker }\varepsilon_{*}=\tilde{H}_{0}(A)$$
>    2. **Claim 2**: $i_{*}(\tilde{H}_{0}(A))\subseteq \tilde{H}_{0}(X)$
>       From the second square, we get that for all $a\in \tilde{H}_{0}(A)$ if $\varepsilon_{*}(a)=0$, then $\varepsilon_{*}(i_{*}(a))=0$ and $i_{*}(a)\in \text{ker }\varepsilon_{*}=\tilde{H}_{0}(X)$.
>    
>    Therefore, we can set $\tilde{i}_{*}:=i_{*}|_{\tilde{H}_{0}(A)}$ and $\tilde{j}_{*}:= j_{*}|_{\tilde{H}_{0}(X)}$. Now we show that our sequence is exact:
>    1. **Exactness at $\tilde{H}_{0}(A)$**
>       We first have that $\tilde{i}_{*}\circ\partial_{*}=0$ as $i_{*} \circ \partial_{*}=0$. Hence, $\text{im}(\partial_{*})\subseteq \text{ker }\tilde{i}_{*}$.
>       
>       Conversely, for $a\in \text{ker }\tilde{i}_{*}$. Then, $i_{*}(a)=\tilde{i}_{*}(a)=0$ and $a\in \text{ker }i_{*}=\text{im }\partial_{*}$. Hence, $\text{ker }\tilde{i}_{*}\subseteq \text{im }\partial_{*}$
> 	  1. **Exactness at $\tilde{H}_{0}(X)$**
> 	     As $j_{*} \circ i_{*} = 0$, we have that $\tilde{j}_{*} \circ \tilde{i}_{*}=0$. Conversely, consider the following diagram:
> 	     .
> 	     ``````tikz
> 	     \usepackage{tikz-cd}\begin{document}\begin{tikzcd} 
> 	     0 & {\tilde{H}_0(A)} & {H_0(A)} & {H_0(P)} & 0 \\ 0 & {\tilde{H}_0(X)} & {H_0(X)} & {H_0(P)} & 0 \\ && {H_0(X,A)} 
> 	     \arrow[from=1-1, to=1-2] \arrow[hook, from=1-2, to=1-3] \arrow[from=1-4, to=1-5] \arrow[dashed, no head, from=1-4, to=2-4] \arrow[from=2-1, to=2-2] \arrow[hook, from=2-2, to=2-3] \arrow["{j_*}"', from=2-3, to=3-3] \arrow[from=2-4, to=2-5] \arrow["{\tilde{i}_*}"', from=1-2, to=2-2] \arrow["{\varepsilon_*}", from=1-3, to=1-4] \arrow["{\tilde{i}_*}"', from=1-3, to=2-3] \arrow["{\tilde{j}_*}"', from=2-2, to=3-3] \arrow["{\varepsilon_*}", from=2-3, to=2-4] \arrow["{\textrm{id}}"', from=1-4, to=2-4] \end{tikzcd}
> 	     \end{document} 
> 	     ```
> 	    
> 	    
> 	   Then the two rows are exact and the diagram commutes. Hence, for $x\in \text{ker }\tilde{j}_{*}$, we have that $j_{*}(x)=0$ for $x\in H_{0}(X)$. Hence, there exists $a\in A$ with $i_{*}(a)=x$. Now, $\varepsilon_{*}(a)=\varepsilon_{*}(\tilde{i}_{*}(a))=\varepsilon_{*}(x)=0$ as $x\in \tilde{H}_{0}(X)$. 
> 	   
> 	   Therefore, $a\in \tilde{H}_{0}(A)$ and $x\in \text{im }\tilde{i}_{*}$.
> 	  
> 	  3. **Exactness at $H_{0}(X,A)$.** 
> 	     $\text{im }\tilde{j}_{*}\subseteq \text{ker }\partial_{*}$ by definition. Then, for $x\in \text{ker }\partial_{*}$, we have that 


---
> [!lemma] Theorem 3
> The singular homology is a homology theory with coefficients group $\mathbb{Z}$.


---
##### Examples
> [!h] Example 1
> Let 
> 1. $B^n:=B_{\leq 1}(0)\subseteq \mathbb{R}^n$ for $n\geq 1$ and $B_{0}:=\{ 0 \}$. 
> 2. $S^n:=\partial B^{n+1}$.
> 3. $B^n_{+}:=\{ (x_{1},\dots,x_{n+1})\in S^n:x_{n+1}\geq 0 \}\subseteq S^n$ for all $n\geq 0$.
>    
> Then, we have that:
> 1. $\tilde{H}_{p}(S^n)\cong \begin{cases}G&p=n\\0&p\neq n\end{cases}$
> 2. $H_{p}(B^n,S^{n-1})\cong \begin{cases} G&p=n\\0&p\neq n\end{cases}$
> 3. $H_{p}(S^n,B^n_{+})=\begin{cases}G&p=n\\0&p\neq n\end{cases}$

> [!proof]-
> We first define $\pi:S^n\to \mathbb{R}^n,(x_{1},\dots,x_{n+1})\mapsto (x_{1},\dots,x_{n})$. Then, $\pi(S^n)=B^n$ and $\pi(N)=\pi(S)=0$ where $N:=(0,\dots,0,+1)\in S^n$ and $S:=(0,\dots,0,-1)\in S^n$.
> 
> Further, $\phi:B^n\to B^n_{+}$ can be defined as $$\phi(x_{1},\dots,x_{n})=\left( x_{1},\dots,x_{n},\sqrt{ 1-\sum_{i=1}^{n}x_{i}^{2} } \right)$$which is continuous inverse for $\pi|_{B^n_{+}}$. Hence, as $B^n_{+}$ is compact and $B^n$ is Hausdorff, $\pi|_{B^n_{+}}$ is a homeomorphism.
> 
> Now we prove the following claims:
> 1. **Claim 1: 3 holds for $n=0$.**
>    By excision, we have: $$H_{p}(S^0,B^0_{+})=H_{p}(\{ \pm 1 \},\{ +1 \})=H_{p}(\{ -1 \},\varnothing)=\begin{cases}G&p=0\\0&p\neq 0\end{cases}$$
> 2. **Claim 2: 1 holds for $n$ if and only if 3 holds for $n$**
>    Consider the reduced LES of $(S^n,B^n_{+})$. We have that: $$\tilde{H}_{p}(B^n_{+})\to \tilde{H}_{p}(S^n)\to H_{p}(S^n,B^n_{+})\xrightarrow{\partial_{*}}\tilde{H}_{p-1}(B^n_{+})$$However, as $B^n_{+}$ is contractible, we have that $\tilde{H}_{p}(B^n_{+})=0$ and we have that by [[Exact Sequence|Proposition 1]], $\tilde{H}_{p}(S^n)\cong H_{p}(S^n,B^n_{+})$.
> 3. **Claim 3: 2 holds for $n$ if and only if 3 holds for $n$**.
>    Let $\mathcal{U}:=\{x\in S^n:x_{n+1} > 1-\varepsilon \}$. Then, $$H_{p}(S^n,B^n_{+})\cong H_{p}(S^n \backslash U,B^n_{+} \backslash U)$$we claim that $(S^n \backslash U,B^n_{+} \backslash U)\sim(B^n_{-},S^{n-1})$. If this is true, then: $$H_{p}(S^n,B^n_{+})\cong H_{p}(B^n_{+},S^{n-1})\cong H_{p}(B^n,S^{n-1})$$where the last follows from the fact that $\pi|_{B^n_{+}}$ is a homeomorphism.
>    
>    Now, we will show the homotopy equivalence. We define: $$q:(S^n \backslash U,B^n_{+} \backslash U)\to(B^n_{-},S^{n-1}),\quad x\mapsto \begin{cases}\left( \frac{\pi(x)}{\left\| \pi(x) \right\| } ,0\right)&x\in B^n_{+}\\x&x\in B^n_{-}\end{cases}$$which is well-defined. Then, for the inclusion $i:(B^n_{-},S^{n-1})\to(S^n \backslash U, B^n_{+} \backslash U)$, we have that:
>    1. $q\circ i=\text{id}$. 
>    2. To show that $i\circ q \sim \text{id}_{(S^n \backslash U)}$, we define the homotopy: $$F:(S^n \backslash U)\times[0,1]\to S^n \backslash U,\quad (x,t)\mapsto \begin{cases}\frac{(1-t)x+tq(x)}{\left\| (1-t)x+tq(x) \right\| }&x\notin B^n_{-}\\x&x\in B^n_{-}\end{cases}$$Then, $F(x,0)=x$ and $F(x,1)=q(x)$. Further, it is well-defined as $(1-t)x+tq(x)\neq 0$ for all $x\notin B^n_{-}$ and $t\in [0,1]$.  
>  4. **Claim 4: 2 holds for $n$ if and only if 1 holds for $n-1$.**
>     Consider the reduced LES: $$0=\tilde{H}_{p}(B^n)\to H_{p}(B^n, S^{n-1})\to \tilde{H}_{p-1}(S^{n-1})\to \tilde{H}_{p-1}(B^n)=0$$which is exact. Hence, $H_{p}(B^n,S^{n-1})\cong \tilde{H}_{p-1}(S^{n-1})$.
>     
>  Hence, by induction this proves the statement.