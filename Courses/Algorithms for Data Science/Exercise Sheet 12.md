#Series #Algorithms 

#### 1. The Median as a Robust Mean Estimator
We firs 
Let $S\subseteq[n]$ be the set that are not corrupted, i.e. $S:=\{ i\in[n] :Z_{i}=Y_{i}\}$. Then, $\left| S \right|\geq (1-\varepsilon) n$. Then, $\widehat{\mu}\leq$

Let $X_{i}$ be the indicator variable denoting if $Y_{i}-\mu ^{*}>C\varepsilon$. Then, $\mathbb{E}[X_{i}]=\mathbb{P}(Y_{i}-\mu ^{*}>C\varepsilon)\leq \frac{1}{2}-2\varepsilon$.

1. We have that $\mu_{\text{high}}\geq \mu ^{*}+C\varepsilon$ if and only if $\frac{1}{n}\sum_{i}^{}X_{i}\geq \frac{1}{2}-\varepsilon$. $$\mathbb{P}\left( \frac{1}{n}\sum_{i}^{}X_{i}\geq \frac{1}{2}-\varepsilon\right)\leq \mathbb{P}\left( \frac{1}{n}\sum_{i}^{}X_{i}\geq \mathbb{E}[X_{1}]+\varepsilon\right)\leq \exp \left( -2n\varepsilon^{2} \right) $$

We first show it for 
Let $C$ be a constant and $0<\varepsilon< 1 / C$. We have that $\left| \widehat{\mu}-\mu ^{*} \right|> C\varepsilon$ implies that $\left| \mu_{\text{low}}-\mu ^{*} \right|> C\varepsilon$ or $\left| \mu_{\text{high}}-\mu ^{*} \right|> C\varepsilon$ as $\mu_{\text{low}}\leq \widehat{\mu}\leq \mu_{\text{high}}$. 

Now, we have that: 
$$\mathbb{P}(\mu ^{*}<\mu_{\text{low}})=$$

Then,

 $$\mathbb{P}(\left| \mu_{\text{low}}-\mu ^{*} \right|> C\varepsilon)=\mathbb{P}(\exists S\in {\choose })$$