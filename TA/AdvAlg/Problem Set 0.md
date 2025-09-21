### 1. Basic Recursions
**Master theorem**:
$$T(n)=aT\left( \frac{n}{ b} \right)+f(n)$$where $a\geq 1,b>1$ and $f(n)$ is asymptotically positive. Then,
1. If $f(n)=O(n ^{\log_{b}a-\varepsilon})$ for some $\varepsilon> 0$, then $\Theta(n^{\log_{b}a})$.
2. If $f(n)=\Theta(n^{\log_{b} a}\log^k n)$ then $T(n)=\Theta(n^{\log_{b}a}\log^{k+1}n)$.
3. If $f(n)=\Omega(n^{\log_{b}a+\varepsilon})$ for $\varepsilon>0$ and $af\left( \frac{n}{b} \right)\leq c f(n)$ for some $c< 1$ and all sufficiently large $n$, then $T(n)=\Theta(f(n))$

Hence, we have: 
1. $f(n)=n(2-\cos n)$, then we have $$af\left( \frac{n}{b} \right)=2f\left( \frac{n}{3} \right)\geq f(n)$$
   
   $$2f\left( \frac{n}{3} \right)$$
2. if $f(n)=2n$ then: $$af\left( \frac{n}{b} \right)=\frac{2a}{b}n\leq$$
	1. As $\log_{3}2 <1$, we have that exists $S,T>0$ and $n_{0}$ s.t. for all $n\geq n_{0}$: $Sn \leq f(n)\leq Tn$. Hence, $$af\left( \frac{n}{b} \right)\leq \frac{aT}{b}n\leq \frac{a}{b}\cdot  \frac{T}{S}\cdot Sn$$
	2. 
	3. $$af\left( \frac{n}{b} \right)\leq \frac{aT}{b}n\leq $$
---
