#Series #Algebra 

> [!definition] Problem 1
> Let $R$ be a principal ideal domain. 
> 1. Show that every ascending chain of ideals, $I_{1}\subseteq I_{2}\subseteq\dots$ , eventually become stationary. In other words, there is a positive index $n$ such that $I_{k}=I_{n}$ for all $k\geq n$. 
> 2. Show that every irreducible element is a prime element.

We have:
1. Let $\{ I_{k} \}_{k}$ be an ascending chain of ideals. We claim that $I:=\bigcup_{k=1}^{\infty}I_{k}$ is an ideal. For $x,y\in I$, there exists $a,b\geq 1$ s.t. $x\in I_{a}$ and $y\in I_{b}$. Then, $x-y\in I_{\max\{ a,b \}}\subseteq I$. Similarly, for $r\in R$, $rx\in I_a\subseteq I$. 
   
   This means, $I=(x)$ for some $x\in R$ as $R$ is a PID. Therefore, there exists $n\geq 1$ s.t. $x\in I_{n}$. Hence, for any $k\geq n$, $x\in I_{k}$ and therefore, $I=(x)\subseteq I_{k}\subseteq I$. This shows that $I_{k}=I_{n}=I$ for all $k\geq n$.
2. Let $r\in R$ be irreducible. Then, by definition, $r\neq 0$ and $r\notin R^{*}$. Now let $a,b\in R$ s.t. $r|ab$. Then, $ab\in (r)$ and $(ab)\subseteq(r)$. However, as $R$ is PID, there exists $c\in R$ with $(c)=(ab)\subseteq(r)$, i.e. $r|c$ and $r=sc$ for some $s\in R$. From the irreducibility, $s\in R^{*}$ or $c\in R^{*}$. 
   
   If $c\in R^{*}$, then $R=(c)\subseteq(r)$ and $r\in R^{*}$, which is a contradiction. Therefore, $s\in R^{*}$. Then, $r\sim c$ and $(r)=(c)=(ab)$. This gives us $r=mab$ for some $m\in R$. As it is not possible that $a,b$ are both units as $r$ is non-unit, we have from irreducibility that either $ma\in R^{*}$ or $mb\in R^{*}$. Wlog assume that $ma\in R^{*}$. Then, $r\sim b$ and $r|b$.
---
> [!def] Problem 2
> Show that every principal ideal domain is a unique factorization domain.

Let $R$ be a PID and $r\in R$ non-zero and non-unit. Let $r_{0}=r$ and we construct the following algorithm:
1. If $r_{i}$ is irreducible, we are done.
2. If $r_{i}$ is not irreducible, $(r_{i})$ is not a maximal ideal. Then, we can find a non-zero non-unit $r_{i+1}\in R$ s.t. $(r_{i})\subsetneq(r_{i+1})\subsetneq R$. Proceed with $r_{i+1}$.

We will now show the following:
1. **For all $i$, $r_{i}=s_{i}r_{i+1}$ where $s_{i}$ is irreducible**:
   As $(r_{i})\subseteq(r_{i+1})$, there exists $s_{i}\in R$ with $r_{i}=s_{i}r_{i+1}$. We just need to show that $s_{i}$ is irreducible. If $s_{i}=0$, then $r_{i}=0$. If $s_{i}\in R^{*}$, then $r_{i}\sim r_{i+1}$ and $(r_{i})=(r_{i+1})$. Therefore, $s_{i}$ is non-zero and non-unit.


We first show that it is possible to find such $r_{i+1}$. As $R$ is a PID, there exists $r_{i+1}$ with $(r_{i})\subsetneq(r_{i+1})$. Then, as $r_{i}\neq 0$, $r_{i+1}\neq 0$. Further, there exists $s\in R$ with $r_{i}=sr_{i+1}$. 
