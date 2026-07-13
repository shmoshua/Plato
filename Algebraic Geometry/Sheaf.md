#Definition #AlgebraicGeometry 

> [!definition]
> Let $X$ be a [[topological space]].
> 1. A ***presheaf*** $\mathcal{F}$ of rings assigns a ring $\mathcal{F}(U)$ to every open $U\subseteq X$ and a ring homomorphism $\rho_{V,U}:\mathcal{F}(V)\to \mathcal{F}(U)$ to every inclusion $U\subseteq V$ of open sets in $X$ s.t. 
> 	- $\mathcal{F}(\varnothing)=0$,
> 	- $\rho_{U,U}=\text{id}_{\mathcal{F}(U)}$ for any open $U$,
> 	- for any inclusion $U\subseteq V\subseteq W$, $\rho_{W,V}\circ\rho_{V,U}=\rho_{W,U}$.
> 2. A presheaf $\mathcal{F}$ is a ***sheaf*** if further for any open set $U\subseteq X$ with an arbitrary open cover $\{ U_{i} \}_{i}$ of $U$, for sections $\varphi_{i}\in \mathcal{F}(U_{i})$ s.t. $\varphi_{i}=\varphi_{j}$ on $U_{i}\cap U_{j}$, there exists a unique $\varphi\in \mathcal{F}(U)$ s.t. $\varphi|_{U_{i}}=\varphi_{i}$. 
> 3. For a presheaf $\mathcal{F}$ on $X$ and $a\in X$, the ***stalk*** of $\mathcal{F}$ at $a$ is defined as:$$\mathcal{F}_{a}:=\{ (U,\varphi):U\subseteq X\text{ open with }a\in U, \varphi\in \mathcal{F}(U) \}/_{\sim}$$where $(U,\varphi)\sim(U',\varphi')$ if and only if there is an open subset $V$ with $a\in V \subseteq U\cap U'$ and $\varphi|_{V}=\varphi'|_{V}$.
> 4. For a sheaf $\mathcal{F}$ on $X$ and a non-empty irreducible closed subset $Y\subseteq X$, the ***stalk of $\mathcal{F}$ at $Y$*** is defied as: $$\mathcal{F}_{Y}:=\{ (U,\varphi) :U\subseteq X\text{ open with }U\cap Y\neq \varnothing,\varphi\in \mathcal{F}(U) \} / _{\sim}$$where $(U,\varphi)\sim(U',\varphi')$ if and only if there is an open subset $V\subseteq U\cap U'$ with $V\cap Y\neq \varnothing$ and $\varphi|_{V}=\varphi'|_{V}$. 


- **Related definition**: The elements of $\mathcal{F}(U)$ are called ***sections***. The elements of $\mathcal{F}_{a}$ are called ***germs***.
- **Related definition**: For a presheaf $\mathcal{F}$ on $X$ and $U\subseteq X$ open, the restriction of $\mathcal{F}$ to $U$ is given by: $$\mathcal{F}|_{U}(V):=\mathcal{F}(V),\quad \forall V\subseteq U\text{ open}$$If $\mathcal{F}$ is a sheaf then so is $\mathcal{F}|_{U}$. 
- **Remark**: $\mathcal{F}_{a}$ is a ring for all $a\in X$.
---
> [!lemma] Lemma 1
> Let $\varphi,\psi\in \mathcal{F}(U)$ be two sections of a sheaf $\mathcal{F}$ on an open subset $U$ of a topological space $X$. 
> 1. if $\overline{(U,\varphi)}=\overline{(U,\psi)}\in \mathcal{F}_{a}$ for all $a\in U$, $\varphi=\psi$.
> 2. Let $U\ni a$ be an open neighborhood of $a$. Then, $\mathcal{F}_{a}\cong (\mathcal{F}|_{U})_{a}$

> [!proof]-
> We have that:
> 1. Assume that $\varphi\neq \psi$. Then there exists $a\in U$ s.t. $\varphi(a)\neq \psi(a)$. However, there exists an open subset $V\ni a$ in $U$ where $\varphi|_{V}=\psi|_{V}$. Hence, $\varphi(a)=\psi(a)$. This is a contradiction.
> 2. Consider the following homomorphism: $$\mathcal{F}_{a}\to (\mathcal{F}|_{U})_{a},\quad \overline{(V,\varphi)}\mapsto  \overline{(V\cap U,\varphi)}$$Notice that as $V\subseteq X$ is open with $a\in V$ and $\varphi\in \mathcal{F}(V)$, $a\in V\cap U$ is an open neighborhood and $\varphi\in \mathcal{F}|_{U}(V\cap U)$. Further, if $(V,\varphi)\sim(V',\varphi')$, then there exists $a\in W\subseteq V\cap V'$ with $\varphi|_{W}=\varphi'|_{W}$. Hence, $\varphi|_{W\cap U}=\varphi'|_{W\cap U}$. Therefore, this is well-defined. 
>    
>    For surjectivity, let $\overline{(W,\varphi)}\in (\mathcal{F}|_{U})_{a}$ where $W\subseteq U$ is open with $a\in W$. Then, by definition $W$ is open in $X$ and $\overline{(W,\varphi)}\in \mathcal{F}_{a}$. 
>    
>    For injectivity, let $\overline{(V\cap U,\varphi)}=0$ in $(\mathcal{F}|_{U})_{a}$. Then, there exists some open neighborhood $a\in W\subseteq V\cap U$ where $\varphi|_{W}=0$. Then, we have that $(V,\varphi)\sim(W,0)$ in $\mathcal{F}_{a}$. This proves the statement. 
---
##### Examples
> [!h] Example 1 (The sheaf of functions)
> The following are sheaves:
> 1. The sheaf of regular functions is given by $\mathcal{O}_{X}$.
> 2. The sheaf of continuous functions $\mathcal{F}(U):=C(U;R)$.
- **Remark**: Constant functions do not form a sheaf, only a presheaf. Let $U$ and $V$ be two non-empty disjoint open sets. Then, for $\varphi_{1}\in \mathcal{F}(U_{1})$ and $\varphi_{2}\in \mathcal{F}(U_{2})$, if we take $U:= U_{1}\cup U_{2}$, there is no function in $\mathcal{F}(U)$ that restricts to $\varphi_{1}$ and $\varphi_{2}$.