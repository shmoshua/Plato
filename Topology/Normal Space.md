#Definition #Topology 

> [!definition]
> A [[Hausdorff space]] $X$ is ***normal***, if one of the following equivalent conditions hold:
> 1. If $A,B\subseteq X$ are disjoint closed, there exist disjoint open sets $U\supseteq A$ and $V\supseteq B$.
> 2. if $A\subseteq U\subseteq X$ with $A$ closed and $U$ open, there exists $V\subseteq X$ open s.t. $A\subseteq V\subseteq \overline{V}\subseteq U$.
> 3. if $A,B\subseteq X$ are disjoint closed, there exists a continuous function $f:X\to[0,1]$ s.t. $f|_{A}=0$ and $f|_{B}=1$.
> 4. if $A\subseteq X$ is closed and $f:A\to[a,b]$ is continuous, there exists a continuous extension $F:X\to[a,b]$.

---
##### Properties
> [!lemma] Theorem 1 (Urysohn's Lemma, Tietze Extension Theorem)
> The conditions above are indeed equivalent.

> [!proof]-
> We have: 
> - (1=>2): take $B:= X \backslash U$. Then, there exists $V\supseteq A$ open and $\overline{V}\subseteq U$.
> - **(2=>3): Urysohn's Lemma**: Let $A, B\subseteq X$ be two disjoint closed subsets. Let $U:=X \backslash B$.  Further let: $$\Delta:=\{ k 2^{-n}:0<k<2^n, n\geq 1 \}$$We claim there exists a collection $\{ U_{r}:r\in \Delta \}$ of open sets in $X$ s.t. 
> 	1. $A\subseteq U_{r}\subseteq U$ for all $U_{r}\in \Delta$ and 
> 	2. $\overline{U_{r}}\subseteq U_{s}$ for all $r<s$.
> 	
> 	From 1, we have $U_{\frac{1}{2}}\subseteq X$ open with $A\subseteq U_{ \frac{1}{2}}\subseteq \overline{U}_{\frac{1}{2}}\subseteq U$. We can inductively construct $U_{r}$ where $r=k 2^{-n}$ over $n$.
> 	
> 	Now set $U_{1}:=X$ and define $f(x):=\inf\{ r\in\Delta \cup \{ 1 \}: x\in U_{r} \}$f for $x\in X$}. We clearly have $0\leq f(x)\leq 1$ for all $x\in X$. 
> 	
> 	Since $A\subseteq U_{r}\subseteq U$ for all $r\in \Delta$, we moreover deduce $f(x)=0$ for all $x\in A$ and $f(x)=1$ for all $x\in B$. It remains to show that $f$ is continuous. 
> 	
> 	To that purpose fix $\alpha\in \mathbb{R}$. We observe that $f(x)<\alpha$ if and only if there is an $r\in \Delta \cup \{ 1 \}$ with $r<\alpha$ and $x\in U_{r}$, which is in turn equivalent to $x\in \bigcup_{r<\alpha}^{}U_{r}$. We conclude that $$f^{-1}((-\infty,\alpha))=\bigcup_{r<\alpha }^{}U_{r}$$is open. 
> 	
> 	Analogously, $f(x)>\alpha$ if and only if there is an $r\in \Delta$ with $r>\alpha$ and $x\notin U_{r}$. Here we used that $\overline{U_{\sigma}}\subseteq U_{\rho}$ for all $\sigma<\rho$. This fact also allows us to deduce that the last result is equivalent to the existence of a number $s\in \Delta$ with $s>\alpha$ and $x\notin U_{s}$. We conclude that $$f^{-1}((\alpha,\infty))=\bigcup_{s>\alpha}^{}\overline{U_{s}}^c$$ which is open again.  Since the open half-lines generate the topology on $\mathbb{R}$, we infer that $f$ is continuous.
> - **(3=>4): Tietze's Extension Theorem**:
> 	  By replacing $f$ with $\frac{f-a}{b-a}$, we may assume that $[a,b]=[0,1]$. We inductively construct a sequence $(g_{n})_{n}$ of continuous functions on $X$ such that 
> 	  1. $0\leq g_{n}\leq \frac{2^{n-1}}{3^n}$ on $X$ and 
> 	  2. $0\leq f-\sum_{j=1}^{n}g_{j}\leq \left( \frac{2}{3} \right)^n$ on $A$ for all $n\in \mathbb{N}$. 
> 	  
> 	  Set $B:=f^{-1}\left( \left[ 0, \frac{1}{3} \right] \right)$ and $C:=f^{-1}\left( \left[  \frac{2}{3},1 \right] \right)$. Since $f$ is continuous on $A$, we have $B,C$ are closed in $A$. Hence, $B,C$ are closed in $X$ as well as $A$ is closed. Therefore, by Urysohn’s Lemma, we have a continuous function $g_{1}:X\to\left[ 0, \frac{1}{3} \right]$ with $g_{1}|_{B}=0$ and $g_{1}|_{C}= \frac{1}{3}$. In particular, $0\leq f-g_{1}\leq \frac{2}{3}$ on $A$. 
> 	  
> 	  Now assume that we constructed continuous functions $g_{1},\dots,g_{N}$ on $X$ with the above conditions. The function $h_{N}:=f -\sum_{j=1}^{N}g_{j}$ is continuous on $A$ so that the sets $B_{N}:=h_{N}^{-1}([0,2^N / 3^{N+1}])$ and $C_{N}:=h_{N}^{-1}([(2 /3)^{N+1},1])$ are closed in $X$ by the same reasoning as above. We again apply Urysohn’s Lemma to get a continuous function $g_{N+1}:X \to \left[ 0, \frac{2^N}{3^{N+1}} \right]$ with $g_{N+1}|_{B_{N}}=0$ and $g_{N+1}|_{C_{N}}=\frac{2^N}{3^{N+1}}$. 
> 	  
> 	  It follows that $0\leq h_{N}-g_{N+1}\leq\left( \frac{2}{3} \right)^{N+1}$ on $A$. Since $\left\| g_{n} \right\|_{\infty}\leq \frac{2^{n-1}}{3^n}$ for all $n\in \mathbb{N}$, the series $\sum_{n=1}^{\infty}g_{n}$ converges uniformly to a continuous function $F$ on $X$. Moreover, we infer $0\leq f-F\leq \left( 2 /3 \right)^n$ on $A$ for all $n\in N$, implying $f=F$ on $A$.
> - **(4=>3):** 
>   For $A,B\subseteq X$ disjoint closed, define $f:A\cup B\to[0,1]$ where $f|_{A}=0$ and $f|_{B}=1$. Then, for any closed $C\subseteq[0,1]$, $f^{-1}(C)$ is closed and $f$ is continuous. Therefore, by Tietze's extension theorem, we can extend this to a continuous function $F:X\to[0,1]$.
> - **(3=>1):**
>   For $A,B\subseteq X$ disjoint closed, let $f:X\to[0,1]$ be the continuous function with $f|_{A}=0$ and $f|_{B}=1$. Take $U:= f^{-1}\left( \left[ 0, \frac{1}{3} \right) \right)$ and $V:= f^{-1}(\left( \frac{2}{3}, 1] \right)$. 
---
##### Examples
> [!h] Example 1
> Any metric space is normal.

> [!proof]-
> We will verify condition 1. Let $A,B\subseteq X$ disjoint and closed. We verify that $d_{A}:=d(\cdot,A)$ is a continuous function with $d_{A}(A)=\{ 0 \}$. Therefore, we can define: $$U:=\{ x\in X:d_{A}(x)<d_{B}(x) \},\quad V:=\{ x\in X:d_{B}(x)<d_{A}(x) \}$$as open disjoint sets. 
---
> [!h] Example 2
> Any compact Hausdorff space is normal.

> [!proof]-
> We prove condition 1. Let $A,B\subseteq X$ be disjoint closed. Then, for every $x\in B$, we can define $U_{x},V_{x}$ disjoint open s.t. $A\subseteq U_{x}$ and $x\in V_{x}$. Then, $B\subseteq \bigcup_{x\in B}^{}V_{x}$ and there exists finite $J\subseteq B$ s.t. $B\subseteq \bigcup_{x\in J}^{}V_{x}$. By defining $U:=\bigcap_{j\in J}^{}U_{j}$ and $V:=\bigcup_{j\in J}^{}V_{j}$ proves the statement.
---
