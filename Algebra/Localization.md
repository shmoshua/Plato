#Definition #Algebra 

> [!definition]
> Let $R$ be a commutative [[ring]].
> 1. A subset $S\subseteq R$ is called ***multiplicatively closed***, if $1\in S$ and $ab\in S$ for all $a,b\in S$. 
> 2. For a multiplicatively closed set $S\subseteq R$, the ***localization of $R$ at $S$*** is given by the ring: $$S^{-1}R:= (R\times S) / {\sim}$$where $(a,s)\sim(a',s')$ if and only if there exists $u\in S$ s.t. $u(as'-a's)=0$ where $\frac{a}{s}:=[(a,s)]$. The addition and multiplication are given by: $$\frac{a}{s}+\frac{a'}{s'}=\frac{as'+a's}{ss'},\quad \frac{a}{s}\cdot \frac{a'}{s'}=\frac{aa'}{ss'}$$
> 3. For a multiplicatively closed set $S\subseteq R$ and a $R$-[[module]] $M$, the ***localization of $M$ at $S$*** is given by the $S^{-1}R$-module: $$S^{-1}M:= (M\times S) / {\sim}$$where $(m,s)\sim(m',s')$ if and only if there exists $u\in S$ s.t. $u(ms'-m's)=0$ where $\frac{m}{s}:=[(m,s)]$. The addition and multiplication are given by: $$\frac{m}{s}+\frac{m'}{s'}=\frac{ms'+m's}{ss'},\quad \frac{a}{s}\cdot \frac{m'}{s'}=\frac{am'}{ss'}$$
> 4. For a multiplicatively closed set $S\subseteq R$ and a homomorphism $\varphi:M\to N$ of $R$-modules, the ***localization of $\varphi$ at $S$*** is given by: $$S^{-1}\varphi:S^{-1}M\to S^{-1}N,\quad S^{-1}\varphi\left( \frac{m}{s} \right)=\frac{\varphi(m)}{s}$$

^e626db

- **Remark**: If $0\in S$, then $S^{-1}R=0$ by taking $u=0$ all the time. ^59501f

---
##### Properties
> [!lemma] Proposition 1
> Let $R$ be a ring and $S\subseteq R$ a multiplicatively closed subset. Further, let $M$ be a  $R$-module. Then, 
> 1. $\sim$ is an equivalence relation. 
> 2. $S^{-1}R$ is a ring.
> 3. $S^{-1}R$ is a $R$-[[algebra]].
> 4. $S^{-1}M$ is a $S^{-1}R$-module.

^321ab4

> [!proof]-
> We have that:
> 1. $\sim$ is clearly reflexive and symmetric. For transitivity, if $(a,s)\sim(a',s')$ and $(a',s')\sim(a'',s'')$, with $u,v\in S$ s.t. $u(as'-a's)=v(a's''-a''s')=0$. Then, $$\begin{align}s'uv(as''-a''s)&=s'uvas''-s'uva''s-uvs''a's+uvs''a's\\&=s''v\cdot u(as'-a's)+su\cdot v(a's''-a''s')=0\end{align}$$where $s'uv\in S$ as it is multiplicatively closed.
> 2. If $(a,s)\sim (a'',s'')$ with $u(as''-a''s)=0$, then: $$u((as'+a's)(s''s')-(a''s'+a's'')(ss'))=(s')^{2}\cdot u(as''-a''s)=0$$and $$u((aa')(s''s')-(a''a')(ss'))=a's'\cdot  u(as''-a''s)=0$$
> 3. Given by $\varphi:R\to S^{-1}R, a\mapsto \frac{a}{1}$. This is injective only if $S$ doesn't contain any zero divisors. 

^b7609c

---
> [!lemma] Proposition 2 (Ideals in Localizations)
> Let $S$ be a multiplicatively closed subset of a ring $R$. Consider the homomorphism $\varphi:R\to S^{-1}R$.
> 1. for any $I\unlhd R$, $I^e=(\varphi(I))=\left\{  \frac{a}{s}:a\in I,s\in S  \right\}$.
> 2. for any $I\unlhd S^{-1}R$, $(I^c)^e=I$. 
> 3. [[Ring Homomorphism|contractions]] and [[Ring Homomorphism|extensions]] give a 1:1-correspondence: $$\begin{align}\{ \text{Prime ideals in }S^{-1}R \}&\leftrightarrow \{ \text{Prime ideals } I\text{ in }R\text{ with }I\cap S=\varnothing\}\\I&\mapsto I^c\\I^e&\leftarrow I\end{align}$$

^68bf11

> [!proof]-
> We have:
> 1. As $\frac{1}{s}\in S^{-1}R$ for all $s\in S$ and $I^e$ is an ideal, $\frac{a}{s}:=\frac{1}{s}\cdot\varphi(a)\in I^e$. However, for the other direction, for any $a\in I$, $\varphi(a)$ is contained in the RHS. This proves the statement as RHS is an ideal.
> 2. By [[Ring Homomorphism|Proposition 4]] it suffices to show that $(I^c)^e\supseteq I$. Let $\frac{a}{s}\in I$. Then, $a\in \varphi ^{-1}(I)=I^c$ since $\varphi(a)=\frac{a}{1}=s\cdot \frac{a}{s}\in I$. Applying 1 to $I^c$, we have that: $\frac{a}{s}\in (I^c)^e$. 
> 3. We first check that $\to$ is well-defined. If $I$ is a prime ideal in $S^{-1}R$, then $I^c$ is a prime ideal in $R$ by [[Prime Ideal|Proposition 2.1]]. Further $S$ are all mapped to units in by $\varphi$ but $I^c$ cannot contain any units. 
>    
>    To check that $\gets$ is well-defined, let $I\unlhd R$ be prime with $I\cap S=\varnothing$. Let $\frac{a}{s}, \frac{b}{t}\in S^{-1}R$ with $\frac{ab}{st}\in I^e$. Then, by 1, $\frac{ab}{st}=\frac{c}{u}$ for some $c\in I$ and $u\in S$, i.e. there exists some $v\in S$ s.t. $v(abu-stc)=0$. This implies that $vabu\in I$. Since $I$ is prime, one of these 4 factors have to lie in $I$, but as $u,v\in S$, either $a\in I$ or $b\in I$. Hence, $\frac{a}{s}\in I^e$ or $\frac{b}{t}\in I^e$.
>    
>    Now, from 2, $(I^c)^e=I$ and we are left to show that $(I^e)^c=I$ for all prime $I\unlhd R$ with $I\cap S=\varnothing$. From [[Ring Homomorphism|Proposition 4]], we only need to show $\subseteq$. Let $a\in (I^e)^c$, i.e. $\varphi(a)=\frac{a}{1}\in I^e$. Then, by $a$, there exists $b\in I$ and $s\in S$ s.t. $\frac{a}{1}=\frac{b}{s}$, i.e. there exists $u\in S$ with $u(as-b)$. hence, $uas\in I$ and as $u,s\in S$ and $I$ is prime, we have that $a\in I$. 

^c88fd9

- **Remark**: Applying 3 to localization at prime ideals, we have a correspondence between prime ideals in $R_{P}$ and prime ideals $I$ in $R$ with $I\subseteq P$.  ^56eb95
---
> [!lemma] Proposition 3 (Universal Property)
> Let $S$ be a multiplicatively closed subset of $R$. 
> 1. for a homomorphism $\alpha:R\to R'$ s.t. $\alpha(S)\subseteq (R')^\times$, there exists a unique ring homomorphism $\varphi:S^{-1}R\to R'$ s.t. $\varphi\left( \frac{r}{1} \right)=\alpha(r)$ for all $r\in R$.

^7baea4

> [!proof]-
> We define: $$\varphi:S^{-1}R\to R',\quad \frac{r}{s}\mapsto \alpha(r)\alpha(s)^{-1}$$We first show that this is well-defined. If $\frac{r}{s}=\frac{r'}{s'}$ s.t. $u(rs'-sr ')=0$ for some $u\in S$: $$\begin{align}\alpha(r)\alpha(s)^{-1}&=\alpha(u)^{-1}\alpha(u)\alpha(r)\alpha(s')\alpha(s')^{-1}\alpha(s)^{-1}\\&=\alpha(u)^{-1}\alpha(u)\alpha(s)\alpha(r')\alpha(s')^{-1}\alpha(s)^{-1}\\&=\alpha(r')\alpha(s')^{-1}\end{align}$$This is a ring homomorphism as it is defined through homomorphisms. 
> 
> To show uniqueness, let $\varphi'$ be another homomorphism with the same property. Then, $$\varphi'\left( \frac{r}{s} \right)=\varphi'\left( \frac{r}{1} \right)\varphi'\left( \frac{1}{s} \right)=\alpha(r)\alpha(s)^{-1}=\varphi\left( \frac{r}{s} \right) $$where $1=\alpha(1)=\varphi'\left( \frac{1}{1} \right)=\varphi'\left( \frac{1}{s} \right)\varphi'\left( \frac{s}{1} \right)=\varphi'\left( \frac{1}{s} \right)\alpha(s)$ hence $\varphi'\left( \frac{1}{s} \right)=\alpha(s)^{-1}$.

^e819db

---
> [!lemma] Proposition 4 (Localization is a Tensor Product)
> Let $S$ be a multiplicatively closed subset of $R$ and $M$ a $R$-module. Then, 
> 1. $S^{-1}M\cong M\otimes_{R} S^{-1}R$

^35ae68

> [!proof]-
> Consider the homomorphism: $$\varphi:S^{-1}M\to M \otimes _{R}S^{-1}R,\quad \frac{m}{s}\mapsto m\otimes  \frac{1}{s}$$This is well-defined as if $\frac{m}{s}=\frac{m'}{s'}$ with $u(ms'-m's)=0$ for $u\in S$, we have that: $$m\otimes  \frac{1}{s}=m\otimes \frac{us'}{uss'}=us'm\otimes  \frac{1}{uss'}=usm'\otimes  \frac{1}{uss'}=m'\otimes \frac{1}{s'} $$Similarly, $M\times S^{-1}R\to S^{-1}M,\left( m, \frac{a}{s} \right)\mapsto \frac{am}{s}$ is a bilinear map and this extends to a map $\psi :M\otimes S^{-1}R\to S^{-1}M$, where $\varphi$ and $\psi$ are inverses. This map is well-defined as for $\frac{a}{s}=\frac{a'}{s'}$ with $u(as'-a's)$, $u(ams'-a'ms)=0$.

