 a#Series #Topology 

> [!definition] Problem 1
> Let $X$ be a set.
> 1. Let $d_{1}$ and $d_{2}$ be distances on $X$. If there exist $a,b>0$ s.t.$$d_{1}(x,y)\leq d_{2}(x,y)^a,\quad d_{2}(x,y)\leq d_{1}(x,y)^b,\quad \forall(x,y)\in X\times X$$ show that the topologies defined by $d_{1}$ and $d_{2}$ are the same.
> 2. Let $d$ be a distance on $X$. Show that: $$\delta(x,y)= \frac{d(x,y)}{1+d(x,y)}$$is a distance on $X$. Show that the topology defined by $\delta$ is the same as the topology defined by $d$. Show that $\delta(x,y)\leq 1$ for all $(x,y)\in X\times X$. 

We have:
1. Let $U\subseteq \mathcal{T}_{d_{1}}$. Then, for any $x\in X$, there exists $r>0$ s.t. $B^1_{<r}(x)\subseteq U$. Consider $B^2_{<r^{1/a}}(x)$. We have:$$B^2_{<r^{1 /a}}(x)=\{ y\in X:d_{2}(x,y)<r^{1/a} \}\subseteq \{ y\in X:d_{1}(x,y)<r \}=B^1_{<r}(x)\subseteq U$$Therefore, $U\subseteq \mathcal{T}_{d_{2}}$. The opposite inclusion holds by symmetry.
2. **Showing $\delta$ is a distance**: The non-negativity, non-degeneracy and symmetry are clear from the definition. For triangle inequality, notice that for $a,b,c\geq 0$ s.t. $a\leq b+c$, we have: $$\frac{a}{1+a}\leq \frac{b+c}{1+b+c}=\frac{b}{1+b+c}+ \frac{c}{1+b+c}\leq \frac{b}{1+b}+\frac{c}{1+c}$$This shows the triangle inequality.
   
   Showing For any $x\in X$ and $r>0$, as $\delta(x,y)\leq d(x,y)$ (from the non-negativity of $d(x,y)$), $B_{<r}^d(x)\subseteq B_{<r}^\delta(x)$. On the other hand, $d(x,y)= \delta(x,y)/(1-\delta(x,y))$ and $B_{< \frac{r}{1-r}}^\delta(x)\subseteq B^\delta_{<r}(x)$. This shows that the topologies coincide.  
3. Let $U\subseteq \mathcal{T}_{\delta}$. Then, for any $x\in X$, there exists $r>0$ s.t. $B^\delta_{<r}(x)\subseteq U$. But, $$B_{}$$ 
	
	2. $\delta(x,y)\leq d(x,y)$ as $d(x,y)$ is non-negative.
	3. $d(x,y)^a+d(x,y)^{a+1}\leq d(x,y)$ $d(x,y)^{a-1}+d(x,y)^a\leq 1$
4. $$x^{b}\leq\frac{x}{1+x}\leq x^ a$$