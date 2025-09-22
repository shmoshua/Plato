### 1. Basic Recursions
**Master theorem**:
$$T(n)=aT\left( \frac{n}{ b} \right)+f(n)$$where $a\geq 1,b>1$ and $f(n)$ is asymptotically positive. Then,
1. If $f(n)=O(n ^{\log_{b}a-\varepsilon})$ for some $\varepsilon> 0$, then $\Theta(n^{\log_{b}a})$.
2. If $f(n)=\Theta(n^{\log_{b} a}\log^k n)$ then $T(n)=\Theta(n^{\log_{b}a}\log^{k+1}n)$.
3. If $f(n)=\Omega(n^{\log_{b}a+\varepsilon})$ for $\varepsilon>0$ and $af\left( \frac{n}{b} \right)\leq c f(n)$ for some $c< 1$ and all sufficiently large $n$, then $T(n)=\Theta(f(n))$

Hence, we have: 
1. Inconclusive. 
2. $T(n)=\Theta(n^{\log_{2}3})$
3. $T(n)=\Theta(n \log n)$
4. $f(n)=\Theta(n^{1/2})$ Hence, $T(n)=\Theta(n)$
5. $T(n)=\Theta(n \log \log n)$
6. Let $T'(k)$ s.t. $T'(\log k)=T(k)$. Then, $$T'(\log n)=T'\left( \frac{\log n}{2} \right)+1$$ Hence $T'(k)=\Theta(\log k)$

---
### 2. Estimation
Assume that $\varepsilon< \frac{1}{10}$. Then, 

If $\frac{r}{n}\geq \frac{1+\varepsilon}{10}$, then: $$\mathbb{E}[X]\geq \frac{1+\varepsilon}{10}k$$By Chernoff: $$\begin{aligned}\mathbb{P}\left( X\leq \frac{k}{10} \right)&\leq \mathbb{P}\left( X\leq (1-\varepsilon')\mathbb{E}[X] \right)\\&\leq \exp\left( \frac{-\varepsilon'^{2} \mathbb{E}[X]}{2} \right)\\&\leq \exp \left( -\frac{\varepsilon^{2}}{1+\varepsilon}  \frac{k}{20}\right) \\&\leq \exp \left( -\frac{1}{22}\varepsilon^{2} k\right) \end{aligned}$$Let $\varepsilon< \frac{1}{10}$, then, 

Setting $Y:= k-X$, we have $\mathbb{E}Y\geq \frac{9+\varepsilon}{10} k$
$$\begin{aligned}\mathbb{P}\left( Y\leq \frac{9}{10}k  \right)&=\mathbb{P}\left( Y\leq \frac{9}{9+\varepsilon}  \mathbb{E}[Y] \right) \\&=\mathbb{P}\left( Y\leq \left( 1-\frac{\varepsilon}{9+\varepsilon} \right)  \mathbb{E}[Y] \right) \\&\leq \exp \left( -\frac{\varepsilon^{2}}{(9+\varepsilon)^{2}}\frac{\mathbb{E}[Y]}{2} \right) \\&\leq \exp \left( - \frac{1}{182}\varepsilon^{2} k\right) \leq \delta\end{aligned}$$
Setting $k\geq  O\left( \frac{1}{\varepsilon^{2}}\log \frac{1}{\delta} \right)$

---
### 3. Selection
Sample a random index uniformly.

If less than $k$ elements are larger, delete them and subtract.
If at least $k$ elements are larger, then delete all smaller elements. 

In each iteration, $m-1$ comparisons are made, if the pivot is not in the smallest or largest $\left\lfloor m / 4\right\rfloor$ elements, at least $\left\lfloor m / 4\right\rfloor> m / 4-1\geq m / 8$ elements are deleted.

$$\left\lfloor \frac{m}{4}\right\rfloor\geq \frac{m-3}{4}\geq \frac{m}{8} $$$$8m-24\geq 4m$$
$$\left\lfloor \frac{m}{4}\right\rfloor \geq \frac{m-3}{4}$$
$$$$