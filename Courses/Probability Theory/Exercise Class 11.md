#ExerciseClass #ProbabilityTheory 

### 1. Estimation

1. Statistics and Probability.
2. Estimator, Bias, MSE

Let $X_{1},\dots,X_{n}\sim \text{Poi}(\theta)$ i.i.d. Show that $T:=(X_{1}+\dots+X_{n}) / n$ is an unbiased estimator of $\theta$. What is $\text{MSE}(T)$?

$$\mathbb{E}[T]=\mathbb{E}[X_{1}]=\theta$$ and $$\text{MSE}(T)=\text{Var}(T)=\frac{1}{n}\theta$$

1. Confidence interval.

---
#### 2. Distributions
1. Chi-Squared distribution
	$$f(y)=\frac{1}{2^{m/2}\Gamma\left( \frac{m}{2} \right)}y^{m/2-1}e^{-y/2},\quad y\geq 0$$
	$\mathbb{E}[X]=\nu,\text{Var}(X)=2\nu$
	2. Using Chebyshev find a lower bound for: $$\mathbb{P}\left[ \left| \frac{Y}{\nu}-1 \right| \leq \frac{3}{4} \right] $$What is the concrete value for $\nu=12$?
	3. Using CLT, what is the approximation of the above value?
2. $t$-distribution
	$$f(x)=\frac{\Gamma\left( \frac{m+1}{2} \right)}{\sqrt{ m\pi }\Gamma\left( \frac{m}{2} \right)}\left( 1+\frac{x^2}{m} \right)^{-(m+1)/2}$$

---
#### 3. Confidence Intervals
Let $X_{1},\dots,X_{n}\sim \mathcal{N}(\mu,\sigma^{2})$ iid.
1. CI of $\mu$ when $\sigma^{2}$ is known. $$\left[ \overline{X}-\Phi ^{-1}\left( 1-\frac{\alpha}{2} \right)\sqrt{ \frac{\sigma^{2}}{n} } ,\overline{X}+\Phi ^{-1}\left( 1-\frac{\alpha}{2} \right)\sqrt{ \frac{\sigma^{2}}{n} } \right]$$is a $(1-\alpha)$ confidence interval for $\mu$.
2. CI of $\mu$ when $\sigma^{2}$ is unknown. $$\left[ \overline{X}-c\left( n-1, \frac{\alpha}{2} \right)\sqrt{ \frac{S^{2}}{n} } ,\overline{X}+c\left( n-1, \frac{\alpha}{2} \right)\sqrt{ \frac{S^{2}}{n} } \right]$$
3. CI of $\sigma^{2}$ when $\mu$ is known. $$\left[ \frac{n\widehat{\sigma}^{2}}{G^{-1}_{n}\left( 1-\frac{\alpha}{2} \right)} ,\frac{n\widehat{\sigma}^{2}}{G^{-1}_{n}\left( \frac{\alpha}{2} \right)} \right] $$

---
#### 4. Approximate Confidence Intervals
Let $X_{1},\dots,X_{n}\sim \text{Poi}(\lambda)$ iid. Then $X:=\sum_{i}^{}X_{i}\sim \text{Poi}(n\lambda)$. 

---
Laura throws a dart on $D:=\{ (x,y)\in \mathbb{R}^{2}:x^{2}+y^{2}\leq 1 \}$. Let $\theta$ be a model family s.t. the hitting point $(X,Y)$ has the distribution: $$f_{\theta}(x,y):=c_{\theta}(x^{2}+y^{2})^{\theta / 2}$$
1. Show that $\theta>-2$ and $c_{\theta}=\frac{\theta+2}{2\pi}$
2. If Laura throws $n$ times and they are all indpeendent, find the MLE estimator.