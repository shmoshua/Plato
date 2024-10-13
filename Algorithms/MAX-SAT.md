#Definition #Algorithms 

> [!definition]
> Let $x_{1},\dots,x_{n}$ be variables and $c_{1},\dots,c_{m}$ be clauses on the variables. Further, let $w:[m]\to \mathbb{R}$ be the ***weight*** function. 
> 1. The ***MAX-SAT problem*** aims to find: $$\alpha_{\text{OPT}}\in \underset{ \alpha \text{ assignment} }{ \arg\max }\sum_{j:c_{j}\text{ satisfied by }\alpha}^{}w_{j}$$
---
##### Properties
> [!lemma] Proposition 1
> Consider the following algorithm:
>    ```pseudo
>    \begin{algorithm} \caption{Random($I$)} 
>    \begin{algorithmic}
>    \For{$i\in[n]$}
>    \State $\alpha(x_{i})\gets \{ 0,1 \}$  uniformly at random.
\EndFor
>    \Return $\alpha$
>    \end{algorithmic}
>    \end{algorithm}
>    ```
> 
> Then, 
> 1. $\mathbb{P}(\alpha \text{ satisfies }c_{j})=1-2^{-\left| c_{j} \right|}$ for all $j\in[m]$.
> 2. $\text{Random}$ is a 1/2-[[Approximation Algorithm|approximation algorithm]] in expectation. 
> 3. By repeating $\text{Random}$ $n$ times and taking the maximum, 

> [!proof]-
> We have that:
> 1. $\alpha$ does not satisfy $c_{j}$ if and only if $\alpha$ gives false to all literals in $c_{j}$. This happens with probability $\frac{1}{2^\left| c_{j} \right|}$. This proves the statement.
> 2. For an assignment $\alpha$, let $S(\alpha):=\{ j\in[m]:\alpha \text{ satisfies }c_{j} \}$. Then, $$\mathbb{E}[w(S(\alpha))]=\sum_{j=1}^{m}w_{j}\cdot \mathbb{P}(\alpha \text{ satisfies }c_{j})=\sum_{j=1}^{m}w_{j}\left( 1-\frac{1}{2^{\left| c_{j} \right| }} \right)\geq \frac{1}{2}\sum_{j=1}^{m}w_{j}\geq \frac{1}{2}w(S(\alpha_{\text{OPT}})) $$
> 3. We have that: $$\begin{align}\mathbb{P}\left( w(S(\alpha))< \frac{49}{100}w_{\text{OPT}} \right)&=\prod_{k=1}^{n}\mathbb{P}\left( w(S(\alpha_{i}))< \frac{49}{100}w_{\text{OPT}} \right)\\&=\mathbb{P}\left( w(S(\alpha_{i}))< \frac{49}{100}w_{\text{OPT}} \right)^n \\&=\mathbb{P}\left( w(S(\alpha_{i}))< \frac{49}{100}W\right)^n \\&=\mathbb{P}\left(W- w(S(\alpha_{i}))> \frac{51}{100}W \right)^n\\&\leq  \left( \frac{50}{51} \right)^n\end{align}$$Therefore, if $n=233$, then we get that it is a $0.49$-approximation with $99\%$ probability.