^ef7c7d

- **Remark**: This shows the localization of homomorphisms as $\varphi \otimes \text{id}:M\otimes S^{-1}R\to N\otimes S^{-1}N$. ^07bb27
---
> [!lemma] Proposition 5 (Localization is Exact)
> Let $0\to M_{1}\xrightarrow{\varphi} M_{2}\xrightarrow{\psi} M_{3}\to 0$ be a [[Exact Sequence|SES]]. Then, for any multiplicatively closed $S\subseteq R$, $$0\to S^{-1}M_{1}\xrightarrow{S^{-1}\varphi}S^{-1}M_{2}\xrightarrow{S^{-1}\psi}S^{-1}M_{3}\to 0$$is also exact.

^4d7290

> [!proof]-
> By Proposition 4 and right exactness of tensor products, it is left to show that $S^{-1}\varphi$ is injective if $\varphi$ is. 
> 
> Let $\frac{m}{s}\in S^{-1}M_{1}$ s.t. $S^{-1}\varphi\left( \frac{m}{s} \right)=\frac{\varphi(m)}{s}=0$. Then, there exists $u\in S$ with $u\varphi(m)=\varphi(um)=0$. However, as $\varphi$ is injective, $um=0$. Hence, $\frac{m}{s}=0$. 

^9b7b77

