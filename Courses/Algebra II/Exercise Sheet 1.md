#Series #Algebra 

> [!definition] Problem 1
> Let $R$ be a principal ideal domain. 
> 1. Show that every ascending chain of ideals, $I_{1}\subseteq I_{2}\subseteq\dots$ , eventually become stationary. In other words, there is a positive index $n$ such that $I_{k}=I_{n}$ for all $k\geq n$. 
> 2. Show that every irreducible element is a prime element.

We have:
1. Let $\{ I_{k} \}_{k}$ be an ascending chain of ideals. We claim that $I:=\bigcup_{k=1}^{\infty}I_{k}$ is an ideal. For $x,y\in I$, there exists $a,b\geq 1$ s.t. $x\in I_{a}$ and $y\in I_{b}$. Then, $x-y\in I_{\max\{ a,b \}}\subseteq I$. Similarly, for $r\in R$, $rx\in I_a\subseteq I$. 
   
   This means, $I=(x)$ for some $x\in R$ as $R$ is a PID. Therefore, there exists $n\geq 1$ s.t. $x\in I_{n}$. Hence, for any $k\geq n$, $x\in I_{k}$ and therefore, $I=(x)\subseteq I_{k}\subseteq I$. This shows that $I_{k}=I_{n}=I$ for all $k\geq n$.
2. Let $r\in R$ be irreducible. Then, by definition, $r\neq 0$ and $r\notin R^{*}$. Now let $a,b\in R$ s.t. $r|ab$. Then, $rs=ab$ for some $s\in R$. From the irreducibility, $s\in R^{*}$ or $ab\in R^{*}$. If $ab\in R^{*}$, then $R=(ab)\subseteq(r)$ and $r\in R^{*}$, which is a contradiction. Therefore, $s\in R^{*}$. Now, as $r$ is irreducible, $sa\in R^{*}$ or $b\in R^{*}$. If $sa\in R^{*}$, $r\sim b$ and $r|b$. If $b\in R^{*}$, $r|sa$ and as $s\in R^{*}$, $r|a$.
---
> [!def] Problem 2
> Show that every principal ideal domain is a unique factorization domain.

Let $R$ be a PID and we define a poset with respect to inclusion:
$$\mathcal{I}:=\{ (r)\subseteq R:r\neq 0,r\notin R^{*},r \text{ has no unique factorization} \}$$
Then, we will use Zorn's lemma to show that there is a maximal element in $\mathcal{I}$. Let $\{ (r_{n}) \}_{n}\subseteq \mathcal{I}$ be an ascending chain. From 1, we know that there is $n\geq 1$ s.t. $(r_{k})=(r_{n})$ for all $k\geq n$. Therefore, $(r_{n})$ is the upper bound. Indeed, now we can use the Zorn's lemma to find a maximal element $(m)\in \mathcal{I}$. 

As $m$ is not irreducible by definition, $(m)$ is not maximal and there exists $q\in R$ s.t. $(m)\subsetneq (q)\subsetneq R$. However, we claim that $(q)\in \mathcal{I}$. As $m\neq 0$, $q\neq 0$. Further, as $(q)\neq R$, $q\notin R^{*}$. 

From 1, we know that every ascending chain $I_{1}\subseteq I$

Let $R$ be a PID and $r\in R$ non-zero and non-unit. Let $r_{0}=r$ and we construct the following algorithm:
1. If $r_{i}$ is irreducible, we are done.
2. If $r_{i}$ is not irreducible, $(r_{i})$ is not a maximal ideal. Then, we can find a non-zero non-unit $r_{i+1}\in R$ s.t. $(r_{i})\subsetneq(r_{i+1})\subsetneq R$. Proceed with $r_{i+1}$.

We will now show the following:
1. **For all $i$, $r_{i}=s_{i}r_{i+1}$ where $s_{i}$ is irreducible**:
   As $(r_{i})\subseteq(r_{i+1})$, there exists $s_{i}\in R$ with $r_{i}=s_{i}r_{i+1}$. We just need to show that $s_{i}$ is irreducible. If $s_{i}=0$, then $r_{i}=0$. If $s_{i}\in R^{*}$, then $r_{i}\sim r_{i+1}$ and $(r_{i})=(r_{i+1})$. Therefore, $s_{i}$ is non-zero and non-unit.


We first show that it is possible to find such $r_{i+1}$. As $R$ is a PID, there exists $r_{i+1}$ with $(r_{i})\subsetneq(r_{i+1})$. Then, as $r_{i}\neq 0$, $r_{i+1}\neq 0$. Further, there exists $s\in R$ with $r_{i}=sr_{i+1}$. 
