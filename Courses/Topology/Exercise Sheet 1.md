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


---

##### Problem 2

> Sei X eine Menge und sei Y ein topologischer Raum. Sei f : X → Y eine beliebige Funktion. (a) Zeigen Sie, dass die Menge T der Teilmengen von X der Form U = f −1 (V ) f¨ur eine offene Menge V = f −1 (V ) eine Topologie auf X ist. (b) Zeigen Sie, dass f : (X, T ) → Y stetig ist.
