#Series #Algorithms 

#### Problem 1
1. Firstly, note that: $$\frac{1}{n}\sum_{i\in[n]}^{}\braket{  x_{i},u}^{2}=\frac{1}{n }u^\top X^\top X u=u^\top u=\|u\|^2=1 $$Now, using Cauchy-Schwarz, we have for all $i\in[n]$ that: $$\braket{ x_{i} , u }^{2}\leq \braket{ x_{i} , u }\|x_{i}\|\underbrace{ \|u\| }_{ =1 }\leq C\sqrt{ d }\braket{ x_{i} , u } $$ Then, it follows that:$$\frac{1}{n}\sum_{i=1}^{n}\braket{ x_{i}, u } ^4\leq C^{2}d\left( \frac{1}{n}\sum_{i=1}^{n}\braket{ x_{i} , u } ^{2} \right) =C^{2}d$$

2. Notice that:$$u^\top M_{\text{low}}u=\frac{1}{2n}\sum_{i=1}^{n}b_{i}u^\top x_{i}x_{i}^\top u=\frac{1}{2n}\sum_{i=1}^{n} b_{i}\braket{  x_{i} ,u} ^{2}$$ As $\eta_{i}$ are independent, so are $b_{i}$. Further, we have that: $$ 0\leq \frac{1}{2n}b_{i}\braket{ x_{i} ,u}^{2}\leq  \frac{1}{2n}\braket{  x_{i},u }^{2}$$Now, by noting that: $\mathbb{E}[b_{i}\braket{ x_{i} , u } ^{2}]=\mathbb{E}[b_{i}]\braket{ x_{i} , u } ^{2}=\alpha \braket{ x_{i} , u }^{2}$, we have: $$\frac{1}{2n}\sum_{i=1}^{n}\mathbb{E}[b_{i}\braket{ x_{i} , u } ^{2}]=\frac{\alpha}{2n}\sum_{i=1}^{n}\braket{ x_{i} , u } ^{2}=\frac{\alpha}{2n}u^\top X^\top X u =u^\top \left( \frac{\alpha}{2}I_{d} \right) u$$Hence, by Hoeffding, $$\begin{align}\mathbb{P}\left( \left| u^\top\left( M_{\text{low}}-\frac{\alpha}{2}I_{d} \right)u \right| \geq \frac{\alpha}{24} \right)&=\mathbb{P}\left(\frac{1}{n} \left|  \sum_{i=1}^{n}(b_{i}-\mathbb{E}[b_{i}])\braket{ x_{i} , u } ^{2}\right| \geq \frac{\alpha}{12} \right)\\&\leq 2 \exp \left( -\frac{2\alpha^{2}}{24^{2}}\cdot \frac{1}{\frac{1}{4n^{2}}\sum_{i\in[n]}^{}\braket{ u , x_{i} } ^{4} } \right) \leq2\exp \left( -\frac{8n\alpha^{2}}{24^2 C^2d} \right)\end{align} $$This proves the statement.
3. For $A\in \text{Mat}_{d,d}(\mathbb{R})$ symmetric and $u,v\in S^{d-1}$. Then, there exists $u',v'\in \mathcal{N}_{1 / 4}$ with $\left\| u-u' \right\|\leq 1 / 4$ and $\left\| v-v' \right\|\leq 1 /4$. Therefore, $$\left| u^\top Av \right| =\left| u^\top A(v'+v-v') \right|\leq \left| u^\top Av' \right| +\frac{\left\| A^\top u \right\|}{4}  $$
   
	 we have that: $$\max_{u\in S}\left| u^\top Au \right| =\max_{u,v\in S}\left| u^\top Av \right| $$

	We have that: $$\begin{align}\left| u^\top Au \right| =\left| (u'+u-u')^\top A (u'+u-u') \right| &\leq \left| u'^\top Au' \right| +2\left| u'^\top A(u-u') \right| +\left| (u-u')^\top A (u-u') \right| \\&\leq \left| u'^\top A u' \right| +\frac{9}{16}\left\| A \right\|\end{align} $$

	$$\begin{align} \left| u'^\top A u' \right| &=\left| (u+u'-u)^\top A (u+u'-u) \right|\\&= \left|  u^\top A u-2(u-u')\right|  \end{align}$$
4. First, notice that $M_{\text{low}}-\frac{\alpha}{2}I_{d}$ is symmetric. Hence, by 3, $$\begin{align}\mathbb{P}\left( \exists u\in S^{d-1}: \left| u^\top\left( M_{\text{low}}-\frac{\alpha}{2}I_{d} \right) u \right| \geq \frac{\alpha}{6}\right)&=\mathbb{P}\left(\max_{u\in S^{d-1}} \left| u^\top\left( M_{\text{low}}-\frac{\alpha}{2}I_{d} \right) u \right| \geq \frac{\alpha}{6}\right)\\&\leq \mathbb{P}\left(\max_{u\in \mathcal{N}_{1 / 4}} \left| u^\top\left( M_{\text{low}}-\frac{\alpha}{2}I_{d} \right) u \right| \geq \frac{\alpha}{24}\right)\\&\leq 10^d  \cdot 2\exp \left( -\frac{2n\alpha^{2}}{24^{2}\cdot C^{2}d} \right) \end{align}$$

---
#### Problem 2
1. Let $\ell_{i}:=\mathbb{1}_{\{ \eta_{i}<-\varepsilon \}}$ and $h_{i}:=\mathbb{1}_{\{ \eta_{i}>\varepsilon \}}$. Then, $$\mathbb{P}\left( \left| \widehat{\beta} \right| >\varepsilon \right) =\mathbb{P}(\widehat{\beta}<-\varepsilon)+\mathbb{P}(\widehat{\beta}>\varepsilon)=\mathbb{P}\left( \sum_{i\in[n]}^{}\ell_{i}\geq n-\left\lceil \frac{n}{2}\right\rceil +1  \right)+\mathbb{P}\left( \sum_{i\in[n]}^{}h_{i}\geq \left\lceil \frac{n}{2}\right\rceil  \right) $$Notice that: $$\mathbb{E}[\ell_{i}]=\mathbb{P}(\eta_{i}<-\varepsilon)\leq \frac{1-\delta}{2},\quad \mathbb{E}[h_{i}]=\mathbb{P}(\eta_{i}>\varepsilon)\leq \frac{1-\delta}{2},\quad \forall i\in[n]$$Hence, $$\begin{align}\mathbb{P}\left( \left| \widehat{\beta} \right| >\varepsilon \right)&\leq \mathbb{P}\left( \sum_{i\in[n]}^{}(\ell_{i}-\mathbb{E}[\ell_{i}])\geq \frac{n}{2}-\frac{n(1-\delta)}{2} \right)+\mathbb{P}\left( \sum_{i\in[n]}^{}(h_{i}-\mathbb{E}[h_{i}])\geq \frac{n}{2}-\frac{n(1-\delta)}{2} \right)\\&\leq \mathbb{P}\left( \sum_{i\in[n]}^{}(\ell_{i}-\mathbb{E}[\ell_{i}])\geq \frac{n\delta}{2}\right)+\mathbb{P}\left( \sum_{i\in[n]}^{}(h_{i}-\mathbb{E}[h_{i}])\geq \frac{n\delta}{2}\right)\\&\leq 2\exp \left( -\frac{n\delta^{2}}{2} \right) \end{align} $$
2. Let $\eta_{i}\sim \text{Uniform}(\{ -1,+1 \})$ for all $i\in[n]$ independently. Then, for any odd $n$, we have that:
	1. $\eta_{i}$ and $-\eta_{i}$ have the same distribution.
	2. $\mathbb{P}(\left| \eta_{i} \right|\leq 1)=1\geq \alpha$ for any $\alpha\leq 1$. 
	
	However, as $n$ is odd, $\widehat{\beta}\in \{ -1,+1 \}$. This shows the statement.
3. Consider the following function: $$f:\mathbb{R}\to \mathbb{R},\quad m\mapsto \sum_{i=1}^{n}\left| y_{i}-m \right| $$Then, $$\nabla f(m)=-\sum_{i=1}^{m}\frac{y_{i}-m}{\left| y_{i}-m \right| }=-\sum_{i=1}^{m}\text{sgn}(y_{i}-m)$$Now, for the median, we have that $\nabla f(\text{Median}(y_{1},\dots,y_{n}))=0$. This shows the statement. 

---
