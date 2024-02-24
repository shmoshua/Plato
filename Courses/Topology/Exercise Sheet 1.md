#Series #Topology 

---
> [!definition] Problem 1
> Let $X$ be a set. 
> 1. Show that the cofinite topology: $$\mathcal{T}_{\text{cof}}:=\{ U\subseteq X:X \backslash U\text{ is finite or empty} \}$$is a topology on $X$.
> 2. For what $X$ does the set of all finite subsets build a topology?

We have:
1. **Showing the cofinite topology is a topology**: 
   Firstly, we have that $\varnothing\in \mathcal{T}_{\text{cof}}$ and $X\in \mathcal{T}_{\text{cof}}$ as $X\backslash X=\varnothing$. 
   
   For the union of $\{ U_{\lambda} \}\subseteq \mathcal{T}_{\text{cof}}$,  wlog we can assume that $X \backslash U_{\lambda}$ is finite, as $\varnothing$ does not "add" anything to the union. Therefore, $X \backslash \bigcup_{\lambda\in \Lambda}^{}U_{\lambda}=\bigcap_{\lambda\in \Lambda}^{}X \backslash U_{\lambda}$, which is finite, and $\bigcup_{\lambda\in \Lambda}^{}U_{\lambda}$ is open. 
   
   For $U_{1},U_{2}\in \mathcal{T}_{\text{cof}}$, if any of them is empty, then the intersection is empty and thereby open. Otherwise, $X\backslash (U_{1}\cap U_{2})=(X \backslash U_{1})\cup(X \backslash U_{2})$ which is finite as a union of two finite sets. This proves the statement.
2. **Showing $X$ is finite if and only if the finite subsets build a topology**:
	Assume $X$ is finite. Then, the set of all finite subsets equals the discrete topology on $X$. Therefore, it builds a topology. 
	
	Conversely, if $X$ is infinite, the union of all singleton sets, which are open sets by definition, is not open and therefore it is not a topology.

---

> [!definition] Problem 2
>  Let $X$ be a set and $(Y,\mathcal{T}_{Y})$ a topological space. Let $f:X\to Y$ be any function. 
>  1. Show that $\mathcal{T}:=\{ f^{-1}(V)\subseteq X:V\in \mathcal{T}_{Y} \}$ is a topology on $X$.
>  2. Show that $f:(X,\mathcal{T})\to(Y,\mathcal{T}_{Y})$ is continuous.

We have:
1. Firstly, $\varnothing =f^{-1}(\varnothing)$ and $X=f^{-1}(Y)$. Therefore, $\varnothing,X\in \mathcal{T}$.
   
   For $\{ U_{\lambda} \}\subseteq \mathcal{T}$, then there exists $\{ V_{\lambda} \}\subseteq \mathcal{T}_{Y}$ s.t. $f^{-1}(V_{\lambda})=U_{\lambda}$. Then, $$\bigcup_{\lambda\in \Lambda}^{}U_{\lambda}=\bigcup_{\lambda\in \Lambda}^{}f^{-1}(V_{\lambda})=f^{-1}\left( \bigcup_{\lambda \in \Lambda}^{}V_{\lambda} \right) $$as $\bigcup_{\lambda\in \Lambda}^{}V_{\lambda}$ is open, $\bigcup_{\lambda\in \Lambda}^{}U_{\lambda}\in \mathcal{T}$.
   
   Similarly, for $U_{1},U_{2}\in \mathcal{T}$, $U_{1}\cap U_{2}=f^{-1}(V_{1})\cap f^{-1}(V_{2})=f^{-1}(V_{1}\cap V_{2})$ which is analogously open.
2. By definition, any open map $V\subseteq Y$ is mapped to $f^{-1}(V)\in \mathcal{T}$. 
---
> [!definition] Problem 3
> Let $X,Y$ be topological spaces. Let $(U_{\lambda})\subseteq \mathcal{T}_{X}$ s.t. $X=\bigcup_{\lambda\in \Lambda}^{}U_{\lambda}$ and $f:X\to Y$ any function. 
> 1. Show $U\subseteq X$ open if and only if $U_{\lambda}\cap U$ is open for all $\lambda\in \Lambda$.
> 2. Show that if $f$ is continuous, then $f|_{U_{\lambda}}$ is continuous for all $\lambda\in \Lambda$ w.r.t. the subspace topology.
> 3. Show the converse: if $f|_{U_{\lambda}}$ is continuous for all $\lambda\in\Lambda$, then $f$ is continuous.
> 4. Construct $X,Y,f$ and $\{ U_{\lambda} \}\subseteq \mathcal{T}_{X}$ s.t. $f|_{U_{\lambda}}$ is constant for all $\lambda\in \Lambda$ but $f$ is not.
> 5. For $\lambda\in \Lambda$, let $f_{\lambda}:U_{\lambda}\to Y$ be a continuous function w.r.t. the subspace topology. If $f_{\alpha}(x)=f_{\beta}(x)$ for all $\alpha,\beta\in \Lambda$ and $x\in U_{\alpha}\cap U_{\beta}$, then show that there exists a unique continuous function $f:X\to Y$ where $f_{\lambda}$ and $f$ coincide on $U_{\lambda}$.

We have:
1. If $U$ is open, $U_{\lambda}\cap U$ is open as an intersection of open sets. Conversely, $$U=U\cap X=U\cap \bigcup_{\lambda\in \Lambda}^{}U_{\lambda}=\bigcup_{\lambda\in \Lambda}^{}(U\cap U_{\lambda})$$which is open as a union of open sets. 
2. 

---