---
> [!lemma] Theorem 2 (Linear Programming)
> Let $(y^{*},z^{*})$ be the optimal solution of the LP:$$\begin{align}\text{max}\quad&\sum_{j=1}^{m}w_{j}z_{j}\\\text{subject to}\quad &\sum_{i\in S_{j}^+}^{}y_{i}+\sum_{i\in S_{j}^-}^{}(1-y_{i})\geq z_{j}&&\forall j\in [m]\\&0\leq z_{j}\leq 1&&\forall j\in [m]\\&0\leq y_{i}\leq 1&&\forall i\in[n]\end{align}$$
>   ```pseudo
>    \begin{algorithm} \caption{LP\_Rounding($I,f:[0,1]\to[0,1]$)} 
>    \begin{algorithmic}
>    \State $(y^{*},z^{*})\gets$\Call{LP}{$I$}
>    \For{$i\in[n]$}
>    \State Choose $\alpha(x_{i})$ from $\{ 0,1 \}$ where $\mathbb{P}(\alpha(x_{i})=1)=f(y^{*}_{i})$.\EndFor
>    \Return $\alpha$
>    \end{algorithmic}
>    \end{algorithm}
>    ```
>    
>    
> We have that:
> 1. With $f=\text{id}$, $\mathbb{P}(\alpha \text{ satisfies }c_{j})\geq \left( 1-\left( 1-\frac{1}{k} \right)^k \right)z^{*}_{j}$
> 2. $\text{LP\_Rounding}(I,\text{id})$ is a $\left( 1-\frac{1}{e} \right)$-approximation algorithm in expectation.
> 3. $\max(\text{Random}(I),\text{LP\_Rounding}(I, \text{id}))$ is a $3/4$-approximation algorithm in expectation.
> 4. for $f:[0,1]\to[0,1]$ with $f(y)\in [1-4^{-y},4^{y-1}]$, $\text{LP\_Rounding}(I,f)$ is a $3/4$-approximation.

