#Series #Algorithms 

#### Problem 1
1. Using Cauchy-Schwarz, $$\frac{1}{n}\sum_{i=1}^{n}\braket{ x_{i} , u } ^4\leq \frac{1}{n}\sum_{i=1}^{n}\|x_{i}\|^4\underbrace{ \|u\| ^4}_{ =1 }\leq\frac{1}{n}\sum_{i=1}^{n}C^{4}d^{2}=C^4d^{2}$$$$\frac{1}{n}\sum_{i=1}^{n}\braket{ x_{i} , u } ^4\leq \frac{1}{n}\left( \sum_{i=1}^{n}\braket{ x_{i} , u } ^2 \right)^2\leq \frac{1}{n}\left( \sum_{i=1}^{n}\|x_{i}\|^2 \right)^2=\frac{1}{n}\text{tr}(XX^\top)^2=\frac{1}{n}\text{tr}(X^\top X)^{2}=nd^{2}$$It suffices to show that $nd^{2}\leq C^{2}d$. We have: $$nd=\sum_{i=1}^{n}\left\| x_{i} \right\| ^{2}\leq nC^{2}d$$
   
   $nd^{2}\leq \|x_{i}\|^2$. 

We have: $$\sum_{i=1}^{n}\left\| x_{i} \right\| ^{2}=nd$$. Hence, $d\leq\max\|x_{i}\|^2\leq C^{2}d$. $$\sum_{i=1}^{n}\|x_{i}\|^4\leq$$ $$\frac{1}{n}\sum_{i=1}^{n}\braket{ x_{i} , u } ^4\leq \frac{1}{n}\sum_{i=1}^{n}\|x_{i}\|^2\braket{ x_{i} , u } ^{2}\leq \frac{C^{2}d}{n}\sum_{i=1}^{n}\braket{ x_{i} , u } ^{2}$$$$\sum_{i=1}^{n}\left\| x_{i} \right\| ^4=\text{tr}(XX^\top)$$
 $$\sum_{i=1}^{n}\braket{ x_{i} , u } ^2=\|Xu\|^2\leq \left\| X \right\| ^{2}$$

1. Notice that:$$u^\top M_{\text{low}}u=\sum_{j,k=1}^{d}\sum_{i=1}^{n} \frac{1}{2n}b_{i}u_{j}u_{k}x_{ij}x_{ik}=\frac{1}{2n}\sum_{i=1}^{n} b_{i}\braket{ u , x_{i} } ^{2}$