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

- **Related definition**: $H_{p}(X):=H_{p}$
- **Related definition**: $G:=H_{0}(X,\varnothing)$