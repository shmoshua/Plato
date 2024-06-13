#Definition #Topology 

> [!definition]
> Let $X$ be a set. A [[filter]] $\mathcal{F}$ is an ***ultrafilter*** if for all $A\subseteq X$ either $A\in \mathcal{F}$ or $A^c\in \mathcal{F}$.
---
##### Properties
> [!lemma] Proposition 1
> For $X$, we have:
> 1. A filter $\mathcal{F}$ is an ultrafilter if and only if it is a maximal filter.
> 2. Every filter is contained in an ultrafilter.
> 3. For an ultrafilter $\mathcal{F}$, $A\cup B\in \mathcal{F}$ if and only if $A\in \mathcal{F}$ or $B\in \mathcal{F}$

^574d44

> [!proof]-
> We have:
> 1. Assume $\mathcal{F}$ is maximal and $A\notin \mathcal{F}$. Since $\mathcal{F}\cup \{ A \}$ is not contained in a filter, by [[Filter|Filter Lemma 3]], $\mathcal{F}\cup \{ A \}$ doesn't have the finite intersection property. So there is $B\in \mathcal{F}$ with $B\cap A=\varnothing$. Hence, $B\subseteq A^c$ and $A^c\in \mathcal{F}$.
>    
>    Conversely, assume that $\mathcal{F}$ is an ultrafilter and that there exists $\mathcal{F}\subsetneq\mathcal{G}$ where $\mathcal{G}$ is a filter. Then, there exists $A\in \mathcal{G} \backslash \mathcal{F}$ and $A^c\in \mathcal{F}$. Then, $A^c\in \mathcal{G}$ and as $\mathcal{G}\cup \{ A \}$ has the finite intersection property, $A^c\cap A\neq \varnothing$, which is a contradiction.
> 2. Let $\mathcal{F}$ be a filter. It suffices to show that $\mathcal{F}$ is contained in a maximal filter: $$\mathcal{Z}:=\{ \mathcal{G} \subseteq \mathcal{P}(X):\mathcal{G}\supseteq \mathcal{F},\mathcal{G}\text{ is a filter}\}$$
> Now, let $(\mathcal{G_{i}})_{i}$ be an increasing sequence of filters. We will show that $\mathcal{G}:=\bigcup_{i}^{}\mathcal{G_{i}}$ is a filter. 
>    1. $\varnothing \notin \mathcal{G}$ as $\varnothing \notin \mathcal{G}_{i}$ for all $i$.
>    2. For $A,B\in \mathcal{G}$, there exists $i$ s.t. $A,B\in \mathcal{G_{i}}$. Therefore, $A\cap B\in \mathcal{G_{i}}$ and $A\cap B\in \mathcal{G}$.
>    3. For $A\in \mathcal{G}$ and $B\supseteq A$, there exists $i$ s.t. $A\in \mathcal{G}_{i}$ and $B\in \mathcal{G_{i}}$. Therefore, $B\in \mathcal{G}_{i}$.
>   
>    Therefore, by [[Poset|Zorn's lemma]], $\mathcal{Z}$ has a maximal element.
> 3. Let $A\cup B\in \mathcal{F}$ and assume $A\notin \mathcal{F}$ and $B\notin \mathcal{F}$. Then, $F^c,G^c\in \mathcal{F}$ and: $$F^c\cap G^c=(F\cup G)^c\in \mathcal{F}$$which is a contradiction. Conversely, if $A\in \mathcal{F}$, then $A\subseteq A\cup B\in \mathcal{F}$.

^e1a97b

---

> [!lemma] Proposition 2
> For a topological space $X$, the following are equivalent:
> 1. $X$ is [[Compact Space|compact]].
> 2. every ultrafilter $\mathcal{F}$ on $X$ converges.

^041e9b

> [!proof]-
> We have:
> 1. (1=>2): Assume that $X$ is compact and let $\mathcal{F}$ be an ultrafilter on $X$. Then, for $$\mathcal{A}:=\{ \overline{A}\subseteq X:A\in \mathcal{F} \}\subseteq \mathcal{F}$$by [[Filter|Lemma 3]], $\mathcal{A}$ has finite intersection property. Therefore, by [[Compact Space|Theorem 2]], $\bigcap_{A\in \mathcal{F}}^{}\overline{A}\neq \varnothing$. Let $x\in \bigcap_{A\in \mathcal{F}}^{}\overline{A}$. We will show that $\mathcal{F}\to x$. Let $U\ni x$ be an open neighborhood. Then, $U\in \mathcal{F}$ as otherwise $X \backslash U\in \mathcal{F}$, which cannot happen as $x\notin X \backslash U$. 
> 2. (2=>1): Assume that every ultrafilter converges. Let $(U_{i})_{i\in I}$ be an open covering of $X$. Assume that there is no finite subcovering. Then, $$\mathcal{F}:=\left\{  A\subseteq X: A\supseteq \bigcap_{j\in J}^{}(X\backslash U_{j}),J\subseteq I\text{ finite}  \right\}$$is clealry a filter. Then, by Proposition 1, there exists an ultrafilter $\tilde{\mathcal{F}} \supseteq\mathcal{F}$ and $\tilde{\mathcal{F}}\to x\in X$. However, for any $i\in I$ and any neighborhood of $U\ni x$, we have that: $U\in \tilde{\mathcal{F}}$ and $X \backslash U_{i}\in \tilde{\mathcal{F}}$. Therefore, $U\cap X \backslash U_{i}\in \tilde{ \mathcal{F}}$ with $\varnothing\neq U\cap X \backslash U_{i}$. Hence, $x\in \overline{X \backslash U_{i}}=X \backslash U_{i}$. We conclude that: $$x\in \bigcap_{i\in I}^{}X \backslash U_{i}=X \backslash \bigcup_{i\in I}^{}U_{i}=X \backslash X=\varnothing$$which is a contradiction.

^e2df7f

---
> [!lemma] Lemma 3
> Let $\mathcal{F}$ be an ultrafilter on $X$ non-empty. TFAE:
> 1. $\mathcal{F}$ is [[Filter|principal]], i.e. there exists $x\in X$ s.t. $\mathcal{F}=\mathcal{F}_{x}$.
> 2. there exists a finite set $A\in \mathcal{F}$

> [!proof]-
> Assume $\mathcal{F}$ is a principal ultrafilter of $x\in X$. Then, $\{ x \}\in \mathcal{F}$. Conversely, let $A\subseteq X$ be a finite set s.t. $A\in \mathcal{F}$. Then by Proposition 1.3, we can iteratively find a smaller set that is in $\mathcal{F}$.
- **Corollary**: The [[filter|Frechet filter]] is contained in a non-principal filter.
---

> [!lemma] Proposition 4
> Consider the following set function $\omega:\mathcal{P}(X)\to \{ 0,1 \}$ s.t. 
> 1. $\omega(\varnothing)=0$, $\omega(X)=1$,
> 2. for $A_{1},A_{2}\subseteq X$ s.t. $A_{1}\cap A_{2}=\varnothing$, $\omega(A_{1}\cup A_{2})=\omega(A_{1})+\omega(A_{2})$
> 
> Denote $\Omega(X)$ the set of such functions and $\text{Ultra}(X)$ the set of ultrafilters on $X$. Then, $$\begin{array}{cccc} {}&{\Omega(X)}&\to&{\text{Ultra}(X)}\\&{\omega} &\mapsto & {\mathcal{F}_{\omega}:=\{ A\subseteq X:\omega(A)=1 \}} \end{array}{}$$is a bijection.

> [!proof]-
> We have:
> 1. **Claim 1: $\mathcal{F}_{\omega}$ is an ultrafilter.**
>    We have $\omega(B)=\omega(B \backslash A)+\omega(A\cap B)$ and $$\omega(A\cup B)+\omega(A\cap B)=\omega(A)+\omega(B \backslash A)+\omega(A\cap B)=\omega(A)+\omega(B)$$
>    
>    1. As $\omega(\varnothing)=0$, $\varnothing\notin \mathcal{F}_{\omega}$. 
>    2. For $A\subseteq B$ with $A\in \mathcal{F}_{\omega}$, $\omega(A)=1$ and $\omega(B)=\omega(A)+\omega(B \backslash A)\geq 1$. Therefore, $\omega(B)=1$ and $B\in \mathcal{F}_{\omega}$. 
>    3. Lastly, for $A,B\in \mathcal{F}_{\omega}$, $\omega(A \cap B)=\omega(A)+\omega(B)-\omega(A \cup B)=1$. Therefore, $A\cap B\in \mathcal{F}_\omega$. 
>    4. for $A\subseteq X$, $1=\omega(X)=\omega(A)+\omega(X \backslash A)$. Therefore, either $A\in \mathcal{F}_{\omega}$ or $A^c\in \mathcal{F}_{\omega}$.
> 2. **Claim 2: Inverse**:
>    Conversely, assume $\mathcal{F}$ is an ultrafilter and we define the set function: $$\omega(A)=1 \iff A\in \mathcal{F}$$Then, $\omega(\varnothing)=0$ and therefore, $X\in \mathcal{F}$ and $\omega(X)=1$. Similarly, for $A_{1},A_{2}\subseteq X$ with $A_{1}\cap A_{2}=\varnothing$, it's not possible that $A_{1}\in \mathcal{F}\land A_{2}\in \mathcal{F}$ from the finite intersection property. Therefore, if $A_{1}\in \mathcal{F}$ wlog, then $A_{1}\cup A_{2}\in \mathcal{F}$ and if $A_{1},A_{2}\notin \mathcal{F}$, Then, $X \backslash A_{1} \cap X \backslash A_{2}=X \backslash (A_{1}\cup A_{2})\in \mathcal{F}$ and $\omega(A_{1}\cup A_{2})=0$.
---
 > [!lemma] Lemma 5
 > Let $X:=\prod_{i\in I}^{}X_{i}$. For any ultrafilter $\mathcal{F}$ on $X$, the [[Filter|direct image]] $(p_{i})_{*}(\mathcal{F})$ is an ultrafilter.

^8bbcf9

> [!proof]-
> Let $A\subseteq X_{i}$ and consider $B:=p_{i}^{-1}(A)$ . As $\mathcal{F}$ is an ultrafilter, we have that either $B\in \mathcal{F}$, in which case $A\in (p_{i})_{*}(\mathcal{F})$ or $X \backslash B\in \mathcal{F}$, in which case $X_{i} \backslash A\in (p_{i})_{*}(\mathcal{F})$.
---