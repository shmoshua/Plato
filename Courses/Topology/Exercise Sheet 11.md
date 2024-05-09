#Series #Topology 

> [!def] Problem 1
> A topological space $X$ is called ***path-connected*** if, for every $x$ and $y$ in $X$, there exists a path $\gamma:[0,1]\to X$ s.t. $\gamma(0)=x$ and $\gamma(1)=y$.
> 1. Show that if $X$ is path-connected, then it is connected. 
> 2. Show that the relation $\sim$ defined by $x\sim y$ if and only if there exists a path in $X$ from $x\sim y$ is an equivalence relation. 
> 3. Show that the equivalence class of some $x\in X$ for the relation $\sim$ is contained in the connected component of $x\in X$. This equivalence class is called the path-connected component of $x$. 
> 4. We now assume that $X$ is a connected topological manifold. Show that the path-connected component of any $x\in X$ is open. 
> 5. Let $X$ be a contractible space. Show that $X$ is path connected. 

We have:
1. let $x\in X$. Then, for any $y\in X$, there exists a path $\gamma_{y}$ from $x$ to $y$ and as $\gamma_{y}$ is continuous and $[0,1]$ is connected, $\text{im }\gamma_{y}$ is connected. Then, $X=\bigcup_{y\in X}^{}\text{im }\gamma_{y}$ is connected as $x\in \text{im }\gamma_{y}$ for all $y\in X$.
2. we have that $\gamma:[0,1]\to X,t\mapsto x$ is a path from $x$ to $x$ for any $x\in X$. Therefore, $x \sim x$. For $x\sim y$ with a path $\gamma$, $\overline{\gamma}$ is a path from $y$ to $x$. Lastly, for $x\sim y$ and $y\sim z$ with paths $\gamma_{1}$ and $\gamma_{2}$, $\gamma_{1}\gamma_{2}$ is a path from $x$ to $z$.
3. The path-connected component of $X$ is by 1 connected. As the connected component of $x$ is the largest connected set containing $x$, this proves the statement.
4. Let $x\in X$ and $P\subseteq X$ be the path-connected component of $x$. For $p\in P$, let $U$ be the open neighborhood of $p$ and $\varphi$ the homeomorphism. For the path $\gamma$ from $x$ to $p$, let $Q:=\text{im }\gamma \cap U$. 
5. 
6. $\gamma ^{-1}(U)$ is an open set. For $q\in \gamma ^{-1}(U)$, 