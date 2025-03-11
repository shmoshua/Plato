#Series  #Algorithms 

#### 1. Multiple-Spike Model Estimation
Let $U:= \widehat{X}-X^{*}$. We have that: $$0\leq \left\| X^{*}-Y \right\| ^2_{F}-\left\| \widehat{X}-Y \right\| ^2_{F}=\left\| W \right\| ^2_{F}-\left\| U-W \right\| ^{2}_{F}=2\braket{ U , W } -\left\| U \right\| ^{2}_{F}$$ Further, $\text{rk}(U)\leq \text{rk}(\widehat{X})+\text{rk}(X^{*})\leq 2r$. Hence, $$\left\| U \right\| _*\leq \sqrt{ 2r }\|U\|_{F}$$Therefore, by Hölder, $$\left\| U \right\| ^{2}_{F}\leq 2\braket{ U , W } \leq 2 \|U\|_{*}\|W\|\leq 2\sqrt{ 2r }\|U\|_{F}\|W\|$$Hence, $\|U\|^2_{F}\leq 8r\|W\|^{2}$. We can conclude by: $$\mathbb{E}\left[  \left\| \widehat{X}-X^{*} \right\| ^{2}_{F}\right]\leq 8r\underbrace{ \mathbb{E}[\left\| W \right\| ^{2}] }_{ \leq O(n) }\leq  O(rn)$$

---
#### 2. Closed-Form Optimal Solution for PCA
Let $Y:= U\Sigma V^\top$ be the SVD of $Y$ where $U\in \mathbb{R}^{n,n}$ and $V\in \mathbb{R}^{d,d}$ are orthogonal. Then, $U,V$ are invertible and: $$\min_{a\in \mathbb{R}^n,b\in \mathbb{R}^d}\left\| Y-ab^\top \right\| ^2_{F}=\min_{a\in \mathbb{R}^n,b\in \mathbb{R}^d}\left\| Y-Uab^\top V^\top \right\| ^2_{F}=\min_{a\in \mathbb{R}^n,b\in \mathbb{R}^d}\left\| \Sigma-ab^\top  \right\| ^2_{F}$$where the last equality holds from the orthogonality of $U,V$. Indeed, for any matrix $A$ and orthogonal $U$ with appropriate dimensions: $$\left\| UA \right\| ^2_{F}=\text{tr}(UAA^\top U^\top)=\text{tr}(U^\top U AA^\top) = \text{tr}(AA^\top)=\left\| A \right\| ^2_{F}$$Similarly, $$\left\| AU \right\| ^{2}_{F}=\text{tr}(AUU^\top A^\top)=\text{tr}(AA^\top)=\left\| A \right\| ^2_{F}$$

Now, we have that: $$\left\| \Sigma-ab^\top \right\| ^2_{F}=\text{tr}((\Sigma-ab^\top)^\top(\Sigma-ab^\top))=\left\| \Sigma \right\| ^2_{F}-2a^\top \Sigma b+\|a\|^{2}\|b\|^{2}$$Notice that: $$2a^\top\Sigma b-\|a\|^{2}\|b\|^{2}\leq2\sigma_{1}\sum_{i\in[r]}^{}a_{i}b_{i}-\left( \sum_{i\in[r]}^{}a_{i}^{2} \right) \left( \sum_{i\in[r]}^{}b_{i}^{2} \right)  $$



We have that for $f:\mathbb{R}^{n}\times \mathbb{R}^d\to \mathbb{R},(a,b)\mapsto \left\| \Sigma-ab^\top \right\| ^{2}_{F}$, $$\nabla f(a,b)=\left(2\|b\|^{2}a-2\Sigma b,2\|a\|^{2} b -2\Sigma^\top a\right)$$Let $f$ attain its minimum at $a^{*},b^{*}$. Then, we have that: $$\left\| b^{*} \right\| ^{2}a^{*}=\Sigma b^{*},\quad \|a^{*}\|^{2}b^{*}=\Sigma^\top a^{*}$$Hence, $(b^{*})^\top \Sigma^\top a^{*}=\|a^{*}\|^2\|b^{*}\|^2$ and $$\left\| Y-a^{*}b^{*} \right\|^{2}_{F}=\|Y\|^2_{F}-\|a^{*}\|^2\|b^{*}\|^2$$Therefore, we are left to maximize $a^\top \Sigma b$. We have that: $$a^\top \Sigma b=\sum_{i\in[r]}^{}\sigma_{i}a_{i}b_{i}\leq \sigma_{1} a^\top b$$
