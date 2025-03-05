#Series #Algorithms 

#### Problem 1
1. Firstly, n
   
   Using Cauchy-Schwarz, $$\frac{1}{n}\sum_{i=1}^{n}\braket{ x_{i} , u } ^4\leq \frac{1}{n}\sum_{i=1}^{n}\|x_{i}\|^4\underbrace{ \|u\| ^4}_{ =1 }\leq\frac{1}{n}\sum_{i=1}^{n}C^{4}d^{2}=C^4d^{2}$$$$\frac{1}{n}\sum_{i=1}^{n}\braket{ x_{i} , u } ^4\leq \frac{1}{n}\left( \sum_{i=1}^{n}\braket{ x_{i} , u } ^2 \right)^2\leq \frac{1}{n}\left( \sum_{i=1}^{n}\|x_{i}\|^2 \right)^2=\frac{1}{n}\text{tr}(XX^\top)^2=\frac{1}{n}\text{tr}(X^\top X)^{2}=nd^{2}$$It suffices to show that $nd^{2}\leq C^{2}d$. We have: $$nd=\sum_{i=1}^{n}\left\| x_{i} \right\| ^{2}\leq nC^{2}d$$
   
   $nd^{2}\leq \|x_{i}\|^2$. 

We have: $$\sum_{i=1}^{n}\left\| x_{i} \right\| ^{2}=nd$$. Hence, $d\leq\max\|x_{i}\|^2\leq C^{2}d$. $$\sum_{i=1}^{n}\|x_{i}\|^4\leq$$ $$\frac{1}{n}\sum_{i=1}^{n}\braket{ x_{i} , u } ^4\leq \frac{1}{n}\sum_{i=1}^{n}\|x_{i}\|^2\braket{ x_{i} , u } ^{2}\leq \frac{C^{2}d}{n}\sum_{i=1}^{n}\braket{ x_{i} , u } ^{2}$$$$\sum_{i=1}^{n}\left\| x_{i} \right\| ^4=\text{tr}(XX^\top)$$
 $$\sum_{i=1}^{n}\braket{ x_{i} , u } ^2=\|Xu\|^2\leq \left\| X \right\| ^{2}$$

1. Notice that:$$u^\top M_{\text{low}}u=\sum_{j,k=1}^{d}\sum_{i=1}^{n} \frac{1}{2n}b_{i}u_{j}u_{k}x_{ij}x_{ik}=\frac{1}{2n}\sum_{i=1}^{n} b_{i}\braket{ u , x_{i} } ^{2}$$ As $\eta_{i}$ are independent, so are $b_{i}$. Further, we have that: $$ 0\leq \frac{1}{2n}b_{i}\braket{ u , x_{i} }^{2}\leq  \frac{1}{2n}\braket{ u , x_{i} }^{2}$$By noting that:$$\mathbb{E}[u^\top M_{\text{low}} u]=\frac{1}{2n}\sum_{i=1}^{n}\mathbb{E}[b_{i}]\braket{ u , x_{i} } ^{2}=\frac{\alpha}{2n}\sum_{i=1}^{n}\braket{ u , x_{i} } ^{2}=\frac{\alpha}{2n}u^\top X^\top Xu=u^\top\left( \frac{\alpha}{2}I_{d} \right)u$$Therefore, by Hoeffding, $$\begin{align}\mathbb{P}\left( \left| u^\top\left( M_{\text{low}}-\frac{\alpha}{2}I_{d} \right)u \right| \geq \frac{\alpha}{24} \right)&\leq 2 \exp \left( -\frac{2\alpha^{2}}{24^{2}}\cdot \frac{1}{\frac{1}{4n^{2}}\sum_{i\in[n]}^{}\braket{ u , x_{i} } ^{4} } \right) \leq2\exp \left( -\frac{8n\alpha^{2}}{24^2 C^2d} \right)\end{align} $$