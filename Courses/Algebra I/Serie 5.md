#Series #Algebra-I 

##### Problem 30

We have that:
```tikz
\usepackage{tikz-cd}
\begin{document}
\begin{tikzcd}
\rho^3 \arrow[dr, "\rho"] \arrow[dd, swap, "\sigma"] 
&&  \rho^2  \arrow[ll, swap, "\rho"] \arrow[dd, swap, "\sigma" near start ] \arrow[from=3-3] \\
& \iota \arrow[rr,crossing over, "\rho" near start ] \arrow[dd, crossing over, swap, "\sigma" near start ] 
& & \rho \arrow[ul, "\rho"] \arrow[dd, swap, "\sigma"] \\
\rho\sigma \arrow[rr, "\rho" near start] \arrow[uu] 
&&  \rho^2\sigma  \arrow[dr, "\rho"]  \\
& \sigma \arrow[lu, "\rho"] \arrow[uu, crossing over] \arrow[from=2-2]
& & \rho^3\sigma \arrow[ll, "\rho"] \arrow[uu] \\


\end{tikzcd}
\end{document}
```
---
##### Problem 31

```tikz
\usepackage{tikz-cd}
\begin{document}

\begin{tikzcd}
\iota \arrow[rr, "\rho"] \arrow[ddddddd, bend right]&& {[2,3,4]} \arrow[dl, "\rho"] \arrow[r, "\sigma"]
& {[1,3,4,2]} \arrow[l] \arrow[rr, "\rho"]& & {[1,3,2,4]}\arrow[dl,"\rho"]\arrow[ddddddd, bend left, "\sigma"]\\
& {[2,4,3]} \arrow[lu, "\rho"] \arrow[d, "\sigma"]
&&& {[1,3]}\arrow[lu,"\rho"]  \arrow[d, "\sigma"]\\
& {[1, 4, 3, 2]} \arrow[u]\arrow[dr, "\rho"] 
&&&{[1,2,3]}\arrow[u] \arrow[dr, "\rho"]\\
{[1,4,2,3]} \arrow[ur, "\rho"]\arrow[d,"\sigma"] && {[1,4]} \arrow[ll, "\rho"] \arrow[r, "\sigma"]& {[1,2,4]}\arrow[l]\arrow[ur,"\rho"]&& {[1,2][3,4]}\arrow[ll, "\rho"]\arrow[d, "\sigma"]\\
{[1,3][2,4]}\arrow[u]\arrow[rr, "\rho"]&&{[1,3,2]}\arrow[ld, "\rho"]\arrow[r, "\sigma"]
& {[2,3]}\arrow[l]\arrow[rr, "\rho"] && {[3,4]}\arrow[ld, "\rho"]\arrow[u]\\
& {[1,3,4]}\arrow[lu, "\rho"] \arrow[d, "\sigma"]&&& {[2,4]}\arrow[lu, "\rho"]\arrow[d,"\sigma"]\\
& {[1,2,3,4]}\arrow[u]\arrow[dr, "\rho"]&&& {[1,4,2]}\arrow[u]\arrow[dr, "\rho"]\\
{[1,2]}\arrow[ru, "\rho"]\arrow[uuuuuuu, bend left, "\sigma"]&&{[1,2,4,3]}\arrow[ll, "\rho"]\arrow[r, "\sigma"]&{[1,4,3]}\arrow[ru, "\rho"]\arrow[l]&& {[1,4][2,3]}\arrow[ll, "\rho"]\arrow[uuuuuuu, bend right]
\end{tikzcd}
\end{document}
```
;-;

---
##### Problem 32
1. Firstly, we show that $N \unlhd KN$. For any $k\in K$, we have: $$k N N k^{-1}N=kNk^{-1}N=(kk^{-1})N=N$$
    For $KN \leq G$, we have for $k_{1}n_{1}, k_{2}n_{2}\in KN$: $$k_{1}n_{1}(k_{2}n_{2})^{-1}=k_{1}\underbrace{ n_{1}n_{2}^{-1} }_{ =:n }k_{2}^{-1}=k_{1}k_{2}^{-1}\underbrace{ k_{2}nk_{2}^{-1} }_{ \in N }\in KN$$
    This proves the statement.
