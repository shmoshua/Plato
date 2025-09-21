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
If $\frac{r}{n}\geq \frac{1+\varepsilon}{10}$, then: $$\mathbb{E}[X]\geq \frac{1+\varepsilon}{10}k$$By Chernoff: $$\begin{aligned}\mathbb{P}\left( X\leq \frac{k}{10} \right)&\leq \mathbb{P}\left( X\leq (1-\varepsilon')\mathbb{E}[X] \right)\\&\leq \exp\left( \frac{-\varepsilon'^{2} \mathbb{E}[X]}{2} \right)\\&\leq \exp \left( -\frac{\varepsilon^{2}}{1+\varepsilon}  \frac{k}{20}\right) \end{aligned}$$Let $\varepsilon< \frac{1}{10}$, then, 

If $\frac{r}{n}\leq \frac{1-\varepsilon}{10}$, then $\mathbb{E}{X}\leq \frac{1-\varepsilon}{10} k$ By chernoff, $$\begin{aligned}\mathbb{P}\left( X\geq \frac{k}{10} \right)&\leq \mathbb{P}\left( X\geq \left( \frac{1}{1-\varepsilon} \right)\mathbb{E}[X] \right)\\&\leq \mathbb{P}\left( X\geq \left( 1+\varepsilon'\right)\mathbb{E}[X] \right)\\&\leq \exp\left( \frac{-\varepsilon^{2}}{(1-\varepsilon)^{2}3} \mathbb{E}[X]\right)\end{aligned}$$ 
