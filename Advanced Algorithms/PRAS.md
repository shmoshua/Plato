#Definition #Algorithms 

> [!definition]
> For a given cost metric $c$ and an optimal solution $\text{OPT}$ and a parameter $\varepsilon$, a ***polynomial randomized approximation scheme (PRAS)*** for a minimization problem is a Monte Carlo algorithm $\mathcal{A}_{\varepsilon}$ s.t. for all input instance $I$, 
> 1. $P(\left| c(\mathcal{A}_{\varepsilon}(I))-c(\text{OPT}(I)) \right|\geq \varepsilon \cdot c(\text{OPT}(I)))\leq \frac{1}{3}$
> 2. $\mathcal{A}_{\varepsilon}$ runs in $\text{poly}(\left| I \right|)$ time.

^fecdc3

---
##### Properties
> [!lemma] Proposition 1
> Let $\mathcal{A}_{\varepsilon}$ be a PRAS. Let $X:= c(\mathcal{A}_{\varepsilon}(I))$ be the random variable of the output and $x_{1},\dots,x_{k}$ be $k$ instances of $X$. Then, 
> 1. for the median $x_{\text{med}}$ of $x_{1},\dots,x_{k}$, $$P(x_{\text{med}}>(1+\varepsilon)\cdot c( \text{OPT}(I) ))<e^{-k / 36}$$

^7bca5c

> [!proof]-
> We have that: $$\begin{align}P(x_{\text{med}}>(1+\varepsilon)\cdot c( \text{OPT}(I) ))&\leq P(\text{Bin}(k,1 / 3 )\geq k / 2)\leq e^{-(\delta^{2})k/9}=e^{-k / 36}\end{align}$$

^9346bc



---
##### Examples
> [!h] Example 1 (Sampling)
> Let $S$ be a set and $T\subseteq S$. We aim to find $\left| T \right|/\left| S \right|$. Then, 
>    ```pseudo
>    \begin{algorithm} \caption{$\mathcal{A}_{\varepsilon}(S)$} 
>    \begin{algorithmic}
>    \State $c\gets 0$
>    \For{$i\in[m]$}
>    \State Sample $x_{i}$ from $S$ uniformly randomly
>    \If{$x_{i}\in T$}
>    \State $c\gets c+1$
>    \EndIf
>    \EndFor
>    \Return $c /m$
>    \end{algorithmic}
>    \end{algorithm}
>    ```
> Then,
> 1. for $m:=\Theta\left( \frac{\left| S \right|}{\left| T \right|}\varepsilon^{-2} \log(1/\delta)\right)$ samples, $\mathbb{P}\left( \left| \mathcal{A}_{\varepsilon}(S)-\frac{\left| T \right|}{\left| S \right|} \right|\geq\varepsilon \frac{\left| T \right|}{\left| S \right|}\right)\leq\delta$.
> 

^858f88

> [!proof]-
> We have that: 
> 1. Let $X$ denote the number of elements in $T$ from the $m$ samples. Then, $$\mathbb{E}[X]=m\cdot \mathbb{P}(x_{i}\in T)=m\cdot \frac{\left| T \right|}{\left| S \right| } $$Therefore, by Chernoff bounds, $$\begin{align}\mathbb{P}\left(   \left|  \frac{X}{m} -\frac{\left| T \right| }{\left| S \right|} \right|\geq \varepsilon \frac{\left| T \right| }{\left| S \right| } \right)&=\mathbb{P}\left( \left| X-\mathbb{E}[X] \right| \geq \varepsilon \mathbb{E}[X]\right)\\&\leq 2\exp \left( -\frac{\varepsilon^{2}m}{3} \cdot \frac{\left| T \right|}{\left| S \right| }\right) \end{align}$$We then get that: for $m=\Theta\left( \frac{\left| S \right|}{\left| T \right|}\varepsilon^{-2} \log(1/\delta)\right)$, the probability is bounded by $\delta$.
> 2. The probability that we sample an element from $T$ is $\left| T \right| / \left| S \right|$. Therefore, by geometric distribution, the expected number of trials we need is: $\frac{\left| S \right| }{\left| T \right| }$. Hence, if we sample only $O\left( \frac{\left| S \right|}{\left| T \right|} \right)$ we may never sample an element from $T$. 

^bf590a