---
> [!lemma] Corollary 6
> Let $S$ be a multiplicatively closed set of $R$. Then,
> 1. for any homomorphism $\varphi:M\to N$ of $R$-modules, $$\text{ker}(S^{-1}\varphi)=S^{-1}\text{ker }\varphi,\quad \text{im}(S^{-1}\varphi)=S^{-1}\text{im }\varphi$$
> 	In particular, if $\varphi$ is injective/surjective, so is $S^{-1}\varphi$. 
> 2. If $N\leq M$, then $S^{-1}N\leq S^{-1}M$ in a natural way.
> 3. If $N\leq M$, then $S^{-1}(M / N)\cong S^{-1}M / S ^{-1}N$.
> 4. for any $R$-modules $M,N$, $S^{-1}(M\oplus N)\cong S^{-1}M\oplus S^{-1}N$.
> 5. for $M_{1},M_{2}\leq M$, $S^{-1}(M_{1}+M_{2})\cong S^{-1}M_{1}+S^{-1}M_{2}$
> 6. for $M_{1},M_{2}\leq M$, $S^{-1}(M_{1}\cap M_{2})\cong S^{-1}M_{1}\cap S^{-1}M_{2}$
> 7. for $I\unlhd R$, $S^{-1}\sqrt{ I }\cong  \sqrt{ S^{-1}I }$
> 8. if $R$ is [[Noetherian and Artinian Module|Noetherian/Artinian]], then so is $S^{-1}R$.

