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
2. $t$-distribution
	$$f(x)=\frac{\Gamma\left( \frac{m+1}{2} \right)}{\sqrt{ m\pi }\Gamma\left( \frac{m}{2} \right)}\left( 1+\frac{x^2}{m} \right)^{-(m+1)/2}$$