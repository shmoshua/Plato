1. We have that: $$\mathbf{1}\oplus  a\otimes a^{*}=\mathbf{1}\oplus  a\otimes  \bigoplus _{n=0}^\infty a^{\otimes  n}=a^{\otimes  0}\oplus    \bigoplus _{n=0}^\infty a^{\otimes  n+1}=a^{\otimes  0}\oplus    \bigoplus _{n=1}^\infty a^{\otimes  n}=\bigoplus _{n=0}^\infty a^{\otimes  n}=a^{*}$$
2. Let $a<0$. Then, we have that: $$a^{*}=\bigoplus_{n=0}^\infty na=\log \left( \sum_{n=0}^{\infty}\exp(a)^n \right)=\log \left( \frac{1}{1-\exp(a)} \right)=-\log(1-\exp(a)) $$
   We truly have that: $$0\oplus _{\log}(a-\log(1-\exp(a)))=\log\left( 1+\frac{\exp(a)}{1-\exp(a)}\right)=\log\left( \frac{1}{1-\exp(a)} \right)=-\log(1-\exp(a))$$
3. We have that again for $a<0$ and $b\in \mathbb{R}$: $$\braket{ a , b } ^{*}=\bigoplus _{n=0}^\infty \braket{ a , b } ^{\otimes  n}=\bigoplus _{n=0}^\infty \left\langle a^n , b\cdot \frac{d}{da}a^n \right\rangle=\left\langle \sum_{n=0}^{\infty}a^n, b\cdot  \frac{d}{dt}\sum_{n=0}^\infty a^{n}\right\rangle =\left\langle \frac{1}{1-a}, \frac{b}{(1-a)^2}\right\rangle $$and $$\braket{ 1 , 0 } \oplus \braket{ a , b } \otimes  \left\langle \frac{1}{1-a} ,\frac{b}{(1-a)^2}  \right\rangle=\braket{ 1 , 0 } \oplus \left\langle \frac{a}{1-a}, \frac{ab+(1-a)b}{(1-a)^2}  \right\rangle=\left\langle \frac{1}{1-a}, \frac{b}{(1-a)^2}  \right\rangle$$
4. We have that for all $A,B,C\in 2^{\Sigma ^{*}}$
	1. $A\cup(B\cup C)=(A\cup B)\cup C$.
	2. $\varnothing\cup A=A=A\cup \varnothing$.
	3. $A\cup B = B \cup A$
	4. $\begin{aligned}A\otimes(B\otimes C)&=\{ a\circ z:a\in A,z\in B\otimes C \}=\{ a\circ b\circ c:a\in A,b\in B,c\in C  \}\\&=\{ z\circ c:z\in A\otimes B,c\in C  \}=(A\otimes B)\otimes C\end{aligned}$
	5. $A\otimes \{ \varepsilon \}=\{ a\circ \varepsilon : a\in A \}=\{ a : a \in A \}=\{ \varepsilon \circ a : a\in A \}=\{ \varepsilon \}\otimes A$.
	6. $A\otimes(B\cup C)=\{ a\circ z:a \in A,z\in B\cup C \}=\{ a \circ z : a\in A,z \in B \}\cup \{ a \circ z:a \in A,z \in C \}=A\otimes B\cup A\otimes C$.
	7. $(B\cup C)\otimes A =\{ z\circ a : z\in B\cup C, a\in A \}=\{ z\circ a:z \in B,a\in A \}\cup \{ z \circ a:z\in C, a\in A \}=B\otimes A\cup C\otimes A$
	8. $A\otimes \varnothing=\{ a \circ b:a\in A,b\in \varnothing \}=\varnothing$. $\varnothing \otimes A=\varnothing$.
	
	To find a Kleene star, we have: $$A^{*}:=\bigcup_{n=0}^{\infty}A^n$$which is precisely the Kleene closure. 

