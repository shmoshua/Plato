#Series #Topology 
> [!def] Problem 1
> Let $X$ be a non-empty set.
> 1. Show that an ultrafilter $\mathcal{F}$ on $X$ is principal if and only if there exists a finite set $A\subseteq X$ such that $A\in\mathcal{F}$.
> 2. Show that if $X$ is infinite, then there exists a non-principal ultrafilter on $X$.
> 3. Let $\mathcal{F}$ be an ultrafilter on $X$. Show that if $A,B$ are subsets of $X$, then $A\cup B\in \mathcal{F}$ if and only if $A\in \mathcal{F}$ or $B\in \mathcal{F}$.
> 4. For $\mathcal{F}$ as above, define a function $\mu$ from the subsets of $X$ to $\{ 0,1 \}$ by $$\mu(A)=\begin{cases}1&A\in\mathcal{F}\\0&A\notin\mathcal{F}\end{cases}$$Show that for any subsets $A,B\subseteq X$ with $A\cap B=\varnothing$, $\mu(A\cup B)=\mu(A)+\mu(B)$.
> 5. Conversely, let $\nu$ be a function from the subsets of $X$ to $\{ 0,1 \}$ such that $\nu(X)=1$ and $\nu(A\cup B)=\nu(A)+\nu(B)$ whenever $A\cap B=\varnothing$. Show that $\nu(A\cap B)+\nu(A\cup B)=\nu(A)+\nu(B)$ for any subsets $A,B\subseteq X$.
> 6. Show that $\mathcal{F}_{\nu}:=\{ A \subseteq X:\nu(A)=1 \}$ is an ultrafilter on X.

We have: 
1. Assume $\mathcal{F}$ is a principal ultrafilter of $x\in X$. Then, $\{ x \}\in \mathcal{F}$. Conversely, let $A\subseteq X$ be a finite set s.t. $A\in \mathcal{F}$. Let $F\cup G\in \mathcal{F}$. Then, $F\in\mathcal{F}$ or $G\in \mathcal{F}$. Assume otherwise. Then, $F^c,G^c$ are in $\mathcal{F}$ and $F^c\cap G^c=(F\cup G)^c\in \mathcal{F}$, which is a contradiction. Therefore, there exists $x\in A$ s.t. $\{ x \}\in \mathcal{F}$.
2. We have that $\mathcal{F}:=\{ A\subseteq X:A^c\text{ is finite} \}$ is a filter. Therefore, there exists an ultrafilter $\mathcal{G}\supseteq\mathcal{F}$. If $\mathcal{G}$ is principal, then there exists a finite set $A\in \mathcal{G}$ and $A^c\notin\mathcal{G}$ which is a contradiction as $A^c\in \mathcal{F}$.
3. One direction is shown above. Wlog assume that $A\in \mathcal{F}$. Then, $A\subseteq A\cup B\in \mathcal{F}$.
4. If $\mu(A\cup B)=1$, $A\cup B\in \mathcal{F}$ and $A\in \mathcal{F}$ or $B\in \mathcal{F}$. Assume $A\in \mathcal{F}$. Then, $A^c\notin \mathcal{F}$. However, then if $B\in \mathcal{F}$, then $B\subseteq A^c\in \mathcal{F}$. Therefore, $B\notin\mathcal{F}$ and $\mu(A)+\mu(B)=1$. Conversely, assume that $\mu(A\cup B)=0$. Then, $A\notin \mathcal{F}$ and $B\notin \mathcal{F}$ as  $A,B\subseteq A\cup B$. Therefore, $\mu(A)+\mu(B)=0$.
5. We have $\nu(B)=\nu(B \backslash A)+\nu(A\cap B)$ and $$\nu(A\cup B)+\nu(A\cap B)=\nu(A)+\nu(B \backslash A)+\nu(A\cap B)=\nu(A)+\nu(B)$$
6. As $\nu(X)=1$, $X\in \mathcal{F_{\nu}}$ and $\nu(\varnothing)=0$ with $\varnothing\notin \mathcal{F}_{\nu}$. For $A\subseteq B$ with $A\in \mathcal{F}_{\nu}$, $\nu(A)=1$ and $\nu(B)=\nu(A)+\nu(B \backslash A)\geq 1$. Therefore, $\nu(B)=1$ and $B\in \mathcal{F}_{\nu}$. Lastly, for $A,B\in \mathcal{F}_{\nu}$, $\nu(A \cap B)=\nu(A)+\nu(B)-\nu(A \cup B)=1$. Therefore, $A\cap B\in \mathcal{F}_{\nu}$. To show that it is an ultrafilter, for $A\subseteq X$, $1=\nu(X)=\nu(A)+\nu(X \backslash A)$. Therefore, either $A\in \mathcal{F}_{\nu}$ or $A^c\in \mathcal{F}_{\nu}$.
---
> [!def] Problem 2
> We have:
> 1. Let $X$ be a topological space and let $A$ be a connected subset of $X$. If $B$ is a subset of $X$ such that $A\subseteq B\subseteq \overline{A}$, show that $B$ is connected.
> 2. Let $$A:=\{ (x,y)\in \mathbb{R}^{2} : x>0,y=\text{sin}(1 / x) \}\subseteq \mathbb{R}^{2}$$Show that $A$ is connected.

We have: 
1. Assume $B$ is disconnected. Then, there exists disjoint open $U_{1},U_{2}$ with $B\subseteq U_{1}\cup U_{2}$ s.t. $B\cap U_{1},B\cap U_{2}\neq \varnothing$. Then, $A\subseteq U_{1}\cup U_{2}$ and $A\cap U_{1}$ and $A\cap U_{2}$ are disjoint. However, as $A$ is connected, we can assume wlog $A\subseteq U_{1}$. Therefore, $U_{2}^c$ is a closed set that contains $A$ and $\overline{A}\subseteq U_{2}^c$. This is a contradiction to $B\subseteq \overline{A}$. 
2. We have that $f:\mathbb{R}\to \mathbb{R}^{2},x\mapsto(x,\sin(1/x))$ is continuous and $A=f((0,+\infty))$
---
> [!def] Problem 3
> Let $X$ be a topological space and $A\subseteq X$.
> 1. Show that $$X-\partial A=A^\circ \cup(X \backslash A)^\circ $$
> 2. Let $B\subseteq X$ be a connected subspace. If $B\cap \partial A$ is empty, show that $B\subseteq A^\circ$ or $B\subseteq(X \backslash A)^\circ$.
> 3. 