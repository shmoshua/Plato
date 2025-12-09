1. $f(x_{1},x_{2}) = \sigma(\omega_{2}x_{2} + \omega_{1}x_{1}+\omega_{0})$
2. We have that: $z_{1}=0.4$, $z_{2}=0.4$, $h=1.3$, $p \approx 0.79$
3. We have: $$\mathcal{L}(1,p)=- \log p=-\log \frac{1}{1+\exp(-1.3)}\approx 0.24$$
4. We have: $$\begin{aligned}\frac{\partial \mathcal{L}}{\partial h}=\frac{ \partial \mathcal{L} }{ \partial p }\frac{ \partial p }{ \partial h }  &=-\left( \frac{y}{p}-\frac{1-y}{1-p} \right)\cdot p(1-p) \\&=-(y(1-p)-(1-y)p)\\&=p-y\end{aligned}$$Therefore, $$\frac{ \partial \mathcal{L} }{ \partial \omega_{0} } =\frac{ \partial \mathcal{L} }{ \partial h } \frac{ \partial h }{ \partial \omega_{0} } =p-y,\quad \frac{ \partial \mathcal{L} }{ \partial \omega_{i} } =\frac{ \partial \mathcal{L} }{ \partial h } \frac{ \partial h }{ \partial \omega_{i} } =x_{i}(p-y)$$for $i\in\{ 1,2 \}$. 
---
Let $\omega(\mathbf{t})_{n}:=\exp(\text{score}_{\theta}(\braket{ t_{n-1} , t_{n} },\mathbf{ w}))$ for all $\mathbf{ t}\in \mathcal{T}^N$ and $n\in[N]$. Then, the backward algorithm computes: $$\bigoplus _{\mathbf{t}\in \mathcal{T}^N} \bigotimes_{n\in [N]}\braket{ \omega(\mathbf{t})_{n}, -\omega(\mathbf{t})_{n}\log \omega(\mathbf{t})_{n}}$$Hence, it suffices to show that this results in the unnormalized entropy. 

We first show that for any $\{ x_{i},y_{i} \}_{i}\subseteq \mathbb{R}$,
$$\bigotimes_{i\in[n]}\braket{ x_{i} , y_{i} } =\left\langle \prod_{ i\in[n]}^{} x_{i},\sum_{i\in[n]} y_{i}\prod_{j \in[n]:j \ne i}^{}x_{j}\right\rangle $$We show this via induction over $n$. For $n=1$, it is clear. Now, $$\begin{aligned}\bigotimes_{i\in[n]}\braket{ x_{i} , y_{i} } &=\left( \bigotimes_{i\in[n-1]}\braket{ x_{i} , y_{i} }  \right) \otimes  \braket{ x_{n} , y_{n} }\\&= \left\langle \prod_{ i\in[n-1]}^{} x_{i},\sum_{i\in[n-1]} y_{i}\prod_{j\in[n-1]:j \ne i}^{}x_{j}\right\rangle \otimes  \braket{ x_{n} , y_{n} }\\&=\left\langle \prod_{ i\in[n]}^{} x_{i},y_{n}\prod_{i\in[n-1]}x_{i}+\sum_{i\in[n-1]} y_{i}\prod_{j\in[n]:j \ne i}^{}x_{j}\right\rangle \\&=\left\langle \prod_{ i\in[n]}^{} x_{i},\sum_{i\in[n]} y_{i}\prod_{j\in[n]:j \ne i}^{}x_{j}\right\rangle \end{aligned}$$
Now, using this we have that: 
$$
\begin{aligned}
&\bigoplus _{\mathbf{t}\in \mathcal{T}^N} \bigotimes_{n\in [N]}\braket{ \omega(\mathbf{t})_{n}, -\omega(\mathbf{t})_{n}\log \omega(\mathbf{t})_{n}} \\=\quad &\bigoplus _{\mathbf{t}\in \mathcal{T}^N} \left\langle \prod_{n\in[N]}^{}\omega(\mathbf{t})_{n},-\sum_{n \in[N]}^{}\omega(\mathbf{t})_{n}\log \omega(\mathbf{t})_{n} \prod_{ m \in [N]: m \ne n} \omega(\mathbf{t})_{m}\right\rangle
\\=\quad &\bigoplus _{\mathbf{t}\in \mathcal{T}^N} \left\langle \prod_{n\in[N]}^{}\omega(\mathbf{t})_{n},-\sum_{n \in[N]}^{}\log \omega(\mathbf{t})_{n} \prod_{ m \in [N]} \omega(\mathbf{t})_{m}\right\rangle
\\=\quad &\bigoplus _{\mathbf{t}\in \mathcal{T}^N} \left\langle \prod_{n\in[N]}^{}\omega(\mathbf{t})_{n},-\left( \prod_{ m \in [N]} \omega(\mathbf{t})_{m} \right)\sum_{n \in[N]}^{}\log \omega(\mathbf{t})_{n} \right\rangle
\\=\quad &\bigoplus _{\mathbf{t}\in \mathcal{T}^N} \left\langle \exp(\text{score}_{\theta}(\mathbf{t},\mathbf{w})),-\exp(\text{score}_{\theta}(\mathbf{t},\mathbf{w}))\text{score}_{\theta}(\mathbf{ t},\mathbf{ w}) \right\rangle
\\=\quad &\left\langle \sum_{\mathbf{t}\in \mathcal{T}^N} ^{}\exp(\text{score}_{\theta}(\mathbf{t},\mathbf{w})),\underbrace{ -\sum_{\mathbf{t}\in \mathcal{T}^N} ^{}\exp(\text{score}_{\theta}(\mathbf{t},\mathbf{w}))\text{score}_{\theta}(\mathbf{ t},\mathbf{ w})  }_{ = \text{H}_{\text{U}}(\text{T}_{\mathbf{ w}}) }\right\rangle
\end{aligned}
$$
where: $$\prod_{ n \in [N]} \omega(\mathbf{t})_{n} = \prod_{ n \in [N]} \exp(\text{score}_{\theta}(\braket{ t_{n-1} , t_{n} },\mathbf{ w})) = \exp\left( \sum_{n\in[N]}^{}\text{score}_{\theta}(\braket{ t_{n-1} , t_{n} },\mathbf{ w}) \right)=\exp(\text{score}_{\theta}(\mathbf{t},\mathbf{w}))$$and $$\sum_{n\in[N]}^{}\log \omega(\mathbf{t})_{n}=\sum_{n\in[N]}^{}\text{score}_{\theta}(\braket{ t_{n-1} ,t_{n}  },\mathbf{ w} )=\text{score}_{\theta}(\mathbf{ t},\mathbf{ w})$$
This proves the claim. 

