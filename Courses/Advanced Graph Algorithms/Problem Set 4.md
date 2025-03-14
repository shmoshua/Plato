#Definition #AGAO 

#### Exercise 1
Let $M\in \mathbb{R}^{n,n}$ be a symmetric matrix. Then, $Z=\sum_{i,\lambda_{i}\neq 0}^{}\lambda_{i}^{-1}v_{i}v_{i}^\top$ where $\lambda_{i}$ is the $i$-th eigenvalue of $M$ and $v_{i}$ is a corresponding eigenvector s.t. $V:=\{ v_{i} \}_{i}$ form an ONB.
1. The symmetry follows from the symmetry of $v_{i}v_{i}^\top$ for all $i$.
2. Let $r:= \text{rk}(M)$. Wlog we may assume that $V_{0}:=\{ v_{r+1},\dots,v_{n} \}$ forms a basis for $\text{ker }M$. Hence, we have that for any $v_{i}\in V_{0}$, we have that $Mv_{i}=0$ and $\lambda_{i}=0$. Therefore, for any $v\in \text{ker } M$, $\braket{ v , v_{i} } =0$ for any $i\leq r$. It follows that for any $v\in \text{ker } M$, $$Zv=\sum_{i,\lambda_{i}\neq 0}^{}\lambda_{i}^{-1}v_{i}\underbrace{ v_{i}^\top v }_{ =0 }= 0$$
3. From above, we know that $\{ v_{1},\dots,v_{r} \}$ span $(\text{ker }M)^{{\bot}}$ as $\{ v_{i} \}_{i}$ form an ONB. Hence, for any $v=\sum_{i\leq r}^{}a_{i}v_{i}\in (\text{ker }M)^{\bot}$, we have that: $$\begin{aligned}MZv&=M\left( \sum_{i\leq r}\lambda_{i}^{-1}v_{i}v_{i}^\top  \right)\left( \sum_{i\leq r}^{}a_{i}v_{i} \right)\\&=V\Lambda V^\top\left( \sum_{i\leq r}a_{i}\lambda_{i}^{-1}v_{i} \right)=V\Lambda \left( \sum_{i\leq r}a_{i}\lambda_{i}^{-1}e_{i} \right)=V\left( \sum_{i\leq r}a_{i}e_{i} \right) =v\end{aligned}$$
4. To show the uniqueness, we have to show that the pseudoinverse is independent of the choice of the eigenbasis. As we only use the eigenvectors that correspond to a non-zero eigenvalue, it suffices to show that the pseudoinverse is independent of the choice of the basis of $(\text{ker }M)^{\bot}$. 
   
   Let $V\in \mathbb{R}^{n,r}$ be a basis of $(\text{ker }M)^{\bot}$ and $M_{V}$ be the pseudoinverse. Then, $M=V\Lambda'V^\top$ where $\Lambda':=\Lambda_{1:r,1:r}$. We claim that: $$M^+_{V}= V(V^\top M^\top M V)^{-1}V^\top M^\top$$as: $V(V^\top M^\top M V)^{-1}V^\top M^\top=V(\Lambda'\Lambda')^{-1}\Lambda' V^\top=V(\Lambda')^{-1}V^\top=M^+_{V}$. Now, if $W\in \mathbb{R}^{n,r}$ is another basis of $(\text{ker }M)^{\bot}$, we have that there exists a change of basis $S\in \mathbb{R}^{r,r}$ with $W=VS$ and:$$\begin{aligned}M^+_{W}&=W(W^\top M^\top M W)^{-1}W^\top M^\top\\&=VS(S^\top V^\top M^\top M VS)^{-1}S^\top V^\top M^\top\\&=V( V^\top M^\top M V)^{-1}V^\top M^\top\\&=M^+_{V}\end{aligned}$$ 
   This shows the uniqueness.

---
#### Exercise 2

First, notice that: $$XYX^\top=M=M^\top=XY^\top X^\top$$As $X,X^\top$ are invertible, $Y=Y^\top$. Now, we will show that $Z$ meets the three conditions of a pseudoinverse form above for $M$. 
1. We have that: $$Z^\top=(\Pi_{M}X^{-\top}Y^+ X ^{-1}\Pi_{M})^\top=\Pi_{M}X^{-\top}Y^+ X ^{-1}\Pi_{M}=Z$$as $\Pi_{M}$ and $Y^+$ are symmetric.
2. For $v\in \text{ker}(M)$, $\Pi_{M}v=0$ and $Zv=0$. 
3. Now, first notice that $\Pi_{M}M=M$ and: $$M\Pi_{M}=M^\top\Pi_{M}^\top=(\Pi_{M}M)^\top=M^\top = M$$
   Let $v\in (\text{ker } M)^{\bot}=\text{im }M^\top=\text{im } M$. Then, $v=Mu$ for some $u\in \mathbb{R}^n$. Hence, $$MZv=\underbrace{ M\Pi_{M} }_{ =M }X^{-\top}Y^+  X ^{-1}\underbrace{ \Pi_{M}v }_{ =v=XYX^\top  u }=MX^{-\top}Y^+  YX^\top u=XYY^+  YX^\top u$$ 
   Further, notice that as $YY^+x=x$ for all $x\in \text{ker}(Y)^{\bot}=\text{im}(Y^\top)=\text{im }(Y)$ and $YY^+Y=Y$. Finally, $$MZv=XYX^\top u=Mu=v$$

This shows that $Z$ is the pseudoinverse of $M$.

---