^66b9c4

> [!proof]+
> We have:
> 1. by Proposition 5, localizing $0\to \text{ker }\varphi\to M\to \text{im }\varphi \to 0$, we get: $$0\to S^{-1}\text{ker }\varphi\to S^{-1}M\to S^{-1}\text{im }\varphi \to 0$$but then this means that $\text{ker }(S^{-1}\varphi)=S^{-1}\text{ker }\varphi$ and $\text{im }(S^{-1}\varphi)=S^{-1}\text{im }\varphi$.
> 2. We localize $0\to N\to M \to M / N\to 0$. Then, $$0\to S^{-1}N\to S^{-1}M\to S ^{-1}(M / N)\to 0$$and $S^{-1}(M / N)\cong S^{-1}M / S^{-1} N$.
> 3. Proven above. 
> 4. $S^{-1}(M\oplus N)\cong (M\oplus N)\otimes_{R}S^{-1}R\cong (M\otimes_{R}S^{-1}R)\oplus(N\otimes_{R}S^{-1}R)=S^{-1}M\oplus S^{-1}N$.
> 5. Consider the exact sequence $0\to M_{1}\cap M_{2}\to M_{1}\oplus M_{2} \to M_{1}+M_{2}\to 0$. Then, $$0\to S^{-1}(M_{1}\cap M_{2})\to S^{-1}M\oplus S^{-1}N\to S^{-1}(M_{1}+M_{2})\to 0$$This shows both 5 and 6.
> 6. We have:
> 	$$\varphi:S^{-1}\sqrt{ I }\to \sqrt{ S^{-1}I },\quad \frac{a}{s}\mapsto \frac{a}{s}$$Let $a^n=0$. Then, $\left( \frac{a}{s} \right)^n=\frac{a^n}{s^n}=0$. One easily sees that this is an isomorphism.
> 7. Let $M_{0}\subseteq M_{1}\subseteq \dots$ be an ascending chain of ideals of $S^{-1}R$. Then, we have that: 

^15a3cb

- **Remark**: Localization doesn't commute with arbitrary intersections: For $S:=\mathbb{Z} \backslash \{ 0 \}$, $$S^{-1}\left( \bigcap_{n\geq 2}^{}n\mathbb{Z} \right)=S^{-1}(0)=0\neq \bigcap_{n\geq 2}^{}S^{-1}(n\mathbb{Z})\ni 1$$ ^86ca13
---
> [!lemma] Proposition 7 (Local Properties)
> Let $R$ be a ring.
> 1. $M$ is a $R$-module with $M_{p} =0$ for all maximal $P\unlhd R$ if and only if $M=0$.
> 2. $0\to (M_{1})_{P}\to(M_{2})_{P}\to (M_{3})_{P} \to 0$ is exact for all maximal $P\unlhd R$, if and only if: $$0 \to M_{1}\to M_{2}\to M_{3}\to 0$$is exact.
> 3. For two ideals $I,J\unlhd R$, $I_{P}\subseteq J_{P}$ for all maximal $P\unlhd R$ if and only if $I\subseteq J$.
> 4. $R$ is [[Nilradical|reduced]] if and only if $R_{P}$ is reduced for all maximal $P\unlhd R$. 

