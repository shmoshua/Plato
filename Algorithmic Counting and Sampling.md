#Roadmap 

##### Spectral Methods, Conductance and Canonical Paths

> [!lemma] Lemma 1.4
> Let $\mu,\nu$ be two distributions on $\Omega$. Then, for $f:= d\nu / d\mu$, we have that: $$\left\| \nu-\mu \right\| _{\text{TV}}^{2}\leq \frac{1}{4}\text{Var}_{\mu}(f)$$

> [!proof]-
> We have that: 
> $$\begin{aligned}\left\| \nu-\mu \right\|_{\text{TV}}&=\frac{1}{2}\sum_{x}\mu(x)\left| f(x)-1 \right|\leq \frac{1}{2}\sqrt{ \sum_{x} \mu(x)\left( f(x)-1 \right) ^{2} } \sqrt{ \sum_{x}\mu(x) }=\frac{1}{2}\sqrt{ \text{Var}_{\mu}(f) } \end{aligned}$$as $\mathbb{E}_{\mu}[f]=\sum_{x}^{}\mu(x)f(x)=\sum_{x}\nu(x)=1$.

We have that the Dirichlet form is given by: $$\begin{aligned}\mathcal{E}_{P}(f,g):=\braket{ f , (I-P)g } _{\mu}
&=\sum_{x}\mu(x)f(x)(g(x)-(Pg)(x))\\
&=\sum_{x,y}\mu(x)P(x,y)(f(x)g(x)-f(x)g(y))\end{aligned}$$Similarly, $$\mathcal{E}_{P}(f,g)=\sum_{y,x}\mu(x)P(x,y)(f(y)g(y)-f(y)g(x))$$Hence, $$\mathcal{E}_{P}(f,g)=\frac{1}{2}\sum_{x,y}\mu(x)P(x,y)(f(x)-f(y))(g(x)-g(y))$$

We have that: $$\text{Var}_{\mu}(f)=\braket{ f , f } _{\mu}-\braket{ f , 1 } ^{2}_{\mu}=\sum_{x,y}\mu(x)\mu(y)(f(x)^{2}-f(x)f(y))=\frac{1}{2}\sum_{x,y}^{}\mu(x)\mu(y)(f(x)-f(y))^{2}$$