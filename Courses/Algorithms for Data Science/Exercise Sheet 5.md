#Definition #Algorithms 

#### Problem 1
1. We have that: $$\begin{aligned}\mathbb{P}\left(\exists i\in[d]:\left| W_{ii} \right| \geq 2\sqrt{ \log(d / \delta) }\right)&\leq \sum_{i\in[d]}\mathbb{P}\left(\left| W_{ii} \right| \geq 2\sqrt{ \log(d / \delta) }\right)\\&\leq 2d \exp \left( -2\log (d / \delta)\right) =2 \frac{\delta^{2}}{d}\leq \delta \end{aligned}$$
2. From 1, we have that with probability at least $1-\delta$, $$\left| W_{ii} \right|<2\sqrt{ \log(d / \delta) },\quad \forall i\in[d] $$
   
   As $Y_{ii}=\lambda (x_{i}^{*})^{2}+W_{ii}$ for any $i\in[d]$ and $\left| x_{i}^{*} \right|=\frac{1}{\sqrt{ k }}$ for $i\in S^{*}$, we have: $$Y_{ii}=\begin{cases} \frac{\lambda}{k}+W_{ii}&i\in S^{*}\\W_{ii}&i\notin S^{*}\end{cases}$$Therefore, if the above inequality holds, then for any $i\in S^{*}$ and $j\notin S^{*}$: $$\left| Y_{ii} \right| =\left| 4\sqrt{ \log (d / \delta) }+W_{ii}\right|\geq  4\sqrt{ \log (d / \delta) } - \left| W_{ii} \right| >2\sqrt{ \log(d / \delta) }> \left| W_{jj} \right| =\left| Y_{jj} \right|  $$
   This means that the $k$ largest values are exactly taken from $S^{*}$ and $K=S^{*}$. Therefore, this happens also with probability at least $1-\delta$.
3. Using law of total expectation, we have: $$\begin{aligned}\mathbb{E}\left[\left\| \tilde{X}-X^{*} \right\| ^{2}_{F}\right]=\mathbb{P}(K=S^{*})\mathbb{E}\left[\left. \left\| \tilde{X}-X^{*} \right\| ^{2}_{F} \right| K=S^{*}\right]+\mathbb{P}(K\neq S^{*})\mathbb{E}\left[\left. \left\| \tilde{X}-X^{*} \right\| ^{2}_{F} \right| K\neq S^{*}\right]\end{aligned}$$Now, if $K=S^{*}$, then for any $i,j\in[d]$ s.t. $i\notin S^{*}$ or $j\notin S^{*}$, we have that $\tilde{X}_{ij}=0$ and $X^{*}=0$. Hence, $\left\| \tilde{X}-X^{*} \right\| ^2_{F}=\left\| \widehat{X}(S^{*})-X^{*}_{S^{*}} \right\| ^{2}_{F}$.
   
   Conversely, if $K\neq S^{*}$, then: $$\left\| \tilde{X}-X^{*} \right\| ^2_{F}\leq \left\| \tilde{X} \right\| ^{2}_{F}+2\left\| \tilde{X} \right\| \left\| X^{*} \right\| + \left\| X^{*} \right\| ^{2}_{F}$$We want to show that: $$\left\| \tilde{X} \right\| _{F}^{2}=\left\| \widehat{X}(K) \right\|^{2}_{F}=\sum_{i,j\in }^{} $$
   We have that: $$\left\| X^{*} \right\| ^{2}_{F}=\sum_{i,j\in S^{*}}^{} \frac{\lambda^{2}}{k^{2}}=\lambda^{2}$$
4. By definition: $$\left\| \widehat{X}(K)-Y_{K} \right\|^{2}_{F}\leq \left\| X^{*}_{K}-Y_{K} \right\|^{2}_{F}=\left\|  \right\|   $$
   We have that: $$\frac{1}{k^{2}}\mathbb{E}\left[\left\| \widehat{X}(K) -Y_{K}\right\|^{2}_{F} \right]\leq O\left( \frac{1}{k} \right)$$
