#Definition #Algebra-I 

>[!Definition]
>For $H \leq G$ and $x\in G$, let $$xH:=\{ xh:h\in H \}\quad \text{and}\quad Hx:=\{ hx:h\in H \}$$
> The sets $xH$ and $Hx$ are called ***left cosets*** and ***right cosets***, respectively.
---
##### Properties
> [!lemma] Lemma 1
> Let $G$ be a group, $H \leq G$ and $x,y\in G$ arbitrary. 
> 1. $|xH|=|H|$, i.e. there exists a bijection between $xH$ and $H$.
> 2. $x\in xH$.
> 3. $xH=H$ if and only if $x \in H$.
> 4. $xH=yH$ if and only if $x^{-1}y\in H$.
> 5. $xH=\{ g\in G:gH=xH \}$.
> 6. It holds that:$$\bigcup_{x\in G}^{}xH=G=\bigcup_{x\in G}^{}Hx$$

>[!proof]-
>Consider:
>1. We define a bijection $\varphi_{x}:H\to xH, h\mapsto xh$. If $\varphi_{x}(h_{1})=\varphi_{x}(h_{2})$ for some $h_{1},h_{2}\in H$, then $xh_{1}=xh_{2}$ and $xh_{1}h_{2}^{-1}=xh_{2}h_{2}^{-1}=xe=x$. Therefore, $h_{1}h_{2}^{-1}=e$ and $h_{1}=h_{2}$.
>2. Since $e\in H$, $x=xe\in xH$.
>3. If $xH=H$, then $e\in H$ and $xe\in H$. Now assume that $x\in H$. As $H$ is a group, we have $xH \subseteq H$. For any $h\in H$, as $x^{-1}\in H$, we have $x^{-1}h\in H$ and $h=x(x^{-1}h)\in xH$. Therefore, $H \subseteq xH$ and therefore $xH=H$.
>4. If $xH=yH$, then $$ H=x^{-1}xH=x^{-1}yH \Longrightarrow x^{-1}y\in H$$
>	Conversely, if $x^{-1}y\in H$, then we have $x^{-1}yH=H$ and $yH=x x^{-1}yH=xH$.
>5. If $g\in xH$, then $g=xh$ for some $h\in H$. Therefore, $gH=xhH=xH$. Conversely, if $gH=xH$, then $g\in gH=xH$.
---
> [!lemma] Lemma 2
> Let $H \leq G$, then for any $x,y\in G$, we have either $xH=yH$ or $xH\cap yH=\varnothing$.

>[!proof]-
>If $xH\cap yH=\varnothing$, we are done. If there exists $z\in xH\cap yH$, then $z=xh_{1}=yh_{2}$ for some $h_{1},h_{2}\in H$. Therefore, $x^{-1}z\in H$ and $z^{-1}y\in H$. Then, $(x^{-1}z)(z^{-1}y)=x^{-1}y\in H$. It follows that $xH=yH$.
---
> [!lemma] Lemma 3
> Let $G$ be a group and $H\leq G$ s.t. $[G:H]=2$. Then, for all $x \in G$, we have:$$xH=Hx,\quad \text{i.e. }\quad xHx^{-1}=H$$

>[!proof]-
>If $x\in H$ then $xH=Hx=H$. If $x\in G\backslash H$, then $G=H\cup xH$ and $G=Hx\cup H$ where $H\cap xH=\varnothing =H\cap Hx$, which implies that $xH=Hx$.
---
> [!lemma] Theorem 4 (Lagrange)
> Let $G$ be a group and $H \leq G$, then:$$|G|=[G:H]\cdot|H|$$
> If $G$ is finite, then it holds that $|H| \mid |G|$. 

>[!proof]-
>Consider the partition $G / H$ of $G$. This partition has $|G:H|$ parts and each has size $H$. Therefore, $|G|=|G:H|\cdot|H|$. In particular, if $G$ is finite, $|H|$ divides $|G|$.
- **Corollary**: For a finite $G$, if $x\in G$, $x^{\left| G \right|}=e$, i.e. $\text{ord}(x)|\left| G \right|$ as $\braket{ x  }\leq G$.
---
> [!lemma] Proposition 5
> Let $G$ be a group, $H \leq G$, and $x\in G$. Then, $xHx^{-1}=\{  xhx^{-1} | h\in H \} \leq G$ . $H$ and $xHx ^{-1}$ are ***conjugated subgroups***. 

>[!proof]-
>Let $xh_{1}x^{-1}=:a$ and $xh_{2}x^{-1}=:b$ for $h_{1},h_{2}\in H$. Then, $a,b\in xHx^{-1}$. Then,
> $$ab^{-1}=(xh_{1}x^{-1})(xh_{2}x^{-1})^{-1}=xh_{1}x^{-1}xh_{2}^{-1}x^{-1}=xh_{1}h_{2}^{-1}x^{-1}\in xHx^{-1}$$
---
##### Related Definitions
- [[Quotient Set]]


%% For $K \leq H \leq G$, we have that $K \leq G$ and it holds that $[G:K]=[G:H]\cdot [H:K]$. %%