##### Problem 2
1. Let $a\geq 0$. We have that $\min\{ 0,a \}=0$. Hence, the tropical semiring is 0-closed. Similarly, for $a\leq 0$, $\max\{ 0,a \}=0$. Hence, the arctic semiring is 0-closed.
2. We show this by induction over $n$. If $n=1$, every path of length one is an edge and the statement is true by definition. For $n\geq 2$, we have to now show that for any $i,k\in[N]$, \
   We have that: $$\begin{aligned}(\mathbf{M}^n)_{ik}&=(\mathbf{M}^{n-1}\otimes  \mathbf{M})_{ik}\\&=\bigoplus _{j\in[N]}((\mathbf{M}^{n-1})_{ij}\otimes  \mathbf{M}_{jk})\\&=\bigoplus _{j\in[N]}\left(\left(  \bigoplus_{\pi\in \Pi_{ij}(n)}w(\pi) \right)  \otimes  \mathbf{M}_{jk} \right) \end{aligned}$$If $\mathbf{M}_{jk}=0$ then by annihilation, the term is 0. Hence, $$\begin{aligned}(\mathbf{M}^n)_{ik}&=\bigoplus _{j: jk\in E(\mathcal{G})}\left(\left(  \bigoplus_{\pi\in \Pi_{ij}(n-1)}w(\pi) \right)  \otimes  w_{jk} \right) \\&=\bigoplus _{j: jk\in E(\mathcal{G})}\left(  \bigoplus_{\pi\in \Pi_{ij}(n-1)}\bigotimes_{i=1}^{n-1} w_{\pi(i-1),\pi(i)}\otimes  w_{jk}    \right) 
   \\&=\bigoplus _{j: jk\in E(\mathcal{G})}\left(  \bigoplus_{\pi\in \Pi_{ij}(n-1)}\bigotimes_{i=1}^{n-1} w_{\pi(i-1),\pi(i)}\otimes  w_{jk}    \right) \end{aligned}$$
   We have
$$\begin{aligned}
\bigoplus_{\pi\in \Pi_{uv}(n)}w(\pi)&=\bigoplus_{\pi\in \Pi_{uv}(n)}\bigotimes _{i\in[n]}w_{\pi(i-1),\pi(i)}\\&=\bigoplus_{\pi\in \Pi_{uv}(n)}\bigoplus _{x\in[N]}\bigotimes _{i\in[n-1]}w_{\pi(i-1),\pi(i)} \otimes  w_{x,v}\otimes  1_{\pi(n-1)=x}\\&=\bigoplus _{x\in[N]}\bigoplus_{\pi\in \Pi_{uv}(n)}\bigotimes _{i\in[n-1]}w_{\pi(i-1),\pi(i)} \otimes  w_{v,\pi(i)}\otimes  1_{\pi(n-1)=v}
\end{aligned}$$

