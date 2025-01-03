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
- **Related definition**: For $X\neq \varnothing$, let $P$ be a point space. Then, consider $\varepsilon:X\to P$ be the constant map. Then, 
	1. the ***reduced homology*** $\tilde{H}_{p}(X):=\text{ker }\varepsilon_{*}$ where $\varepsilon_{*}:H_{p}(X)\to H_{p}(P)$ for all $p\in \mathbb{Z}$.
	2. the ***reduced homology*** for a pair $(X,A)$ is given as $\tilde{H}_{p}(X,A):=H_{p}(X,A)$ for all $p\in \mathbb{Z}$.
- **Remark**: $\tilde{H}_{p}(X,\varnothing)\neq \tilde{H}_{p}(X)$ in general.
---
##### Properties
> [!lemma] Lemma 1
> Let $H$ be a homology theory. Then,
> 1. $H_{p}(\varnothing)=0$
> 2. For a [[Homotopy|homotopy equivalence]] $f:(X,A)\to(Y,B)$, $f_{*}$ is an isomorphism.

^d375b2

> [!proof]-
> We have that:
> 1. Let $Y=\varnothing$. Then, $H_{p}(X)\oplus H_{p}(\varnothing) \cong H_{p}(X)$. Hence, $H_{p}(\varnothing)=0$.
> 2. Let $g:(Y,B)\to(X,A)$ be the homology inverse of $f$. Then, $$g_{*} \circ  f_{*} = (g\circ f)_{*}=\text{id}_{*}=\text{id}_{H_{p}(X,A)}$$$$f_{*} \circ  g_{*} = (f\circ g)_{*}=\text{id}_{*}=\text{id}_{H_{p}(Y,B)}$$

^525ab9

---
> [!lemma] Theorem 2 (Reduced Homology)
> Let $\tilde{H}_{p}(X)$ be the reduced homology given by $\text{ker }\varepsilon_{*}$ where $\varepsilon:X\to P$ for the point space $P$. Then,
> 1. $H_{p}(X)=\tilde{H}_{p}(X)$ for $p\neq 0$.
> 2. $H_{0}(X)\cong \tilde{H}_{0}(X)\oplus G$

> [!proof]+
> We have that:
> 1. Follows from the fact that $\varepsilon_{*}$ is the zero map for $p\neq 0$. 
> 2. Let $i:P\to X$. Then, $$

---
> [!lemma] Theorem 3
> The singular homology is a homology theory with coefficients group $\mathbb{Z}$.
> 

---
