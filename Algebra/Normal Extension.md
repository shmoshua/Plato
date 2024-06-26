#Definition #Algebra 

> [!definition]
> A [[Field Extension|field extension]] $L:K$ is ***normal*** if every [[Integral Domain|irreducible]] polynomial $f\in K[X]$ which has a root in $L$ splits in $L$.

---
##### Properties
> [!lemma] Theorem 1
> Let $L:K$ be an extension. Then, the following are equivalent:
> 1. $L:K$ is normal and $[L:K]<+\infty$
> 2. $L$ is a [[splitting field]] of some polynomial $f\in K[X]$

> [!proof]-
> Let $L$ be a splitting field of $g\in K[X]$. Let further $f\in K[X]$ with a root $\alpha\in L$. We need to show that $f$ splits in $L$. Let $M$ be the splitting field of $f\cdot g$. Suppose $\theta_{1},\theta_{2}$ are 2 roots of $f$ in $M$.
> 
> For $j=1,2$, we have that: $$[L(\theta_{j}):L][L:K]=[L(\theta_{j}):K]=[L(\theta_{j}):K(\theta_{j})][K(\theta_{j}):K]$$Since $\theta_{1},\theta_{2}$ are roots of the same irreducible polynomial, $K(\theta_{1})\cong K(\theta_{2})$ and especially, $$[K(\theta_{1}):K]=[K(\theta_{2}):K]$$As $L$ is a splitting field of $g$ over $K$, $L(\theta_{j})$ is a splitting field of $g$ over $K(\theta_{j})$. Therefore, by [[Splitting Field|Theorem 2]], the isomorphism $\varphi:K(\theta_{1})\to K(\theta_{2})$ can be extended to $\sigma:L(\theta_{1})\to L(\theta_{2})$ and in particular, $$[L(\theta_{1}):K(\theta_{1})]=[L(\theta_{2}):K(\theta_{2})]$$Therefore, $$[L(\theta_{1}):L]=\frac{[L(\theta_{1}):K(\theta_{1})][K(\theta_{1}):K]}{[L:K]}=\frac{[L(\theta_{2}):K(\theta_{2})][K(\theta_{2}):K]}{[L:K]}=[L(\theta_{2}):L]$$However, as $\alpha\in L$, it follows that for any other root $\theta$ of $f$, $$[L(\theta):L]=[L(\alpha):L]=1$$Therefore, $\theta\in L$ and $L:K$ is normal and finite by [[Splitting Field|Theorem 1]].
> 
> Conversely, assume $L:K$ is normal and finite, i.e. $L=K(\alpha_{1},\dots,\alpha_{n})$ for some $\alpha_{i}\in L$. Then, consider: $$f:=m_{\alpha_{1},K}\cdot \dots \cdot m_{\alpha_{n},K}$$As each $m_{\alpha_{i},K}$ is irreducible and $\alpha_{i}\in L$, it splits in $L$ and consequently, $f$ splits in $L$. Since $L$ is generated by $K$ and the roots of $f$, it is the splitting field of $f$ over $K$.
---
> [!lemma] Theorem 2 (Equivalence of Normal Extension)
> Let $L:=K(A):K$ be an [[Algebraic and Transcendental Element|algebraic extension]]. Then, the following are equivalent:
> 1. $L:K$ is normal.
> 2. for every $a\in A$, $L$ contains a splitting field of $m_{a,K}$.
> 3. for every $\varphi\in \text{Hom}_{K}(L,\overline{L})$, we have $\varphi(L)=L$.

> [!proof]-
> We have: 
> - (1=>2): is clear as $m_{a,K}$ is irreducible.
> - (2=>3): Let $\varphi\in \text{Hom}_{K}(L,\overline{L})$ and $a\in A$. Then, $$m_{a,K}(x)=\prod_{i=1}^{n}(X-a_{i})$$ for $a_{i}\in L$. Then, $m_{a,K}(\varphi(a_{i}))=\varphi(m_{a,K}(a_{i}))=\varphi(0)=0$. Therefore, $$\varphi(\{ a_{1},\dots,a_{n} \})=\{ a_{1},\dots,a_{n} \}$$and $\varphi(K(a_{1},\dots,a_{n}))=K(a_{1},\dots,a_{n})$. As $a$ is arbitrary, $\varphi(L)=L$.
> - (3=>1): Let $a\in A$ and $m_{a,k}(x)=\prod_{i=1}^{n}(X-a_{i})$ where $a_{i}\in \overline{L}$. Wlog assume that $a_{1}=a$. For each $i$, we have: $$\begin{array}{cccc} {\varphi_{i}:}&{K(a)}&\to&{K(a_{i})}\\&{a} &\mapsto & {a_{i}} \end{array}{}$$Therefore, this can be extended to a map $\varphi:L\to \overline{L}$ but by assumption $\varphi(L)=L$. Then, it follows that $a_{i}\in L$ and $m_{a,K}$ splits over $L$.
---
> [!lemma] Theorem 2 (Equivalence of Normal Extension)
> Let $L:K$ be finite. Then, the following are equivalent:
> 1. $L:K$ is normal.
> 2. for every $K\subseteq L\subseteq M$, $\text{Mono}_{K}(L,M)=\text{Aut}_{K}(L)$
> 3. there exists a normal extension $N$ of $L:K$ s.t. $\text{Mono}_{K}(L,N)=\text{Aut}_{K}(L)$


---
> [!lemma] Corollary 3
> Let $L:M:K$ be a tower of fields. If $L:K$ is normal, then $L:M$ is normal.

> [!proof]-
> For $\varphi\in \text{Hom}_{M}(L,\overline{L})\subseteq \text{Hom}_{K}(L,\overline{L})$ we get that $\varphi(L)=L$ by Theorem 2.
---
##### Examples
> [!h] Example 1
> $\mathbb{C}:\mathbb{R}$ is normal.