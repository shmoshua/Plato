#Definition #Topology 

> [!definition]
> Let $X$ be a [[topological space]].
> 1. The ***unreduced suspension*** of $X$ is the [[Quotient Topology|quotient space]] given by: $$\Sigma X:=I\times X / {\sim}$$where $(0,x)\sim(0,x')$ and $(1,x)\sim(1,x')$ for all $x,x'\in X$.
---
##### Properties
> [!lemma] Proposition 1
> Let $C_{+}X:=\begin{cases}[t,x]\in \Sigma X: t\geq \frac{1}{2}\}\end{cases}$. Then, we have: 
> 1. $C_{+}X$ is [[Contractible Space|contractible]].
> 2. there exists a natural isomorphism $\tilde{H}_{p}(X)\to \tilde{H}_{p+1}(\Sigma X)$. 

> [!proof]+
> Let $q:I\times X\to\Sigma X$ be the quotient function. Then, 
> 1. We define $c:C_{+}X\to C_{+}X, [t,x]\mapsto [1,x]$ be a constant map. We will show that $\text{id}_{C_{+}X}\sim c$. Let: $$F:C_{+}X\times I\to C_{+}X,\quad ([t,x],s)\mapsto [t+(1-t)s,x]$$which is well-defined as $F([1,x],s)=[1,x]=[1,x']=F([1,x'],s)$. Then, $F([t,x],0)=[t,x]$ and $F([t,x],1)=[1,x]=c([t,x])$. 
> 2. Let $A:=q\left( \left\{  \frac{1}{2}  \right\}\times X \right)\subseteq C_{+}X$. Then, $A\cong X$ and we have from the LES: $$\underbrace{ \tilde{H}_{p+1}(C_{+}X) }_{ =0 }\to H_{p+1}(C_{+}X,A)\to \tilde{H}_{p}(A)\to \underbrace{ \tilde{H}_{p}(C_{+}X) }_{ 0 }$$and $H_{p+1}(C_{+}X,A)\cong \tilde{H}_{p}(A)\cong \tilde{H}_{p}(X)$. 
>    
>    Let $U:=\{ [t,x]\in \Sigma X:t> 1-\varepsilon \}$. Then, $$H_{p}(\Sigma X,C_{+}X)\cong H_{p}(\Sigma X \backslash U,C_{+}X \backslash U)\cong H_{p}(C_{-}X,A)\cong \tilde{H}_{p-1}(X)$$where we have $(\Sigma X \backslash U,C_{+}X \backslash U)$ and $(C_{-}X,A)$ as the same homotopy type as the latter is a deformation retract of the former. Lastly, we show that: $$\underbrace{ \tilde{H}_{p}(C_{+}X) }_{ =0 }\to \tilde{H}_{p}(\Sigma X)\to H_{p}(\Sigma X,C_{+}X)\to \underbrace{ \tilde{H}_{p-1}(C_{+}X) }_{ =0 }$$is exact and hence, $\tilde{H}_{p}(\Sigma X)\cong \tilde{H}_{p-1}(X)$. The naturality follows from the naturality of each of these isomorphisms. 