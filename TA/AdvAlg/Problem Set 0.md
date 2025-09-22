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

Until $m> 17$ elements left.

If the pivot is not in the smallest or largest $\left\lceil m / 4\right\rceil$ elements, then at least $\left\lceil m / 4\right\rceil\geq m / 4$ elements are deleted. This happens with probability at most 1/2. Hence, $$T(n)\leq n-1+\frac{1}{2}T\left( \frac{7}{8}n \right)+\left( \frac{n}{2} +1\right)T(n)$$


We have that: $$\frac{2\left\lceil m /4\right\rceil }{m}\leq \frac{2}{m}\left( \frac{m+4}{4} \right) \leq \frac{1}{2}\left( 1+\frac{4}{m} \right) < \frac{5}{8}$$
We have that: $$\frac{2\left\lceil m /4\right\rceil }{m}\leq \frac{4}{5}\leq \frac{7}{8}$$

Hence, $$T(n)\leq \frac{1}{2(1-p)}T\left( \frac{3}{4}n \right)+\Theta(n)$$We have that:

---
### 4. Quicksort


Wlog $i<j$. 

$$\frac{j-i+1}{n}\cdot  \frac{2}{j-i+1}+\left( \frac{n-(j-i+1)}{n} \right) $$


$$p=\frac{2}{n}+\left( 1-\frac{j-i+1}{n} \right)p(k)$$

$$\frac{2}{m+j-i+1}$$