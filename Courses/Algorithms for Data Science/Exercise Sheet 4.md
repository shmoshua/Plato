#Series  #Algorithms 

#### 1. Multiple-Spike Model Estimation
Let $U:= \widehat{X}-X^{*}$. We have that: $$0\leq \left\| X^{*}-Y \right\| ^2_{F}-\left\| \widehat{X}-Y \right\| ^2_{F}=\left\| W \right\| ^2_{F}-\left\| U-W \right\| ^{2}_{F}=2\braket{ U , W } -\left\| U \right\| ^{2}_{F}$$ Further, $\text{rk}(U)\leq \text{rk}(\widehat{X})+\text{rk}(X^{*})\leq 2r$. Hence, $$\left\| U \right\| _*\leq \sqrt{ 2r }\|U\|_{F}$$Therefore, by Hölder, $$\left\| U \right\| ^{2}_{F}\leq 2\braket{ U , W } \leq 2 \|U\|_{*}\|W\|\leq 2\sqrt{ 2r }\|U\|_{F}\|W\|$$Hence, $\|U\|^2_{F}\leq 8r\|W\|^{2}$. We can conclude by: $$\mathbb{E}\left[  \left\| \widehat{X}-X^{*} \right\| ^{2}_{F}\right]\leq 8r\underbrace{ \mathbb{E}[\left\| W \right\| ^{2}] }_{ \leq O(n) }\leq  O(rn)$$

---
#### 2. Closed-Form Optimal Solution for PCA

Let $a\in \mathbb{R}^n,b\in \mathbb{R}^d$. Then, $$\|a\|^{2}\|b\|^{2}-2\|Y\|\|a\|\|b\|+\|Y\|^{2}=(\|a\|\|b\|-\|Y\|)^{2}\geq 0$$Hence, $$\sigma_{1}^{2}=\|Y\|^{2}\geq 2\|Y\|\|a\|\|b\|-\|a\|^{2}\|b\|^{2}\geq 2\braket{ a , Yb } -\|a\|^{2}\|b\|^{2}=2a^\top Yb-\|a\|^{2}\|b\|^{2}$$Therefore, $$\left\| Y -ab^\top\right\|^2_{F}=\text{tr}(YY^\top)-2\text{tr}(Yba^\top)+\text{tr}(ab^\top b a^\top)=\left\| Y \right\| ^{2}_{F}-2a^\top Yb+\|a\|^{2}\|b\|^{2}\geq \|Y\|^{2}_{F}-\sigma^{2}_{1} $$


Now, let $Y:= U\Sigma V^\top=\sum_{i=1}^{r}\sigma_{i}u_{i}v_{i}^\top$ be the SVD of $Y$. Then, $$\left\| Y-\sigma_{1} u_{1}v_{1}^\top \right\|^2_{F}=\left\| \sum_{i=2}^{r}\sigma_{i}u_{i}v_{i}^\top \right\| ^2_{F}=\text{tr}\left( \sum_{i,j=2}^{r}\sigma_{i}\sigma_{j}u_{i}v_{i}^\top v_{j}u_{j}^\top \right) =\text{tr}\left( \sum_{i=2}^{r}\sigma_{i}^{2} u_{i}u_{i}^\top \right) =\sum_{i=2}^{r}\sigma_{i}^{2} $$Hence, $\left\| Y-\sigma_{1} u_{1}v_{1}^\top \right\|^{2}_{F}=\left\| Y \right\|^{2}_{F}-\sigma^{2}_{1}$. This concludes the proof. 






---
#### 3. Matrix Hölder for the Spectral and Frobenius Norm
Let $Y=U\Sigma V^\top=\sum_{i=1}^{r}\sigma_{i} u_{i}v_{i}^\top$ be the SVD of $Y$. Then, we have that: $$\braket{ X , Y } =\text{tr}(XY^\top)=\text{tr}\left( \sum_{i=1}^{r}\sigma_{i}Xv_{i}u_{i}^\top \right)=\sum_{i=1}^{r}\sigma_{i}\text{tr}(X v_{i}u_{i}^\top)=\sum_{i=1}^{r}\sigma_{i}\cdot u_{i}^\top X v_{i} $$
Now, $u_{i}^\top X v_{i}\leq \left\| u_{i} \right\|\left\| Xv_{i} \right\|\leq \left\| X \right\|\left\| v_{i} \right\|=\left\| X \right\|$ as $u_{i},v_{i}$ are unit vectors.  Hence, we have that: $$\braket{ X , Y } \leq \left\| X \right\| \sum_{i=1}^r \sigma_{i}=\left\| X \right\| \cdot \left\| Y \right\| _{*}$$

---
