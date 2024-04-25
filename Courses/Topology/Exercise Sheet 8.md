#Series #Topology 

> [!def] Problem 1
> Let $X:=L^2([0,1])$ with the topology defined by the distance $$d(f,g):=\left( \int_{0}^{1} \left| f-g \right| ^{2} \, dx  \right) ^{1/2}$$
> 1. For $f\in X$ and $\varepsilon>0$, show that the closed ball $$B_{\leq \varepsilon}(f):=\{ g\in X:d(f,g)\leq \varepsilon \}$$ is not compact. (Hint: start with f = 0 and ε = 1, which was an example in the lecture.) 
> 2. Deduce that $X$ is not locally compact, and in fact that there is no $f\in X$ which has any compact neighborhood.
---
> [!def] Problem 2
> Let $(X_{i})_{i\in I}$ be a family of topological spaces and let $$X:=\prod_{i\in I}^{}X_{i}$$ with the product topology. 
> 1. If $X_{i}$ is Hausdorff for all i, prove that X is also Hausdorff. 
> 2. Let $Y_{i}\subseteq X_{i}$ be an arbitrary subset for each $i$. Show that the subspace topology on $$Y:=\prod_{i\in I}^{}Y_{i}\subseteq X$$ is the product of the subspace topologies of $Y_{i}$. 
> 3. Let $Y_{i}\subseteq X_{i}$ be an arbitrary subset for each $i$. Show that $$\overline{\prod_{i\in I}Y_{i}}=\prod_{i\in I}^{}\overline{Y_{i}}$$
> 4. If $C_{i}\subseteq X_{i}$ is closed for all $i$ show that the subset $\prod_{i\in I}^{}C_{i}$ is closed in $X$.
> 5. Give an example of a set $I$, spaces $X_{i}$ and open subsets $U_{i}\subseteq X_{i}$ s.t. $\prod_{i\in I}^{}U_{i}$ is not open in $X$. 
> 6. Let $x_{n}=(x_{n,i})_{i\in I}$ be elements of $X$ for all $n\geq 1$. Show that the sequence $x_{n}\to x=(x_{i})_{i\in I}$ if and only if $x_{n,i}\to x_{i}$ for all $i\in I$.
> 7. For any $x=(x_{i})_{i}$ in $X$, show that the connected component of $X$ is equal to the product of the connected components $Y_{i}$ of $x_{i}$ in $X_{i}$.
---
> [!def] Problem 3
> Let $(X_{n},d_{n})_{n\geq 1}$ be a sequence of metric spaces. Denote $X:=\prod_{n\geq 1}^{}X_{n}$. 
> 1. Show that for $x=(x_{n})_{n}$ and $y=(y_{n})_{n}$ in $X$, the series $$d(x,y):=\sum_{n\geq 1}^{} \frac{1}{2^n}\frac{d_{n}(x_{n},y_{n})}{1+d_{n}(x_{n},y_{n})}$$ d(x, y) = X n≥1 1 2 n dn(xn, yn) 1 + dn(xn, yn) is (absolutely) convergent and that the function d: X × X → [0, +∞[ it defines is a distance on X. (b) Show that the topology defined by d is the product topology on X. (c) Show that if Xn is complete for all n, then X is complete. (This fact is also true for an arbitrary product of complete spaces in the sense of uniform structures.) (d) Assume that Xn is compact for all n. Show that if xm = (xm,n)n≥1 is an element of X for all m ≥ 1, then the sequence (xm)m≥1 has a convergent subsequence. (Hint: show that for every N ≥ 1, there exists a sequence x (N) = (x (N) k )k≥1 of elements of X such that (1) x (1) = (xm); (2) x (N) is a subsequence of x (N−1); (3) for 1 ≤ n ≤ N, the sequence of n-th coordinates (x (N) k )n converges as k → +∞. To conclude, construct a convergence subsequence of (xm) by a diagonal argument.) (e) Deduce that X is compact without using Tychonov’s Theorem.