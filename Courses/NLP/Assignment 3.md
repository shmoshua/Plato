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
2. We show this by induction over $n$. If $n=1$, every path of length one is an edge and the statement is true by definition. For $n\geq 2$, we have to now show that for any $i,k\in[N]$, $$(M^n)_{ik}=\bigoplus _{\begin{array}\ p:p=(v_{0},\dots,v_{n})\\v_{0}=i,v_{n}=k\end{array}}^{}$$
   We have that: $$\begin{aligned}(\mathbf{M}^n)_{ik}&=(\mathbf{M}^{n-1}\otimes  \mathbf{M})_{ik}\\&=\bigoplus _{j\in[N]}((\mathbf{M}^{n-1})_{ij}\otimes  \mathbf{M}_{jk})\\&=\bigoplus _{j\in[N]}\left(\left(  \bigoplus_{\pi\in \Pi_{ij}(n)}w(\pi) \right)  \otimes  \mathbf{M}_{jk} \right) \end{aligned}$$If $\mathbf{M}_{jk}=0$ then by annihilation, the term is 0. Hence, $$\begin{aligned}(\mathbf{M}^n)_{ik}&=\bigoplus _{j: jk\in E(\mathcal{G})}\left(\left(  \bigoplus_{\pi\in \Pi_{ij}(n-1)}w(\pi) \right)  \otimes  w_{jk} \right) \\&=\bigoplus _{j: jk\in E(\mathcal{G})}\left(  \bigoplus_{\pi\in \Pi_{ij}(n-1)}\bigotimes_{i=1}^{n-1} w_{\pi(i-1),\pi(i)}\otimes  w_{jk}    \right) 
   \\&=\bigoplus _{j: jk\in E(\mathcal{G})}\left(  \bigoplus_{\pi\in \Pi_{ij}(n-1)}\bigotimes_{i=1}^{n-1} w_{\pi(i-1),\pi(i)}\otimes  w_{jk}    \right) \end{aligned}$$
   We have
$$\begin{aligned}
\bigoplus_{\pi\in \Pi_{ik}(n)}w(\pi)&=\bigoplus_{\pi\in \Pi_{ik}(n)}\bigotimes _{i\in[n]}w_{\pi(i-1),\pi(i)}\\&=\bigoplus_{\pi\in \Pi_{ik}(n)}\bigoplus _{v\in[N]}\bigotimes _{i\in[n-1]}w_{\pi(i-1),\pi(i)} \otimes  w_{v,\pi(i)}\otimes  1_{\pi(n-1)=v}
\end{aligned}$$