^48623c

> [!proof]-
> We have:
> 1. Assume $M\neq 0$. If we choose $m\neq 0\in M$, then the [[annihilator]] $\text{Ann}(m)$ doesn't contain $1$ and is a proper ideal, hence contained in a maximal ideal $P$. Hence, for all $u\in R \backslash P$, we have that $u\notin \text{Ann}(m)$, i.e. $um\neq 0$ in $M$. Hence, $\frac{m}{1}$ is non-zero in $M_{P}$ and $M_{P}\neq 0$.
>    
>    Conversely, if $M=0$, then $M_{P} = 0$.
> 2. We show that if $L_{P}\xrightarrow{\varphi_{P}}M_{P}\xrightarrow{\psi_{P}}N_{P}$ is exact for all maximal $P\unlhd R$ then $L\to M\to N$ is exact.
>    
>    First, note that: $$\begin{align}(\psi(\varphi(L)))_{P}&=\left\{  \frac{\psi(\varphi(m))}{s}:m\in L,s\in S  \right\}=\left\{  \psi_{P}\left( \varphi_{P}\left( \frac{m}{s} \right) \right):m\in L,s\in S  \right\}\\&=\psi_{P}(\varphi_{P}(L_{P}))=0\end{align}$$Hence, by 1, $\psi(\varphi(L))=0$, i.e. $\text{im }\varphi \subseteq \text{ker }\psi$.
>    
>    Now, by considering $\text{ker }\psi / \text{im }\varphi$, we get: $$(\text{ker }\psi / \text{im }\varphi)_{P}\cong (\text{ker }\psi)_{P} / (\text{im }\varphi)_{P}\cong \text{ker }\psi_{P} / \text{im }\varphi_{P}=0$$This means $\text{ker }\psi / \text{im }\varphi=0$ by 1 again. hence, $\text{ker }\psi=\text{im }\varphi$, which proves the statement.
>    
>    The converse is shown by Proposition 5.
> 1. Consider the exact sequence $0\to I_{P}\cap J_{P}\to I_{P}\oplus J_{P} \to I_{P}+J_{P} \to 0$. Then, we have: $$0 \to I_{P}\to (I\oplus J)_{P}\to (I+J)_{P}\to 0$$for all maximal $P\unlhd R$ and by 2, $0\to I\to I\oplus J\to I+J\to 0$ which shows that $I\subseteq J$. 
>    
>    The converse holds by Corollary 6.2
> 2. $R$ being reduced is equivalent to $\sqrt{ (0) }\subseteq(0)$, which are two ideals in $R$. Hence, by 3, it suffices to show that $(0)_{P}$ coincides with the $(0)$ of $R_{P}$. However this is obvious. 
>    

^6a5807

- **Corollary**: A homomorphism $\varphi:M\to N$ is injective/surjective if and only if $\varphi_{P}:M_{P}\to N_{P}$ is, for all maximal $P\unlhd R$. ^a19d79

---
##### Examples
> [!h] Example 1
> We have that:
> 1. for $S:=\{ 1 \}$, $S^{-1}R\cong R$.
> 2. let $S$ be the set of non-zero divisors of $R$. Then, $S$ is multiplicatively closed and if $R$ is an [[integral domain]], i.e. $S=R \backslash\{ 0 \}$, then 
> 	1. $S^{-1}R\cong \text{Quot}(R)$ the [[quotient field]].
> 	2. for any multiplicatively closed $T\subseteq S$, $T^{-1}R$ is a subring of $\text{Quot}(R)$. 
> 3. Let $S:=\{ a^n:n\in \mathbb{N} \}$ for a fixed element $a\in R$. Then, $S^{-1}R=:R_{a}$ and is called the ***localization of $R$ at $a$.***
> 4. For a [[prime ideal]] $P\unlhd R$, $S:= R \backslash P$ is multiplicatively closed. Then, $S^{-1}R=:R_{P}$ and is called ***localization of $R$ at $P$***.
> 5. $\mathbb{Z}_{(p)}$ is the localization of $R$ at the prime ideal $(p)$ for $p\in \mathbb{Z}$ prime. 