2. For all $k\in K$ and $n\in N \cap K$, we have $kn k^{-1}\in N$ as $N$ is normal, and $knk^{-1}\in K$ as $n\in K$. Therefore, $knk^{-1}\in N \cap K$ and this proves that $N \cap K \unlhd K$.
3. As $N \unlhd KN$, we have the natural homomorphism $\pi: KN \to KN / N$. As $K \leq KN$, we have that: $$\psi:= \left. \pi \right| _{K}$$is a homomorphism. Further, for every $k\in K,n\in N,$$$knN=kN=\pi(k)=\psi(k)$$ Therefore, $\psi$ is surjective. Lastly, $\text{ker}(\psi)=\{ k\in K: kN=N \}=\{ k\in K: k\in N\}=K\cap N$. It follows that, $$KN / N \cong K/(K \cap N)$$from the first isomorphism theorem.
---
##### Problem 33
Firstly, we show that $N / M \unlhd G / M$. For all $nM \in N / M$ and $g M \in G/M$, we have: $$(g M)(nM)(gM)=\underbrace{ (gng) }_{ =: n' }M=n'M\in N / M$$Then, we have a surjective homomorphism $\pi: G / M\to( G / M )/(N / M)$.  Further, as $M \unlhd G$, we have a surjective homomorphism $\varphi: G \to G / M$. Therefore, $\psi:=\pi \circ \varphi$ is a surjective homomorphism from $G$ to $(G / M) / (N / M)$. Then, $$\text{ker}(\psi)=\{ g\in G:\varphi(g)=gM\in \text{ker}(\pi)=N / M \}=N$$ Therefore, we have from the first isomorphism theorem, $$G / N \cong (G / M)/(N / M)$$

---
##### Problem 34

For $m,n\geq 1$, we define the homomorphism: $$\begin{array}{cccc} {\varphi:}&{\mathbb{Z} / m\mathbb{Z}}&\to&{n(\mathbb{Z} / m \mathbb{Z})}\\&{x+m\mathbb{Z}} &\mapsto & {nx+m\mathbb{Z}} \end{array}{}$$
Then, we have $\varphi(m\mathbb{Z})=m\mathbb{Z}$ and $$\varphi(x+y+m\mathbb{Z})=nx+m\mathbb{Z} + ny+m\mathbb{Z} = \varphi(x+m\mathbb{Z})+\varphi(y+m\mathbb{Z})$$
Further, it is surjective by definition. Notice that: $$\text{ker}(\varphi)=\{  x+m\mathbb{Z}\in \mathbb{Z} / m\mathbb{Z}:m |n x \}$$as $\frac{m}{\gcd(m,n)}$ generates this group with order $\gcd(m,n)$, we have that:
$$[\mathbb{Z} / m\mathbb{Z} :n(\mathbb{Z} / m\mathbb{Z})]=\left| \text{ker}(\varphi) \right| =\gcd(n,m)$$
---
##### Problem 35
For $n\geq 1$, let $\varphi: \mathbb{Z} / n\mathbb{Z} \to \mathbb{Z} / n\mathbb{Z}$ be an homomorphism. Let $a+n\mathbb{Z}:= \varphi(1+n\mathbb{Z})$. Then, we have for any $x+n\mathbb{Z}\in \mathbb{Z} / n\mathbb{Z}$, $$\varphi(x+n\mathbb{Z})=x \varphi(1+n\mathbb{Z})=xa+n\mathbb{Z}$$Therefore, $\text{Im}(\varphi)=\braket{ a  }$. As $\text{ord}(a)=\frac{n}{\gcd(a,n)}$ and $\left| \mathbb{Z}/n\mathbb{Z} \right|=n$, we have that $\text{Im}(\varphi)=\mathbb{Z} / n\mathbb{Z}$ if and only if $\text{gcd}(a,n)=1$. Therefore, 
$$\text{Aut}(\mathbb{Z} / n\mathbb{Z})=\{ \varphi: \mathbb{Z} /n\mathbb{Z} \to \mathbb{Z} /n\mathbb{Z}, x+n\mathbb{Z} \mapsto xa+n\mathbb{Z}\ |\ \text{gcd}(a,n)=1 \}$$
---
