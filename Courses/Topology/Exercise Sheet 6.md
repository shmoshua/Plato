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
1. Assume $\mathcal{F}$ is a principal ultrafilter of $x\in X$. Then, $\{ x \}\in \mathcal{F}$. Conversely, let $A\subseteq X$ be a finite set s.t. $A\in \mathcal{F}$. 