---
We have that: $$\begin{aligned}\text{H}(\text{T}_{\textbf{w}}) &= -\sum_{\mathbf{t}\in \mathcal{T}^N}^{} p(\mathbf{t}|\mathbf{w})\log p(\mathbf{t}|\mathbf{w})\\&=-\sum_{\mathbf{t}\in \mathcal{T}^N}^{} \frac{\exp \text{score}_{\mathbf{\theta}}(\mathbf{t},\mathbf{w})}{Z(\mathbf{w})}\log \frac{\exp \text{score}_{\mathbf{\theta}}(\mathbf{t},\mathbf{w})}{Z(\mathbf{w})}\\&=-\sum_{\mathbf{t}\in \mathcal{T}^N}^{} \frac{\exp \text{score}_{\mathbf{\theta}}(\mathbf{t},\mathbf{w})}{Z(\mathbf{w})}(\text{score}_{\mathbf{\theta}}(\mathbf{t},\mathbf{w}) - \log Z(\mathbf{w}))\\&=Z(\mathbf{w})^{-1}\text{H}_{\text{U}}(\text{T}_{\mathbf{w}})+\log Z(\mathbf{w}) \underbrace{ \frac{\sum_{\mathbf{t}\in \mathcal{T}^N}^{} \exp \text{score}_{\theta}(\mathbf{ t}, \mathbf{ w})}{Z(\mathbf{ w})} }_{ = 1 }\\&=Z(\mathbf{w})^{-1}\text{H}_{\text{U}}(\text{T}_{\mathbf{w}})+\log Z(\mathbf{w}) \end{aligned}$$