> [!proof]-
> We have that:
> 1. Notice that: $$\begin{align}\mathbb{P}(\alpha \text{ doesn't satisfy }c_{j})&=\prod_{i\in S^+_{j}}^{}(1-y_{i}^{*})\prod_{i\in S_{j}^-}^{}y^{*}_{i}\\&\leq \left(  \frac{\sum_{i\in S^+_{j}}^{}(1-y_{i}^{*})+\prod_{i\in S_{j}^-}^{}y^{*}_{i}}{k}\right)^k\\&\leq \left(  \frac{k-z^{*}_{j}}{k}\right)^k \end{align}$$Then, $$\mathbb{P}(\alpha \text{ satisfies }c_{j})\geq 1-\left( 1-\frac{z^{*}_{j}}{k} \right) ^k\geq \left( 1-\left( 1-\frac{1}{k} \right)^k \right) z^{*}_{j}$$where $f(t)=1-\left( 1-\frac{t}{k} \right)^k$ is a concave function as: $$f''(t)= \frac{d}{dt}\left( 1-\frac{t}{k} \right)^{k-1}=-\frac{k-1}{k}\left( 1-\frac{t}{k} \right)^{k-2} $$which is non-positive for $t\leq k$. 
> 2. We have: $$\mathbb{E}[w(S(\alpha))]\geq \sum_{j=1}^{m}w_{j}\left( 1-\frac{1}{k} \right) ^kz^{*}_{j}\geq \left( 1-\frac{1}{k} \right) ^kw_{\text{ILP}}\geq\left( 1-\frac{1}{e} \right) w_{\text{OPT}}$$
> 3. Let $X_{r}$ be the weight given from $\text{Random}$ and let $X_{\ell}$ be the weight given by $\text{LP\_Rounding}$. Then, $X:=\max\{ X_{r},X_{\ell} \}$. Notice that we have: $2 X\geq X_{r}+X_{\ell}$. Therefore, it suffices to show that $\mathbb{E}[X_{r}+X_{\ell}]\geq \frac{3}{2}w_{\text{OPT}}$. 
>    
>    Let $\mathcal{C}_{k}$ be the clauses with length $k$. Then, $$\mathbb{E}[X_{r}]=\sum_{k}^{}\sum_{C_{j}\in \mathcal{C_{k}}}^{}w_{j}\left( 1-\frac{1}{2^k} \right)\geq\sum_{k}^{}\sum_{C_{j}\in \mathcal{C_{k}}}^{}w_{j}\left( 1-\frac{1}{2^k} \right)z^{*}_{j} $$Similarly, $$\mathbb{E}[X_{\ell}]\geq\sum_{k}^{}\sum_{C_{j}\in \mathcal{C}_{k}}^{}w_{j}\left( 1- \left( 1-\frac{1}{k} \right) ^k\right) z^{*}_{j} $$Hence, $$\begin{align}\mathbb{E}[X_{r}+X_{\ell}]\geq \sum_{k}^{}\sum_{C_{j}\in \mathcal{C}_{k}}^{}w_{j}\underbrace{ \left( 2-\frac{1}{2^k}-\left( 1-\frac{1}{k} \right) ^k \right)  }_{ =: \xi_{k} } z^{*}_{j}\end{align}$$we claim that $\xi_{k}\geq \frac{3}{2}$ for all $k\geq 1$. 
>    1. for $k=1$, $\xi_{k}=3 /2$.
>    2. for $k=2$, $\xi_{k}=3 /2$.
>    3. for $k\geq 3$, $\xi_{k}\geq 1-\frac{1}{2^k}+\left( 1-\frac{1}{e} \right)=\frac{15}{8} - \frac{1}{e}\geq \frac{3}{2}$ as $\frac{1}{e}\leq\frac{3}{8}$.
>    
>    It follows that $$\mathbb{E}[X]=\frac{\mathbb{E}[X_{r}+X_{\ell}]}{2}\geq \frac{3}{4}\sum_{j\in[m]}^{}w_{j}z^{*}_{j}=\frac{3}{4}w_{\text{LP}}\geq \frac{3}{4}w_{\text{OPT}}$$
>  4. Let $X$ be the random variable about the weight of the output. We have: 
> 	1. **Claim 1:** $\mathbb{P}(\alpha \text{ satisfies }c_{j})\geq 1-4^{-z^{*}_{j}}$
> 	   $$\begin{align}\mathbb{P}(\alpha \text{ doesn't satisfy }c_{j})&=\prod_{i\in S_{j}^+}^{}(1-f(y^{*}_{i}))\prod_{i\in S_{j}^-}^{}f(y^{*}_{i})\\&\leq \prod_{i\in S_{j}^+}^{}4^{-y^{*}_{i}}\prod_{i\in S^-_{j}}^{}4^{y^{*}_{i}-1}\\&=4^{-\left( \sum_{i\in S_{j}^+}^{}y^{*}_{i}+\sum_{i\in S^-_{j}}(1-y^{*}_{i}) \right)}\\&\leq 4^{-z^{*}_{j}}\end{align}$$
> 	
> 	Therefore, $$\mathbb{E}[X]\geq \sum_{j=1}^{m}w_{j}(1-4^{-z^{*}_{j}})$$where $f(t)=(1-4^{-t})$ is a concave function as: $$f''(t)=\frac{d}{dt}(\ln 4\cdot e^{-t\ln 4})=-(\ln 4)^{2}4^{-t}\leq 0$$Hence, $\mathbb{E}[X]\geq \sum_{j=1}^{m}w_{j}(1-4^{-z^{*}_{j}})\geq \frac{3}{4}\sum_{j=1}^{m}w_{j}z^{*}_{j}\geq \frac{3}{4}w_{\text{OPT}}$.
>    
---
> [!lemma] Theorem 3 (Integrality Gap)
> We have:
> 1. $\text{IG}=3/4$. 

> [!proof]-
> Let out CNF be: $$(x_{1}\lor x_{2})\land (x_{1}\lor \neg x_{2})\land (\neg x_{1}\lor  x_{2})\land (\neg x_{1}\lor \neg x_{2})$$with weight $w=1$. Then, any assignment satisfies exactly 3 clauses and therefore, $w_{\text{OPT}}=\text{OPT}_{\text{ILP}}=3$. However, for LP, we have by setting $y_{i}= \frac{1}{2 }$ and $z_{j} = 1$, $w_{\text{LP}}\geq 4$. 
---
