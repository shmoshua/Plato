#Definition #Topology 

> [!definition]
> A [[Hausdorff space]] $X$ is ***normal***, if one of the following equivalent conditions hold:
> 1. if $A,B\subseteq X$ are disjoint closed, there exists $f:X\to[0,1]$ s.t. $f|_{A}=0$ and $f|_{B}=1$.
> 2. if $A\subseteq X$ is closed and $g:A\to[a,b]$ is continuous, there exists a continuous extension $f:X\to[a,b]$.
> 3. if $A,B\subseteq X$ are disjoint closed, there exist disjoint open sets $U\supseteq A$ and $V\supseteq B$.
> 4. if $A\subseteq U\subseteq X$ with $A$ closed and $U$ open, there exists $V\subseteq X$ open s.t. $A\subseteq V\subseteq \overline{V}\subseteq U$.
---
##### Properties
> [!lemma] Proposition 1
> The conditions above are indeed equivalent.

> [!proof]+
> We have: 
> - 3 and 4 are equivalent by taking $B:= X / U$. 
> - (1=>3): For $A,B\subseteq X$ disjoint and closed, choose $U:=f^{-1}([0,1/3))$ and $V:=f^{-1}(( 2/3,1])$.
> - (4=>1): We first claim that there exists open sets $\{ U_{t} \}_{t\in[0,1]}$ s.t. 
> 	1. $A\subseteq U_{0}$
> 	2. for $s<t$, $\overline{U_{s}}\subseteq U_{t}$
> 	3. $B\subseteq X \backslash U_{1}$
> 	
> 	This is the case as starting from $U_{1}:=X \backslash B$, we can inductively define the open sets following the dyadic numbers.
> 	
> 	Then, define $f:X\to[0,1]$ by:$$f(x)=\begin{cases}1&x\in X \backslash U_{1}\\ \inf\{ s\in[0,1]|x\in U_{s} \}&x\in U_{1}\end{cases}$$Then, 
> - (2=>1): Given $A,B\subseteq X$ disjoint closed, let $C:=A\cup B$ is closed and: $$\begin{array}{cccc} {g:}&{C}&\to&{[0,1]}\\&{x} &\mapsto & {\begin{cases}0&x\in A\\1&x\in B\end{cases}} \end{array}{}$$is continuous. 
---
> [!lemma] Lemma 2
> If $A,B\subseteq X$ are disjoint closed