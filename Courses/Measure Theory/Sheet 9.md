#Series #MeasureTheory 

##### Exercise 9.1
1. **False**. The limit $\lim_{ k \to \infty }\int_{\mathbb{R}}^{} f_{k} \, d\mathcal{L}^1$ does not always exist. For example, consider: $$f_{k}=k\cdot \chi_{[0,1/k]}$$for even $k$ and $f_{k}\equiv{0}$ for odd $k$. Then, $f_{k}\to f\equiv 0$ but the limit keeps alternating between $1$ and $0$.
2. **True**: Let $g_{1},g_{2}:[0,1]\to \mathbb{R}$ where $g_{1}(x)=\left| f(x) \right|$ and $g_{2}(x)=\left| x^kf(x) \right|$. Then, $g_{2}(x)\leq g_{1}(x)$ for all $x\in[0,1]$ and $\int_{0}^{1} |x^kf(x)| \, d\mathcal{L}^1=\int_{0}^{1} g_{2} \, d\mathcal{L}^1\leq\int_{0}^{1} g_{1} \, d\mathcal{L}^1=\int_{0}^{1} \left| f \right| \, d\mathcal{L}^1<+\infty$ from monotonicity. Therefore, it is $\mathcal{L}^1$-summable.
3. **False**: Consider $f$ with spikes that increases as $x\to \infty$.
4. **True**: We have that $xf(x)\geq c$ for all $x\geq R$ and follows from monotonicity.
5. **False**: from DCT 
6. **True**: Take $f_{n}=n^2\cdot\chi_{(0,1/n]}$. Then, $f_{n}(x)\to 0$ for all $x\in[0,1]$, but $\int_{0}^{1} f_{n} \, d\mathcal{L}^1=n\to \infty$.