Note that $\Pi_{uv}(n)=\bigsqcup_{x \in [N]: x\to v \in E(\mathcal{G})}\{ \pi \circ (x \to v):\pi\in  \Pi_{ux}(n-1) \}$. Therefore, $$\begin{aligned}\bigoplus _{\pi\in \Pi_{uv}(n)}w(\pi)&=\bigoplus_{x\in [N]}  \left( \left( \bigoplus_{\pi\in \Pi_{ux}(n-1)} w(\pi)\otimes w_{xv}  \right) \otimes  \mathbb{1}_{x\to v \in E( \mathcal{G} )} \right)\\&=\bigoplus_{x\in [N]}  \left( \left( \bigoplus_{\pi\in \Pi_{ux}(n-1)} w(\pi)  \right) \otimes w_{xv}\otimes  \mathbb{1}_{x\to v \in E( \mathcal{G} )} \right) \\&=\bigoplus_{x\in [N]}  \left( \left( \bigoplus_{\pi\in \Pi_{ux}(n-1)} w(\pi)  \right) \otimes \mathbf{M}_{xv}\right) \\&=\bigoplus_{x\in [N]}  \left( (\mathbf{M}^{n-1})_{ux} \otimes \mathbf{M}_{xv}\right)\\&=(\mathbf{M}^{n-1}\otimes  \mathbf{ M})_{uv}\\&=(\mathbf{M}^n)_{uv} \end{aligned}$$
3. Let $\pi$ be a path with a cycle $C$. Then we can decompose the path into $\pi=\pi_{1} \circ C \circ \pi_{2}$. We will show that: $$w(\pi)\oplus  w(\pi_{1} \circ   \pi_{2})=w(\pi_{1} \circ  \pi_{2})$$This follows from: $$\begin{aligned}w(\pi)\oplus w(\pi_{1} \circ  \pi_{2})&=(w(\pi_{1})\otimes  w(C)\otimes  w(\pi_{2}))\oplus (w(\pi_{1})\otimes  w(\pi_{2}))\\&=(w(\pi_{1})\otimes  w(C)\otimes  w(\pi_{2}))\oplus (w(\pi_{1})\otimes  \mathbf{1}\otimes  w(\pi_{2}))\\&=w(\pi_{1})\otimes  (\mathbf{1}\oplus w(C))\otimes  w(\pi_{2})\\&=w(\pi_{1})\otimes  \mathbf{1}\otimes  w(\pi_{2})\\&=w(\pi_{1}\circ  \pi_{2})\end{aligned}$$
   Let $\pi$ now be a path of length $\geq N$. As we have at most $N$ vertices, $\pi$ contains at least one cycle. However, as all simple paths, i.e. paths without cycles, have length at most $\le N-1$, by iteratively removing cycles, there exists a subpath $\pi'$ with length $\le N-1$ s.t. $w(\pi)\oplus w(\pi')=w(\pi')$. This shows the statement.
4. We have from 3 that: $$(\mathbf{M}^{*})_{ij}=\bigoplus _{n\in{0}}^\infty \bigoplus _{\pi\in \Pi^n(i,j)}w(\pi)=\bigoplus _{n=0}^{N-1} \bigoplus _{\pi\in \Pi^n(i,j)}w(\pi)=\bigoplus _{n=0}^{N-1} (\mathbf{M}^n)_{ij}=\left( \bigoplus _{n=0}^{N-1} \mathbf{ M}^n \right)_{ij} $$
5. hihi
6. We have that: $$a\oplus a = (a\otimes  \mathbf{1})\oplus  (a\otimes  \mathbf{ 1})=a\otimes  (\mathbf{ 1}\oplus \mathbf{1})=a\otimes  \mathbf{ 1}=a$$
7. We show this by induction. For $K=0$, we have that both sides are $\mathbf{I}$. For $K\geq 1$, we have: $$\begin{aligned}(\mathbf{I}\oplus \mathbf{M})^K&=\left( \bigoplus _{n=0}^{K-1}\mathbf{M}^n \right) \otimes (\mathbf{I}\oplus  \mathbf{M})\\&=\left( \left( \bigoplus _{n=0}^{K-1}\mathbf{M}^n \right)\otimes  \mathbf{I} \right)  \oplus \left( \left( \bigoplus _{n=0}^{K-1}\mathbf{M}^n \right) \otimes  \mathbf{ M} \right) \\&=\left( \bigoplus _{n=0}^{K-1}\mathbf{M}^n \right)  \oplus \left( \bigoplus _{n=0}^{K-1}\mathbf{M}^{n+1} \right)  \\&=\left( \bigoplus _{n=0}^{K-1}\mathbf{M}^n \right)  \oplus \left( \bigoplus _{n=1}^{K}\mathbf{M}^{n} \right) \\&=\mathbf{I}\oplus\underbrace{  \mathbf{M}\oplus  \mathbf{ M} }_{ =\mathbf{M} }\oplus \underbrace{ \mathbf{M}^2\oplus  \mathbf{M}^2 }_{ =\mathbf{M}^2 }\oplus \dots \oplus  \underbrace{ \mathbf{ M}^{K-1}\oplus  \mathbf{ M}^{K-1}  }_{ =\mathbf{M}^{K-1} }\oplus  \mathbf{ M}^K\\&=\bigoplus _{n=0}^{K}\mathbf{ M}^n \end{aligned}$$ 
8. Let $\mathbf{A}=\mathbf{U\Sigma V}^\top$ be the SVD of $\mathbf{ A}$. Then, let $\mathbf{ V}=[\mathbf{v}_{1}|\dots|\mathbf{v}_{n}]$. We have that: $$\|\mathbf{A}\|_{2}\ge\frac{\left\| \mathbf{Av}_{1} \right\|_{2}}{\|\mathbf{v}_{1}\|_{2}}=\frac{\left\| \mathbf{U\Sigma V^\top v}_{1} \right\|_{2}}{\|\mathbf{v}_{1}\|_{2}}=\sigma_{\max}(\mathbf{A})\frac{\left\| \mathbf{u}_{1} \right\|_{2}}{\|\mathbf{v}\|_{2}}=\sigma_{\max}(\mathbf{A}) $$We have that:, $$\left\| \mathbf{A} \right\| _{2}=\sup_{\mathbf{x}\ne \mathbf{0}}\frac{\left\| \mathbf{U\Sigma V^\top x} \right\|_{2}}{\|\mathbf{x}\|_{2}} =\sup_{\mathbf{x}\ne \mathbf{0}}\frac{\left\| \mathbf{\Sigma V^\top x} \right\|_{2}}{\|\mathbf{x}\|_{2}}  =\sup_{\mathbf{y}\ne \mathbf{0}}\frac{\left\| \mathbf{\Sigma y} \right\|_{2}}{\|\mathbf{Vy}\|_{2}} =\sup_{\mathbf{y}\ne \mathbf{0}}\frac{\left\| \mathbf{\Sigma y} \right\|_{2}}{\|\mathbf{y}\|_{2}}=\left\| \mathbf{\Sigma} \right\| _{2} $$
   Now, $$\left\| \mathbf{\Sigma} \right\|_{2}\ge \|\mathbf{\Sigma}\mathbf{e}_{1}\|_{2}=\sigma_{\max}(\mathbf{A}) $$However, for any $\mathbf{x}\ne \mathbf{0}$:$$\left\| \mathbf{\Sigma}\mathbf{x} \right\|_{2}^2=\sum_{i}^{}\sigma_{i}^{2} x_{i}^{2}\le \sigma^{2}_{\max}(\mathbf{A})\sum_{i}^{}x^{2}_{i}= \sigma^{2}_{\max}(\mathbf{A})\|\mathbf{x}\|^{2}_{2}$$
   9. Assume that $\sigma_{\max}(\mathbf{A})<1$. We have that by defintion, $\left\| \mathbf{ABx} \right\|\leq \left\| \mathbf{ A} \right\|_{2}\left\| \mathbf{Bx} \right\|_{2}$ and: $$\left\| \mathbf{A\mathbf{B}} \right\|_{2}=\sup_{\mathbf{x}\ne \mathbf{0}} \frac{\left\| \mathbf{ABx} \right\|_{2}}{\|\mathbf{x}\|_{2}} \leq \left\| \mathbf{A} \right\| \sup_{\mathbf{x}\ne \mathbf{0}} \frac{\left\| \mathbf{Bx} \right\|_{2}}{\|\mathbf{x}\|_{2}}=\left\| \mathbf{A} \right\| _{2}\left\| \mathbf{B} \right\| _{2} $$Therefore,$$\left\| \mathbf{A^{*}}-\sum_{n=0}^{K}\mathbf{A}^n \right\|_{2}=\left\| \sum_{n=K+1}^{\infty}\mathbf{A}^n \right\| _{2}\leq \sum_{n=K+1}^{\infty}\left\| \mathbf{A}^n \right\| _{2}\leq \sum_{n=K+1}^{\infty}\left\| \mathbf{A} \right\| ^n_{2}=\sum_{n=K+1}^{\infty}\sigma_{\max}(\mathbf{A})^n=\frac{\sigma_{\max}(\mathbf{A})^{K+1}}{1-\sigma_{\max}(\mathbf{A})}$$This shows that $\sum_{n=0}^{K}\mathbf{A}^n\to \mathbf{A}^{*}$.

> ```pseudo
> \begin{algorithm}\caption{Greedy($I$)}
> \begin{algorithmic} 
> \State $J\gets \varnothing$
> \State $V \gets \varnothing$
> \While{$V\neq[n]$}
> \State $j\gets \arg\min_{{i\in [m] \backslash J}}c(S_{i}) / \left| S_{i} \backslash V \right|$
> \State $J\gets J\cup \{j  \}$
> \State $V\gets V\cup \{ S_{j} \}$
\EndWhile
\end{algorithmic}
\end{algorithm}
> ```