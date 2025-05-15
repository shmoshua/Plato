#Series #AGAO 

#### Exercise 1. 
1. We have: $$\mathcal{E}^{*}(z)=\sup_{y}\left( z^\top y- \frac{1}{2}\|y\|^{2} \right) =\sup_{t\geq 0}\left( \sup_{y:\left\| y \right\| =t} z^\top y- \frac{1}{2 }t^{2} \right)=\sup_{t\geq 0}\left( -\frac{1}{2}t^{2}+t\|z\|_{*} \right) $$As $\|z\|_{*}\geq 0$ and we have a quadratic function with a negative leading coefficient, we have that the maximum is achieved when $t=\|z\|_{*}$. Hence, $$\mathcal{E}^{*}(z)=-\frac{1}{2}\|z\|_{*}^{2}+\|z\|^{2}_{*}=\frac{1}{2}\|z\|^{2}_{*}$$
2. We have: $$\mathcal{E}^{*}(z)=\sup_{y}\left( z^\top y-\|y\| \right) =\sup_{t\geq 0}\left( \sup_{y:\|y\|=t} z^\top y-t\right)=\sup_{t\geq 0}\left( -t+t\|z\|_{*} \right) =\sup_{t\geq 0}t(\|z\|_{*}-1) $$Therefore, $$\mathcal{E}^{*}(z)=\begin{cases}0&\text{if }\|z\|_{*}\leq 1\\ \infty&\text{otherwise}\end{cases}$$
3. Wlog we may assume that $z\geq 0$. Indeed, for any $z$ there exists $y^{*}$ s.t. $$\mathcal{E}^{*}(z)=z^\top y^{*}-\mathcal{E}(y^{*})=(-z)^\top (-y^{*})-\mathcal{E}(-y^{*})\leq \mathcal{E}^{*} (-z)$$Therefore, by symmetry, we have $\mathcal{E}^{*}(z)=\mathcal{E}^{*}(-z)$. Now consider $\mathcal{E}^{*}(z)=zy-\mathcal{E}(y)$ for $z\geq 0$. 
    1. Let $\left| y \right|< 1$. Then, $$\frac{d}{dy} \left( zy-\frac{y ^4}{4} \right)=z-y ^3=0 \implies zy-\frac{\left| y \right| ^4}{4}=\frac{3}{4}z^{4/3} $$however as $\left| y \right|<1$, we have that $z<1$.
    2. Let $\left| y \right|=1$. Then, $$zy-\frac{\left| y \right| ^4}{4}=\pm z -\frac{1}{4}$$and as $z\geq 0$, the maximum in this case is given by $z-\frac{1}{4}$.
    3. Let $\left| y \right|>1$. Then, by setting derivative to 0, $z=\left| y \right|^{1/2}$. Hence, $$zy-\frac{2}{3}\left| y \right| ^{3/2}+ \frac{5}{12}=z^3-\frac{3}{2}z^3+\frac{5}{12}=-\frac{1}{2}z^3+\frac{5}{12}$$However as $\left| y \right|>1$, we have that $z>1$. 
    
    Therefore, we have that: $$\mathcal{E}^{*}(z)=\begin{cases} \frac{3}{4}z^{4/3}&\text{if }\left| z \right| <1\\ \left| z \right| -\frac{1}{4}&\text{if }\left| z \right| =1\\-\frac{1}{2}\left| z \right| ^3+\frac{5}{12}&\text{if }\left| z \right| >1\end{cases}$$
---
#### Exercise 3.
1. We have that: $$\begin{aligned}M(x_{0}+\widehat{\delta})&=y_{0}-M\text{H}_{\widehat{\mathcal{E}}}(x_{0})^{-1}\nabla \widehat{\mathcal{E}}(x_{0})\\&=y_{0}-MM^{-1}\text{H}_{{\mathcal{E}}}(Mx_{0})^{-1}(M^\top)^{-1}M^\top\nabla {\mathcal{E}}(Mx_{0})\\&=y_{0}-\text{H}_{\mathcal{E}}(Mx_{0})^{-1}\nabla \mathcal{E}(Mx_{0})\\&=y_{0}-\text{H}_{\mathcal{E}}(y_{0})^{-1}\nabla \mathcal{E}(y_{0})\\&=y_{0}+\delta\end{aligned}$$
2. Let $\delta:= -\frac{1}{\beta}\nabla \mathcal{E}(y_{0})$ and $\widehat{\delta}:= -\frac{1}{\beta}\nabla \widehat{\mathcal{E}}(x_{0})$. Then, $$M(x_{0}+\widehat{\delta})=y_{0}-\frac{1}{\beta}M \nabla\widehat{\mathcal{E}}(x_{0})=y_{0}-\frac{1}{\beta}M M^\top\nabla{\mathcal{E}}(y_{0})=y_{0}+MM^\top  \delta$$Therefore it holds for all $\delta$ if $MM^\top = I$, however, not in general.

---

