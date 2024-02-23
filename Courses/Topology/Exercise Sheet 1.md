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
> 4. Construct $X,Y,f$ and $\{ U_{\lambda} \}\subseteq \mathcal{T}_{X}$ s.t. $f$ is not always(d) Konstruieren Sie X, Y , f und ein gewisses (Ui)i∈I , so dass f nicht immer dann konstant ist, wenn f|Ui f¨ur alle i konstant ist. (Dieses Ergebnis l¨asst sich wie folgt zusammenfassen: Kontinuierlich zu sein ist eine lokale Eigenschaft einer Funktion, aber konstant zu sein jedoch nicht.) (e) F¨ur i ∈ I, sei fi : Ui → Y eine stetige Funktion (wobei Ui die Unterraumtopologie hat). Wenn fi(x) = fj (x) f¨ur alle i und j in I und alle x ∈ Ui ∩ Uj , zeigen Sie, dass es eine einzige stetige Funktion f : X → Y gibt, wobei fi und f auf Ui ¨ubereinstimmen. (Dieses Ergebnis bedeutet, dass man stetige Funktionen lokal definieren kann, vorausgesetzt, dass zwei m¨ogliche Definitionen an den Stellen, an denen eine Mehrdeutigkeit bestehen k¨onnte, dieselbe Antwort geben.)
##### Problem 2

> Sei X eine Menge und sei Y ein topologischer Raum. Sei f : X → Y eine beliebige Funktion. (a) Zeigen Sie, dass die Menge T der Teilmengen von X der Form U = f −1 (V ) f¨ur eine offene Menge V = f −1 (V ) eine Topologie auf X ist. (b) Zeigen Sie, dass f : (X, T ) → Y stetig ist.
