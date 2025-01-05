#Definition #Topology 

> [!definition]
> Let $G$ be a [[topological group]] acting continuously on a [[topological space]] $X$.
> 1. The [[group action]] is called ***proper*** if: $$\rho:G\times X\to X\times X,\quad (g,x)\mapsto (x,gx)$$is a [[proper map]].
---
##### Properties
> [!lemma] Theorem 1
> Let $G\curvearrowright X$ be a proper group action. Then,
> 1. $X / G$ is Hausdorff.
> 1. each orbit $Gx$ is closed in $X$.
> 3. $\text{St}_{G}(x)$ is compact for all $x\in X$.
> 4. $G / \text{St}_{G}(x) \to Gx,[a]\mapsto ax$ is a homeomorphism.
> 5. if $G$ is Hausdorff, then so is $X$.

> [!proof]-
> We have that: 
> 1. As $C:=\{ (x,gx):x\in X,g\in G \}=\rho(G\times X)$, we have that it is closed in $X\times X$ by properness. Let $\sigma:G\times X\to X$ be the group action and $\pi:X\to X / G$ the quotient map. Then, for any open $U\subseteq X$, $$\pi ^{-1}(\pi(U))=\sigma(G \times U)=\bigcup_{g\in G}^{}gU$$which is open. Hence, $\pi$ is an open map by [[Quotient Topology|Lemma 4]], $X / G$ is Hausdorff. 
> 2. As $X / G$ is Hausdorff, $\{ Gx \}\in X / G$ is closed and $Gx\subseteq X$ is closed. 
> 3. As $\{ (x,x) \}$ is compact and $\rho ^{-1}(\{ x,x \})=\text{St}_{G}(x)\times \{ x \}$, we have that by properness, $\text{St}_{G}(x)\times \{ x \}$ is compact. Now, $\text{St}_{G}(x)$ is just the image of the continuous projection $G\times X\to G$. 
> 4. We have that the map is continuous. Further, it is a bijection as $a^{-1}b\in \text{St}_{G}(x)$ if and only if $bx=aa^{-1}bx=ax$. Hence, it's left to show that the map is closed. Let $C\subseteq G / \text{St}_{G}(x)$ be closed. Then, $\pi ^{-1}(C)\subseteq G$ is closed and it follows that $Cx$ is closed. 
> 5. Lastly, if $G$ is Hausdorff, then $\{ e \}\times X$ is closed and $\Delta_{X}=\rho(\{ e \}\times X)$ is closed. Hence, $X$ is Hausdorff.
---
