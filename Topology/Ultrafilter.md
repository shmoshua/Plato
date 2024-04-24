#Definition #Topology 

> [!definition]
> Let $X$ be a set. A filter $\mathcal{F}$ is an ***ultrafilter*** if for all $A\subseteq X$ either $A\in \mathcal{F}$ or $A^c\in \mathcal{F}$.
---
##### Properties
> [!lemma] Theorem 1
> A filter $\mathcal{F}$ is an ultrafilter if and only if it is a maximal filter.

> [!proof]-
> Assume $\mathcal{F}$ is maximal and $A\notin \mathcal{F}$. Since $\mathcal{F}\cup \{ A \}$ is not a filter, $\mathcal{F}\cup \{ A \}$ doesn't have the finite intersection property. So there is $B\in \mathcal{F}$ with $B\cap A=\varnothing$. Hence, $B\subseteq A^c$ and $A^c\in \mathcal{F}$.
> 
> Conversely, assume that $\mathcal{F}$ is an ultrafilter and that there exists $\mathcal{F}\subsetneq\mathcal{G}$ where $\mathcal{G}$ is a filter. Then, there exists $A\in \mathcal{G} \backslash \mathcal{F}$ and $A^c\in \mathcal{F}$. Then, $A^c\in \mathcal{G}$ and as $\mathcal{G}\cup \{ A \}$ has the finite intersection property by Lemma 3, $A^c\cap A\neq \varnothing$, which is a contradiction.
---
> [!lemma] Lemma 2
> Every filter is contained in a maximal one.

> [!proof]-
> Let $\mathcal{F}$ be a filter: $$\mathcal{Z}:=\{ \mathcal{G} \subseteq \mathcal{P}(X):\mathcal{G}\supseteq \mathcal{F},\mathcal{G}\text{ is a filter}\}$$
> Now, let $(\mathcal{G_{i}})_{i}$ be an increasing sequence of filters. We will show that $\mathcal{G}:=\bigcup_{i}^{}\mathcal{G_{i}}$ is a filter. 
> - $\varnothing \notin \mathcal{G}$ as $\varnothing \notin \mathcal{G}_{i}$ for all $i$.
> - For $A,B\in \mathcal{G}$, there exists $i$ s.t. $A,B\in \mathcal{G_{i}}$. Therefore, $A\cap B\in \mathcal{G_{i}}$ and $A\cap B\in \mathcal{G}$.
> - For $A\in \mathcal{G}$ and $B\supseteq A$, there exists $i$ s.t. $A\in \mathcal{G}_{i}$ and $B\in \mathcal{G_{i}}$. Therefore, $B\in \mathcal{G}_{i}$.
>   
> Therefore, by [[Poset|Zorn's lemma]], $\mathcal{Z}$ has a maximal element.
---
> [!lemma] Proposition 3
> Consider the following set function $\omega:\mathcal{P}(X)\to \{ 0,1 \}$ s.t. 
> 1. $\omega(\varnothing)=0$, $\omega(X)=1$,
> 2. for $A_{1},A_{2}\subseteq X$ s.t. $A_{1}\cap A_{2}=\varnothing$, $\omega(A_{1}\cup A_{2})=\omega(A_{1})+\omega(A_{2})$
> 
> Denote $\Omega(X)$ the set of such functions and $\text{Ultra}(X)$ the set of ultrafilters on $X$. Then, $$\begin{array}{cccc} {}&{\Omega(X)}&\to&{\text{Ultra}(X)}\\&{\omega} &\mapsto & {\mathcal{F}_{\omega}:=\{ A\subseteq X:\omega(A)=1 \}} \end{array}{}$$is a bijection.

> [!proof]-
> We show that $\mathcal{F}_{\omega}$ is an ultrafilter. We see that $\varnothing\notin \mathcal{F}_{\omega}$. For $A\in \mathcal{F}_{\omega}$ and $B\supseteq A$, we have first that: $$0=\omega(X \backslash A)=\omega(X \backslash B)+\omega(B \backslash A)$$Therefore, $\omega(X \backslash B)=0$ and $\omega(B)=1$. Now, for $A,B\in \mathcal{\mathcal{F}_{\omega}}$, $$\omega(A\cap B)+\omega(A \backslash B)=\omega(A)=1$$where $\omega(A \backslash B)=0$ as $\omega(X \backslash B)=0$ and $A \backslash B\subseteq X \backslash B$. Finally, for $A\subseteq X$, $\omega(A)=1$ or $\omega(X \backslash A)=1$ as $\omega(X)=1$. 
> 
> Conversely, assume $\mathcal{F}$ is an ultrafilter and we define the set function: $$\omega(A)=1 \iff A\in \mathcal{F}$$Then, $\omega(\varnothing)=0$ and therefore, $X\in \mathcal{F}$ and $\omega(X)=1$. Similarly, for $A_{1},A_{2}\subseteq X$ with $A_{1}\cap A_{2}=\varnothing$, it's not possible that $A_{1}\in \mathcal{F}\land A_{2}\in \mathcal{F}$ from the finite intersection property. Therefore, if $A_{1}\in \mathcal{F}$ wlog, then $A_{1}\cup A_{2}\in \mathcal{F}$ and if $A_{1},A_{2}\notin \mathcal{F}$, Then, $X \backslash A_{1} \cap X \backslash A_{2}=X \backslash (A_{1}\cup A_{2})\in \mathcal{F}$ and $\omega(A_{1}\cup A_{2})=0$.
---
> [!lemma] Proposition 4
> For a topological space $X$, the following are equivalent:
> 1. $X$ is [[Compact Space|compact]].
> 2. every ultrafilter $X$ converges.

^041e9b

---
 > [!lemma] 