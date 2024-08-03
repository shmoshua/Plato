#Definition #Topology 

> [!definition]
> A [[topological space]] $X$ is ***simply connected*** if it is [[Path-Connected Space|path-connected]] and $\pi_{1}(X,x)$ is trivial for some $x\in X$. 
- **Remark**: From path-connectedness, all [[Fundamental Group|fundamental groups]] $\pi_{1}(X,x)$ are isomorphic. So the definition implies that the fundamental group is trivial at every point.
---
##### Properties
> [!lemma] Theorem 1
> Let $Y$ be a simply connected space and $G$ a [[Topological Group|discrete group]] s.t. the projection $p:Y\to X$ is a $G$-[[covering space]] where $X:= Y / G$. Then,
> 1. for all $\overline{x_{0}}\in X$, $\pi_{1}(X ,\overline{x_{0}})\cong G$.

> [!proof]+
> Let $\overline{x_{0}}\in X$. Fix $x_{0}\in Y$ s.t. $p(x_{0})=\overline{x_{0}}$. We aim to define an isomorphism: $$\alpha:\pi_{1}(X,\overline{x_{0}})\to G,$$
> 1. **Defining $\beta:\{ \gamma\in C([0,1],X ):\gamma(0)=\gamma(1)=\overline{x_{0}} \}\to G$:**
>    Let $\gamma:[0,1]\to X$ be a loop at $\overline{x_{0}}$. Let $\{ z_{0} \}$ be any point set and define the homotopy: $$h:\{ z_{0} \}\times[0,1]\to X,\quad (z_{0},t)=\gamma(t)$$Then, $h_{0}=\gamma(0)=\overline{x_{0}}$ and $\tilde{h}_{0}=x_{0}$ is a lift of $h_{0}$. Therefore, by [[Lift|homotopy lifting property]], there exists a unique lift $\tilde{h}:\{ z_{0} \}\times[0,1]\to Y$ of $h$ s.t. $\tilde{h}(z_{0},0)=x_{0}$. It follows that $\tilde{h}$ is a path $$\tilde{\gamma}:[0,1]\to Y,\quad t\mapsto \tilde{h}(z_{0},t)$$with $p\circ\tilde{\gamma}=\gamma$. In particular, $p(\tilde{\gamma}(1))=\gamma(1)=\overline{x_{0}}$. 
>    
>    It follows that $\tilde{\gamma}(1)\in p ^{-1}(\overline{x_{0}})$ and there exists a unique $\beta(\gamma)\in G$ s.t. $\tilde{\gamma}(1)=\beta(\gamma)x_{0}$.
> 2. **Claim: $\beta$ is compatible with path-homotopy**:
>    Let $\gamma,\gamma'$ two loops at $\overline{x_{0}}$ s.t. $\gamma \sim_{p} \gamma'$ with path homotopy $h:[0,1]\times[0,1]\to X$. Similarly, by homotopy lifting property we get $\tilde{h}:[0,1]\times[0,1]\to Y$ s.t. $p\circ\tilde{h}=h$ and $\tilde{h}(t,0)=x_{0}$.
>    
>    Now note that: $\tilde{h}(0,s)=\tilde{\gamma}(s)$ and $\tilde{h}(1,s)=\tilde{\gamma}'(s)$ by the uniqueness. Now, $\eta(t):=\tilde{h}(t,1)$ is a continuous map $[0,1]\to p ^{-1}(\{ \overline{x_{0}} \})$. As $[0,1]$ is connected, this map is constant. Therefore, $\tilde{\gamma}(1)=\tilde{\gamma}'(1)$ and $\beta(\gamma)=\beta(\gamma')$. 
> 3. **Showing $\alpha$ is a group homomorphism**:
>    Let $\alpha$ be induced by $\beta$. Let $\gamma,\gamma'$ be loops at $\overline{x_{0}}$ and $\tilde{\gamma},\tilde{\gamma}'$ their lifts starting from $x_{0}$. We define: $$\tilde{\gamma}''(t):=\begin{cases}\tilde{\gamma}(2t)&0\leq t\leq \frac{1}{2}\\\beta(\gamma)\tilde{\gamma}'(2t-1)& \frac{1}{2}\leq t\leq 1\end{cases}$$Then, $\tilde{\gamma}'':[0,1]\to Y$ is continuous as $\tilde{\gamma}(1)=\beta(\gamma)x_{0}=\beta(\gamma)\tilde{\gamma}'(0)$. Further, $$p(\tilde{\gamma}''(t))=\begin{cases}\gamma(2t)&0\leq t\leq \frac{1}{2}\\\gamma'(2t-1)& \frac{1}{2}\leq t\leq 1\end{cases}$$Therefore, $p\circ\tilde{\gamma}''=\gamma\gamma'$ and we have that: $$\beta(\gamma\gamma')x_{0}=\tilde{\gamma}''(1)=\beta(\gamma)\tilde{\gamma}'(1)=\beta(\gamma)\beta(\gamma')x_{0}$$
> 4. **Showing that $\alpha$ is injective**:
> 	Let $\gamma$ be a loop at $\overline{x_{0}}$ s.t. $\beta(\gamma)=e_{G}$, i.e. $\tilde{\gamma}(1)=x_{0}$. Then, as $Y$ is simply connected, there exists a path homotopy $\tilde{h}:[0,1]\times[0,1]\to Y$ from $\tilde{\gamma}$ to $\varepsilon_{x_{0}}$. Then, $p\circ \tilde{h}:[0,1]\times[0,1]\to X$ is a path homotopy from $\gamma$ to $\varepsilon_{\overline{x_{0}}}$. Therefore, $\gamma$ is trivial in $\pi_{1}(X,\overline{x_{0}})$.
> 5. **Showing that $\alpha$ is surjective**:
>    Given $g\in G$, there exists a path $\tilde{\gamma}:[0,1]\to Y$ from $x_{0}$ to $gx_{0}$. Then, $\gamma:=p\circ\tilde{\gamma}$ is a loop in $X$ at $\overline{x_{0}}$ and $\tilde{\gamma}$ is its lift. Therefore, $\beta(\gamma)=g$. Hence, $\beta$ is surjective and thereby $\alpha$.
>    
- **Remark**: It is necessary that $p$ is a covering space (cf. Non-example 1).
- **Remark**: It is also not possible to have such a simply connected space $Y$ for every $X$, as this implies that $X$ is [[Path-Connected Space|path-connected]] (cf. [[Path-Connected Space|Proposition 1.2]]) and [[Semi-Locally Simply Connected Space|semi-locally simply connected]] (cf. [[Semi-Locally Simply Connected Space|Example 2]])
---
##### Examples
> [!h] Example 1
> From [[Covering Space|Example 1]] $p:\mathbb{R}\to \mathbb{R} /\mathbb{Z}$ is a covering space. Further, $\mathbb{R}$ is simply connected as it is contractible. Therefore, 
> 1. $\pi_{1}(\mathbb{R} / \mathbb{Z},0)\cong \mathbb{Z}$ by Theorem 1.
> 2. $\pi_{1}(S^1, 1)\cong \mathbb{Z}$ by [[Fundamental Group|Corollary of Proposition 2]].
---
##### Non-Examples
> [!h] Non-Example 1
> Consider $H:=\{ z\in \mathbb{C}:\text{Im(z)}>0 \}$. Then, $H$ is simply connected. However, consider $G:=\text{SL}(2,\mathbb{R})$. With the group action: $$G\times H\to H,\quad \begin{bmatrix}a&b\\c&d\end{bmatrix}z=\frac{az+b}{cz+d}$$
> 1. $H /G$ is homeomorphic to $\mathbb{C}$.
> 2. $\pi_{1}(H / G,\overline{x_{0}})$ is trivial, not $\text{SL}(2,\mathbb{R})$.
---
