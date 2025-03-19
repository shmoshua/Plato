#Definition #Algorithms 

#### Problem 1
1. We have that: $$\begin{aligned}\mathbb{P}\left(\exists i\in[d]:\left| W_{ii} \right| \geq 2\sqrt{ \log(d / \delta) }\right)&\leq \sum_{i\in[d]}\mathbb{P}\left(\left| W_{ii} \right| \geq 2\sqrt{ \log(d / \delta) }\right)\\&\leq 2d \exp \left( -2\log (d / \delta)\right) =2 \frac{\delta^{2}}{d}\leq \delta \end{aligned}$$
2. From 1, we have that with probability at least $1-\delta$, $$\left| W_{ii} \right|<2\sqrt{ \log(d / \delta) },\quad \forall i\in[d] $$
   
   As $Y_{ii}=\lambda (x_{i}^{*})^{2}+W_{ii}$ for any $i\in[d]$ and $\left| x_{i}^{*} \right|=\frac{1}{\sqrt{ k }}$ for $i\in S^{*}$, we have: $$Y_{ii}=\begin{cases} \frac{\lambda}{k}+W_{ii}&i\in S^{*}\\W_{ii}&i\notin S^{*}\end{cases}$$Therefore, if the above inequality holds, then for any $i\in S^{*}$ and $j\notin S^{*}$: $$\left| Y_{ii} \right| =\left| 4\sqrt{ \log (d / \delta) }+W_{ii}\right|\geq  4\sqrt{ \log (d / \delta) } - \left| W_{ii} \right| >2\sqrt{ \log(d / \delta) }> \left| W_{jj} \right| =\left| Y_{jj} \right|  $$
   This means that the $k$ largest values are exactly taken from $S^{*}$ and $K=S^{*}$. Therefore, this happens also with probability at least $1-\delta$.
3. Using law of total expectation, we have: $$\begin{aligned}\mathbb{E}\left[\left\| \tilde{X}-X^{*} \right\| ^{2}_{F}\right]=\mathbb{P}(K=S^{*})\mathbb{E}\left[\left. \left\| \tilde{X}-X^{*} \right\| ^{2}_{F} \right| K=S^{*}\right]+\mathbb{P}(K\neq S^{*})\mathbb{E}\left[\left. \left\| \tilde{X}-X^{*} \right\| ^{2}_{F} \right| K\neq S^{*}\right]\end{aligned}$$Now, if $K=S$, then