^ea6d10

---
> [!h] Example 2 (Saturation)
> Let $S$ be a multiplicatively closed set in $R$. Then,
> 1. the ***saturation*** of $S$, defined as $\overline{S}:=\{ s\in R:as\in S\text{ for some }a\in R \}$ is also multiplicatively closed.
> 2. $\overline{S}^{-1}R\cong S^{-1}R$.

^a105c9

> [!proof]-
> We have that:
> 1. Let $s,s'\in \overline{S}$. Then, there exists $a,a'\in R$ s.t. $as,a's'\in S$. Hence, $$aa'ss'\in S \implies ss'\in \overline{S}$$
> 2. We have that: $$\varphi:\overline{S}^{-1}R\to S^{-1}R,\quad \frac{r}{s}\mapsto \frac{ar}{as}$$where $a\in R$ s.t. $as\in S$. This is well-defined as for $\frac{r}{s}=\frac{r'}{s'}$ with $u(rs'-r's)=0$ with $u\in \overline{S}$ s.t. $as\in S$ and $a's'\in S$, we have: $$bu(ara's'-a'r'as)=aa'b\cdot u(rs')=0$$where $bu\in S$. Now, $\varphi$ is surjective as $S^{-1}R$ injects into $\overline{S}^{-1}R$. To show the injectivity, let $\varphi\left( \frac{r}{s} \right)=\frac{ar}{as}=\frac{0}{1}$, i.e. $uar=0$ for some $u\in S$. Then, $$ua(r-0)=0$$and $\frac{r}{s}=0$. 

^200add

---
> [!h] Example 3
> Let $S\subseteq R$ be multiplicatively closed and $I\unlhd R$. Then, 
> 1. $S^{-1}I=I^e$ given by $\varphi:R\to S^{-1}R,a\mapsto \frac{a}{1}$.

^6871e3

---
> [!h] Example 4 (Rq/Pq)
> Let $P,Q\unlhd R$ be maximal ideals. Then, 
> 1. $R_{Q} / P_{Q}$ is a $R_{Q}$-module and $R_{Q} / P_{Q}\cong (R / P)_{Q}$. 
> 2. if $P\neq Q$, then $R_{Q} / P_{Q} = 0$.
> 3. if $P=Q$, $R_{P} / P_{P}\cong R / P$.

^30c1ef

> [!proof]-
> We have:
> 1. This holds by Corollary 6.3.
> 2. Since $P$ is maximal $P\nsubseteq Q$ and there exists $a\in P \backslash Q$. Then, $1=\frac{a}{a}\in P_{Q}$. Hence, $P_{Q}=R_{Q}$and $R_{Q} / P_{Q}=0$.
> 3. Consider: $$\varphi:R / P\to R_{P} / P_{P},\quad \overline{a}\mapsto \overline{\left( \frac{a}{1} \right)}$$Now, consider the morphism $R\to R / P,a\mapsto \overline{a}$ which sends $R \backslash P$ to units as $R / P$ is a field. Hence, it passes to a homomorphism: $$\psi: R_{P}\to R / P,\quad \frac{a}{s}\mapsto \overline{s} ^{-1}\overline{a}$$by the universal property. But $P_{P}\subseteq \text{ker }\psi$ and hence, we get a map: $$\overline{\psi}:R_{P} / P_{P}\to R / P,\quad \overline{\left( \frac{a}{s} \right)}\mapsto \overline{s}^{-1}\overline{a}$$which is a inverse to $\varphi$.

^9b8442

---