---
##### Problem 2
1. For any $n$, let $t^{*}_{n}\in \mathcal{T},s^{*}_{n}\in A$ s.t. $\braket{ \braket{ n , t^{*}_{n} } , s^{*}_{n} }$ is the first element popped from $\texttt{queue}$ with $n$. Then, we claim that for any $n$: $$\exists \mathbf{ t}_{1:n-1}\in \mathcal{T}^{n-1}, \quad  \text{score}(\mathbf{ t}_{1:n-1}, t^{*}_{n},\mathbf{ w})=s^{*}_{n}=\max_{\mathbf{t}\in \mathcal{T}^n }\text{ score}(\mathbf{ t},\mathbf{ w})$$
   We show this by induction over $n$. 
	- Let $n=1$. Before the first iteration of the while loop, we have $\mathtt{queue}=(\braket{ \braket{ 0 , \text{BOT} } , \mathbf{ 1} })$. We pop $\braket{ \braket{ 0 , \text{BOT} } , \mathbf{ 1} }$. Then for all $t'\in \mathcal{T}$, $$\braket{ \braket{ 1 , t' } , \text{score}(t',\text{BOT},\mathbf{ w}) + 0}=\braket{ \braket{ 1 , t' } , \text{score}(t',\text{BOT},\mathbf{ w})}$$is added to the priority queue. Hence, after the first iteration, $\texttt{queue}=(\braket{ \braket{ 1 , t' } , \text{score}(t',\text{BOT},\mathbf{ w})})_{t'\in \mathcal{T}}$. Hence, we have that $$\text{score}(t^{*}_{1},\mathbf{ w})=s^{*}_{1}=\max_{t'\in \mathcal{T}} \text{score}(t',\mathbf{ w})$$
	- Now let $n \ge 2$. Then, by induction hypothesis, there exists $\mathbf{t}_{1:n-1}\in \mathcal{T}^{n-1}$ ending in $t^{*}_{n-1}$ s.t. $$\text{score}(\mathbf{t}_{1:n-1},\mathbf{ w})=s^{*}_{n-1}=\max_{\mathbf{ t}\in \mathcal{T}^{n-1}}\text{score}(\mathbf{ t}_{1:n-1}, \mathbf{ w})$$
	  Therefore, if 
	  
	  Now the first equality is simple: by the algorithm we have that: $$s^{*}_{n}=\text{score}(t,t^{*}_{n},\mathbf{ w})+\gamma[n-1,t]$$for some $t\in \mathcal{T}$.

Let $\texttt{popped}_{j},\texttt{queue}_{j}$ denote $\texttt{popped}$ and $\texttt{queue}$ after the $j$-th iteration respectively. We first prove the following lemma. 

We first prove the following: for all $j$, $$\gamma[n,t]=1_{n\ne 0}\cdot \max_{\mathbf{t}_{1:n-1}\in \mathcal{T}^{n-1}}\text{score}(\mathbf{t}_{1:n-1},t,\mathbf{w}),\quad \forall\braket{ n, t }\in \texttt{popped}_{j}$$
Firstly, notice that for each $\braket{ n , t }$, $\gamma[n,t]$ is updated once during the whole algorithm. Now, we proceed by induction over $j$. 
1. Let $j = 1$. Then, $\texttt{popped}_{1} = \{\braket{  0 , \texttt{BOT} }\}$ and $\gamma[0,\texttt{BOT}]=0$. 
2. Let $j \geq 2$. Notice that for each $\braket{ n , t }$, $\gamma[n,t]$ is updated once during the whole algorithm. Therefore, it suffices to show that the statement holds for the element popped in this iteration, whereas for the other elements the statement holds by the induction hypothesis.
   
   Let $\braket{ \braket{ n , t_{n} } , \text{score}(t^{*}_{n-1},t_{n},\mathbf{ w})+\gamma[n-1,t^{*}_{n-1}] }$ denote the element popped from the priority queue in this iteration. We have that $\gamma[n,t_{n}]= \text{score}(t^{*}_{n-1},t_{n},\mathbf{ w})+\gamma[n-1,t_{n-1}^{*}]$. By induction hypothesis, there exists $\mathbf{t}^{*}_{1:n-2}\in \mathcal{T}^{n-2}$ s.t. $\gamma[n-1,t^{*}_{n-1}]=\text{score}(\mathbf{t}^{*}_{1:n-1},\mathbf{w})$ and therefore, $$\gamma[n,t_{n}]\le \max_{\mathbf{t}_{1:n-1}\in \mathcal{T}^{n-1}}\text{score}(\mathbf{t}_{1:n-1},t,\mathbf{w})$$
   
   
   Now, let $\textbf{t}_{1:n-1}:=(t_{1},\dots,t_{n-1})\in \mathcal{T}^{n-1}$ be arbitrary and let further $k$ to be the minimum index s.t. $\braket{ k , t_{k} }\notin \texttt{popped}_{j-1}$. Then, as $\braket{ n , t_{n} }\notin \texttt{popped}_{j-1}$, we know that $k\leq n$. 
   
   
	- If $k \geq 2$, then $$\begin{aligned}\text{score}(\textbf{t}_{1:n},\mathbf{w})&=\sum_{i=1}^{n}\text{score}(t_{i-1},t_{i},\mathbf{w})\\&\leq \text{score}(\mathbf{t}_{1:k-1},\mathbf{w}) + \text{score}(t_{k-1},t_{k},\mathbf{w})\\&\leq \gamma[k-1,t_{k-1}]+ \text{score}(t_{k-1},t_{k},\mathbf{w})\end{aligned}$$
	   As $\braket{ k-1 , t_{k-1} }\in \texttt{popped}_{j-1}$, we know that $\braket{ \braket{ k , t_{k} } , \text{score}(t',t_{k},\mathbf{w})+\gamma[k-1,t'] }\in \texttt{queue}_{j-1}$ where $\text{score}(t',t_{k},\mathbf{w})+\gamma[k-1,t'] \geq \text{score}(t_{k-1},t_{k},\mathbf{w})+\gamma[k-1,t_{k-1}]$. Therefore, $$\begin{aligned}\text{score}(\textbf{t}_{1:n},\mathbf{w})&\leq \gamma[k-1,t_{k-1}]+ \text{score}(t_{k-1},t_{k},\mathbf{w})\\&\leq \text{score}(t',t_{k},\mathbf{w})+\gamma[k-1,t'] \\& \le \text{score}(t,t_{n},\mathbf{ w})+\gamma[n-1,t_{}]\\&=\gamma[n,t]\end{aligned}$$
	- If $k=1$, then $\braket{ \braket{ 1 , t_{1} } , \text{score}(\texttt{BOT},t_{1},\mathbf{w}) }\in \texttt{queue}_{j-1}$. Hence,$$\text{score}(\mathbf{t}_{1:n},\mathbf{w})\le \text{score}(\texttt{BOT},t_{1},\mathbf{w})\le \gamma[n,t]$$
	
	This proves the claim.
	
