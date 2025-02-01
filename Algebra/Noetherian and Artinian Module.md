#Definition #Algebra 

> [!definition]
> Let $M$ be a $R$-module.
> 1. $M$ is called ***Noetherian*** if every ascending chain of submodules of $M$: $$M_{0}\subseteq M_{1}\subseteq M_{2}\subseteq\dots$$becomes stationary, i.e. for every chain, there exists $n\in \mathbb{N}$ s.t. $M_{k}=M_{n}$ for all $k\geq n$. 
> 2. $M$ is called ***Artinian*** if every deschedning chain of submodules of $M$: $$M_{0}\supseteq M_{1} \supseteq M_{2} \supseteq\dots$$becomes stationary.

---
##### Examples

> [!h] Example 1
> We have that:
> 1. Any field $K$ is both Noetherian and Artinian as it only has trivial ideals. 
> 2. For a $K$-vector space $V$, TFAE:
> 	1. $K$ is Noetherian.
> 	2. $K$ is Artinian.
> 	3. $K$ is finite dimensional.
> 3. $\mathbb{Z}$ is Noetherian but not Artinian.
> 4. $R:=\bigcup_{n}^{}\mathbb{R}[]$

> [!proof]
> We have:
> 1. Obvious.
> 2. If $V$ is finite dimensional, there can only be finite strictly increasing ascending or descending chain of vector subspaces. As the dimension has to be strictly increasing. 
> 	
> 	If $V$ is infinite dimensional, we can form an ascending chain that doesn't become stationary. Set $M_{0}:=0$ and for $i$, let $M_{i+1}:= M_{i}+\braket{ v_{i+1} }$ where $v_{i+1}\notin M_{i}$. Similarly, for a descending chain, we choose $M_{0}:=M$ and let $M_{i+1}:=M_{i}\cap \text{ker }\varphi_{i+1}$ where $\varphi_{i+1}:V\to K$ s.t. $\varphi_{i+1}|_{M_{i}}\neq 0$. Then, $$M/M_{n}\cong (M / M_{n+1}) / (M_{n} / M_{n+1})$$Hence, from $\text{dim}(M_{n} / M_{n+1})=1$, we have that it forms a descending chain. 
> 3. Assume we have a ascending chain $I_{0}\subsetneq I_{1}\subsetneq \dots$. As $\mathbb{Z}$ is a PID, we have that $I_{1}=(a)$ for some $a\neq 0$. However, by [[Ring Homomorphism|Proposition 5]], the ideals in $\mathbb{Z}$ that contain $(a)$ forms a bijection to the ideals in $\mathbb{Z} / (a)$, which is finite. Hence, the chain cannot be infinitely long. 
>    
>    $\mathbb{Z}$ is not Artinian as we have: $$\mathbb{Z} \supsetneq  2\mathbb{Z} \supsetneq 4\mathbb{Z} \supsetneq 8\mathbb{Z} \supsetneq \dots$$
> 	2. 