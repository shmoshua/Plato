#Series #AGAO 

#### Exercise 1. 
1. We have: $$\mathcal{E}^{*}(z)=\sup_{y}\left( z^\top y- \frac{1}{2}\|y\|^{2} \right) =\sup_{t\geq 0}\left( \sup_{y:\left\| y \right\| =t} z^\top y- \frac{1}{2 }t^{2} \right)=\sup_{t\geq 0}\left( -\frac{1}{2}t^{2}+t\|z\|_{*} \right) $$As $\|z\|_{*}\geq 0$ and we have a quadratic function with a negative leading coefficient, we have that the maximum is achieved when $t=\|z\|_{*}$. Hence, $$\mathcal{E}^{*}(z)=-\frac{1}{2}\|z\|_{*}^{2}+\|z\|^{2}_{*}=\frac{1}{2}\|z\|^{2}_{*}$$
2. We have: $$\mathcal{E}^{*}(z)=\sup_{y}\left( z^\top y-\|y\| \right) =\sup_{t\geq 0}\left( \sup_{y:\|y\|=t} z^\top y-t\right)=\sup_{t\geq 0}\left( -t+t\|z\|_{*} \right) =\sup_{t\geq 0}t(\|z\|_{*}-1) $$Therefore, $$\mathcal{E}^{*}(z)=\begin{cases}0&\text{if }\|z\|_{*}\leq 1\\ \infty&\text{otherwise}\end{cases}$$
3. Wlog we may assume that $z\geq 0$. Indeed, for any $z$ there exists $y^{*}$ s.t. $$\mathcal{E}^{*}(z)=z^\top y^{*}-\mathcal{E}(y^{*})=(-z)^\top (-y^{*})-\mathcal{E}(-y^{*})\leq \mathcal{E}^{*} (-z)$$Therefore, by symmetry, we have $\mathcal{E}^{*}(z)=\mathcal{E}^{*}(-z)$.
    1. Let $\left| y \right|< 1$. Then, the $$\frac{d}{dt} \frac{t^4}{4}=t^3=0 \implies $$