Now, let $\braket{ \braket{ N , t_{N}^{*} } , \gamma[N,t^{*}_{N}] }$ be the first element popped from the queue with $N$. Then, there exists $j$ s.t. $\braket{ N , t^{*}_{N} }\notin \texttt{popped}_{j-1}$ but $\braket{ N , t^{*}_{N} }\in \texttt{popped}_{j}$. 

Then, similarly to above, for any other $\mathbf{t}_{1:N}\in \mathcal{T}^N$,  


---
For this exercise, I use the definition of Viterbi in the lecture that computes the 
We show the following claim by induction. Let $\gamma'$ be the array computed by Viterbi. We claim that for all $n\in [N]$ and $t\in \mathcal{T}$, $$\gamma'[n,t]=\gamma[n,t]$$
We show this via induction over $n$. 
- Let $n=1$. Then, $\gamma[1,t]=\text{score}(\texttt{BOT},t,\mathbf{w})$ from above. 
- Let $n\geq 2$. Then, $$\begin{aligned}\gamma'[n,t]&=\max_{t_{n-1}\in \mathcal{T}}(\text{score}(t_{n-1},t,\mathbf{w})+\gamma'[n-1,t_{n-1}])\\&=\max_{t_{n-1}\in \mathcal{T}}(\text{score}(t_{n-1},t,\mathbf{w})+\gamma[n-1,t_{n-1}])\end{aligned}$$
-

$$-\log(2\exp (-x))=x-\log 2$$

---
We give a simple counterexample with $\mathcal{T}:=\{ a,b \}$ and $N=2$. Further, consider the following score function:
$$
\begin{aligned}
\text{{score}}(\texttt{BOT},\cdot ,\textbf{w})=1\\
\text{{score}}(a,a,\textbf{w})=1,\quad \text{{score}}(b,a,\textbf{w})=0,\quad \text{{score}}(a,b,\textbf{w})=0.8,\quad \text{{score}}(b,b,\textbf{w})=0.8
\end{aligned}
$$




```pseudo
\begin{algorithm}\caption{Ford-Fulkerson($G,s,t$)}
\begin{algorithmic} 
\State $f\gets 0$
\While{$\exists s$-$t$-path $p$ in the residual network $G_f$}
\State $c_f(p)\gets \min_{e\in p}c_f(e)$
\For
\State $f\gets f + c_f(p)$
\State $J\gets J\cup \{j  \}$
\State $V\gets V\cup \{ S_{j} \}$
\EndWhile
\end{algorithmic}
\end{algorithm}
```