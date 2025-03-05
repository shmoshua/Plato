#Series #Algorithms 

#### Problem 1
1. Firstly, note that: $$\frac{1}{n}\sum_{i\in[n]}^{}\braket{  x_{i},u}^{2}=\frac{1}{n }u^\top X^\top X u=u^\top u=\|u\|^2=1 $$Now, using Cauchy-Schwarz, we have for all $i\in[n]$ that: $$\braket{ x_{i} , u }^{2}\leq \braket{ x_{i} , u }\|x_{i}\|\underbrace{ \|u\| }_{ =1 }\leq C\sqrt{ d }\braket{ x_{i} , u } $$ Then, it follows that:$$\frac{1}{n}\sum_{i=1}^{n}\braket{ x_{i}, u } ^4\leq C^{2}d\left( \frac{1}{n}\sum_{i=1}^{n}\braket{ x_{i} , u } ^{2} \right) =C^{2}d$$

2. Notice that:$$u^\top M_{\text{low}}u=\frac{1}{2n}\sum_{i=1}^{n}b_{i}u^\top x_{i}x_{i}^\top u=\frac{1}{2n}\sum_{i=1}^{n} b_{i}\braket{  x_{i} ,u} ^{2}$$ As $\eta_{i}$ are independent, so are $b_{i}$. Further, we have that: $$ 0\leq \frac{1}{2n}b_{i}\braket{ x_{i} ,u}^{2}\leq  \frac{1}{2n}\braket{  x_{i},u }^{2}$$Now, by noting that:$$\mathbb{E}[u^\top M_{\text{low}} u]=\frac{1}{2n}\sum_{i=1}^{n}\mathbb{E}[b_{i}]\braket{ x_{i},u } ^{2}=\frac{\alpha}{2n}\sum_{i=1}^{n}\braket{  x_{i},u } ^{2}=\frac{\alpha}{2n}u^\top X^\top Xu=u^\top\left( \frac{\alpha}{2}I_{d} \right)u$$Therefore, by Hoeffding, $$\begin{align}\mathbb{P}\left( \left| u^\top\left( M_{\text{low}}-\frac{\alpha}{2}I_{d} \right)u \right| \geq \frac{\alpha}{24} \right)&\leq 2 \exp \left( -\frac{2\alpha^{2}}{24^{2}}\cdot \frac{1}{\frac{1}{4n^{2}}\sum_{i\in[n]}^{}\braket{ u , x_{i} } ^{4} } \right) \leq2\exp \left( -\frac{8n\alpha^{2}}{24^2 C^2d} \right)\end{align} $$This proves the statement.
3. For $A\in \text{Mat}_{d,d}(\mathbb{R})$ symmetric and $u,v\in S^{d-1}$. Then, there exists $u',v'\in \mathcal{N}_{1 / 4}$ with $\left\| u-u' \right\|\leq 1 / 4$ and $\left\| v-v' \right\|\leq 1 /4$. Therefore, $$\left| u^\top Av \right| =\left| u^\top A(v'+v-v') \right|\leq \left| u^\top Av' \right| +\frac{\left\| A^\top u \right\|}{4}  $$
   
 we have that: $$\max_{u\in S}\left| u^\top Au \right| =\max_{u,v\in S}\left| u^\top Av \right| $$

We have that: $$\begin{align}\left| u^\top Au \right| =\left| (u'+u-u')^\top A (u'+u-u') \right| &\leq \left| u'^\top Au' \right| +2\left| u'^\top A(u-u') \right| +\left| (u-u')^\top A (u-u') \right| \\&\leq \left| u'^\top A u' \right| +\frac{9}{16}\left\| A \right\|\end{align} $$

$$\begin{align} \left| u'^\top A u' \right| &=\left| (u+u'-u)^\top A (u+u'-u) \right|\\&= \left|  u^\top A u-2(u-u')\right|  \end{align}$$