#Series #Algorithms 

#### Part 1. Degree concentration
Let $H=(V,E)$ be any undirected graph. We first claim that $d(H)=2\left| E \right| / \left| V \right|$. Indeed, from the handshake lemma, $$\left| E \right| =\frac{1}{2}\sum_{v\in V}^{}d(v)=\frac{1}{2}d(G)\left| V \right| $$

Now, for $G\sim G\left( n, \frac{d}{n} \right)$. For any edge $e\in E(K_{n})$, et $X_{e}=\mathbb{1}_{e\in E(G)}$. By definition, $X_{e}\sim \text{Ber}( d /n)$ i.i.d. Now from the above claim, $d(G)=\frac{2}{n}X$ where $X:=\sum_{e}^{}X_{e}$. Further, we have that $\mathbb{E}[X]=\sum_{e}^{} \frac{d}{n}=\frac{n-1}{2}\cdot d$. Therefore, for $\varepsilon:=20\sqrt{ \frac{d\log n}{n} }$. $$\begin{aligned}\mathbb{P}\left( \left| d(G)-d \right| \geq  \varepsilon\right)&=\mathbb{P}\left( \left| \frac{2}{n}X-\frac{2}{n-1}\mathbb{E}[X] \right| \geq  \varepsilon \right)\leq \mathbb{P}\left( \left| \frac{2}{n}X-\frac{2}{n}\mathbb{E}[X] \right| \geq  \varepsilon\right)\\&\leq \mathbb{P}\left( \left| X-\mathbb{E}[X] \right| \geq \frac{\varepsilon n}{2}\right)\leq \mathbb{P}\left( \left| X-\mathbb{E}[X] \right| \geq \frac{\varepsilon}{d} \frac{ n}{n-1}\mathbb{E}[X]\right)\end{aligned}$$where $\frac{\varepsilon}{d}\frac{n}{n-1}=\frac{20}{n-1} \sqrt{ \frac{n\log n}{d} }<1$ as $d\geq C\log n$ for large enough constant. Hence, by Chernoff, $$\mathbb{P}(\left| d(G)-d \right| \geq \varepsilon)\leq 2\exp\left( -\frac{400}{6} \frac{n}{n-1}\log n\right)\leq n^{-10} $$

---
#### Part 2. Spectral norm bound
From Part 1, we have that with probability $\geq 1-n^{-10}$, we have from $d\geq C\log n$ that: $$d\leq d(G)+20\sqrt{ \frac{d}{n}\log n }\leq d(G)+\frac{20}{\sqrt{ Cn }}d$$Assuming $C$ is large enough, we may wlog assume that $\frac{20}{\sqrt{ Cn }}\leq \frac{1}{20}$. Therefore, $d\leq \frac{20}{19}d(G)$. Now, 
$$\overline{G}=G-\mathbb{E}[G]+\mathbb{E}[G]-\frac{d(G)}{n}11^\top=G-\mathbb{E}[G]+\frac{d-d(G)}{n}11^\top-\frac{d}{n}I_{n}$$We first bound the spectrum of $\frac{d-d(G)}{n}11^\top-\frac{d}{n}I_{n}$. Let $0< \alpha < 1 / n$. Then, as $\text{Spec}(\alpha 11^\top)=\{ \alpha n,0 \}$, we have that: $\left\| I-\alpha 11^\top \right\| =\max\{1-\alpha n,1 \}=1$. Indeed, $\lambda$ is an eigenvalue of $\alpha 11^\top$, if and only if $1-\lambda$ is an eigenvalue for $I-\alpha 11^\top$.

 
Therefore, as we have that $\frac{d-d(G)}{d}\leq \frac{20}{\sqrt{ Cn }}\leq \frac{1}{20}$ from above, we have that:$$\left\| \frac{d-d(G)}{n}11^\top-\frac{d}{n}I_{n} \right\| =\frac{d}{n}\left\| I_{n}-\frac{d-d(G)}{d}11^\top \right\|=\frac{d}{n} \leq 1\leq \sqrt{ d\log n }$$To bound the spectrum of $G-\mathbb{E}[G]$, we use the matrix Bernstein inequality: We have: $$G-\mathbb{E}[G]=\sum_{i<j}Z^{ij},\quad Z^{ij}:=\left( X_{ij}- \frac{d}{n} \right)(E_{ij}+E_{ji})$$where $E^{ij}$ is the indicator matrix at $(i,j)$ and $X_{ij}$ is the indicator variable from above. Then, $Z^{ij}$ is symmetric and zero-mean by definition and: $$\left\| Z^{ij} \right\| =\left| X_{ij}-\frac{d}{n} \right| \left\| E_{ij}+E_{ji} \right\| =\left| X_{ij}-\frac{d}{n} \right| \leq 1$$Further, $$\mathbb{E}[(Z^{ij})^{2}]=\left( \underbrace{ \mathbb{E}[X_{ij}^{2}] }_{ \frac{d}{n}\left( 1-\frac{d}{n} \right) }-\frac{d^{2}}{n^{2}} \right)(E_{ii}+E_{jj})=\frac{d}{n}(E_{ii}+E_{jj})$$Therefore, $$\left\| \sum_{i<j}^{}\mathbb{E}[(Z^{ij})^{2}] \right\| =\left\| \frac{d}{n}(n-1)I_{n} \right\| =\frac{d(n-1)}{n}\leq d$$It follows that with probability $1-n^{-10}$, $$\left\| G-\mathbb{E}[G] \right\| \leq 8(\sqrt{ d \log n }+\log n)\leq 8\left( 1+\frac{1}{\sqrt{ C }} \right)\sqrt{ d\log n }$$By assuming $C$ is large enough, we may assume that $8\left( 1+\frac{1}{\sqrt{ C }} \right)\leq \frac{17}{2}$. Bringing it all together, 

$$\left\| \overline{G} \right\| \leq \left\| G-\mathbb{E}[G] \right\|+\left\| \mathbb{E}[G]-\frac{d(G)}{n} 11^\top \right\| \leq \frac{19}{2}\sqrt{ d\log n }\leq 10\sqrt{ d(G)\log n } $$with error probability at most $2n^{-10}\leq n^{-9}$ using union bound. As $\overline{G}$ is symmetric, we also have that: $\left\| \overline{G}^{2} \right\| =\left\| \overline{G} \right\| ^{2}\leq 100d(G) \log n$.

---
#### Part 3. Median fails
Let $G\sim G(n, d /n)$. We construct an adversary as follows. Let $d_{\text{med}}$ be the median of $G$. 
1. If $\left| d_{\text{med}}-d \right|\geq 0.99\eta n$, then the adversary does nothing and $G':= G$.
2. If $0\leq d_{\text{med}}-d< 0.99\eta n$, then the adversary finds the $\eta n$ vertices in $G$ with the lowest degree and adds all possible edges incident to them.
3. If $0\leq d-d_{\text{med}}< 0.99\eta n$, then the adversary finds the $\eta n$ vertices in $G$ with the highest degree and deletes all edges incident to them.

Let $d_{\text{med}}$ be the median of $G$. Further, let $d_{\text{low}}, d_{\text{high}}$ be the $\left( \frac{1}{2}-\eta \right)n$ and $\left( \frac{1}{2}+\eta \right)n$ smallest degree of $G$, respectively.
1. If ${d}_{\text{med}}< d$, then the adversary finds the $\eta n$ vertices in $G$ with the lowest degree and adds all possible edges incident to them.
2. If ${d}_{\text{med}}\geq d$, 

Let $G'$ denote the modified graph. Then, as $\text{deg}_{G'}(1),\dots,\deg_{G'}(n)$ differ from $\text{deg}_{G}(1),\dots,\deg_{G}(n)$ in at most $\eta n$ nodes, we have that $d_{\text{low}}\leq\widehat{d}_{\text{med}}\leq d_{\text{high}}$. 
1. If $d_{\text{med}}< d$, then

---
#### Part 4. Spectral certificate
Let $Y$ be a $\rho$-node corruption of $G$. Then, there exists $S\subseteq[n]$ s.t. $\left| S \right|\geq (1-\rho) n$ and for all $i,j\in S$ $Y_{ij}=G_{ij}$. Therefore, in otherwords, we have: $\braket{ G-Y , 1_{S}1_{S}^\top }=0$. It follows that,$$\begin{aligned}\left| d(G)-d(Y) \right| &=\frac{1}{n}\left| \braket{ G-Y , 11^\top }  \right| \\&=\frac{1}{n}\left| \braket{ G-Y , 11^\top -1_{S}1_{S}^\top}  \right| \\&=\frac{1}{n}\left| \left\langle \overline{G}-\overline{Y}+\frac{d(G)-d(Y)}{n}11^\top , 11^\top -1_{S}1_{S}^\top\right\rangle  \right|\\&\leq\frac{1}{n}\left| \left\langle \overline{G},11^\top -1_{S}1_{S}^\top\right\rangle \right|+\frac{1}{n}\left|\left\langle\overline{Y},11^\top -1_{S}1_{S}^\top\right\rangle\right| +\frac{\left| d(G)-d(Y) \right| }{n^{2}}\left|\left\langle 11^\top , 11^\top -1_{S}1_{S}^\top\right\rangle  \right| \end{aligned}$$
Now, $$\braket{ 11^\top  , 11^\top -1_{S}1_{S}^\top } =n^2-\left| S \right| ^{2}\leq (1-(1-\rho)^{2})n^{2}$$Further, $$\left\| 11^\top - 1_{S}1_{S}^\top \right\| _{*}$$

We have that: $$d(G)-d(Y)=\frac{1}{n}\braket{ G-Y , 11^\top } =\frac{1}{n}\braket{ \overline{G}-\overline{Y}+\frac{d(G)-d(Y)}{n}11^\top ,11^\top  }=\frac{1}{n}\braket{ \overline{G}-\overline{Y},11^\top  } +d(G)-d(Y)$$Hence, $\braket{ \overline{G}-\overline{Y} , 11^\top }=0$. 
Notice that $d(G)=\frac{1}{n}\sum_{v}^{}\text{deg}_{G}(v)=\frac{1}{n}\sum_{v}^{}\sum_{u}^{}G_{uv}=\frac{1}{n}\braket{ G , 11^\top }$. Similarly, $d(Y)=\frac{1}{n}\braket{ Y , 11^\top }$. Hence, $$\left| d(G)-d(Y) \right| =\frac{1}{n}\left| \braket{ G-Y , 11^\top }  \right| =\frac{1}{n}\left| \left\langle \overline{G}- \overline{Y}+ \frac{d(G)-d(Y)}{n}11^\top ,  11^\top\right\rangle  \right| $$

---
#### Part 5. Using spectral certificates inside SOS
Using $\vdash \braket{ a , b }\leq\|a\|^{2}\|b\|^{2}$ from 8. Useful SOS Proofs,  $$\begin{aligned}\{ M=M^\top,M^2=\alpha I_{n}- RR^\top \}\vdash \braket{ x , My } ^{2}&\leq \|x\|^{2}\|My\|^{2}\\&=\|x\|^{2} y^\top M^\top My\\&=\|x\|^{2} y^\top M^{2}y\\&=\|x\|^{2} y^\top (\alpha I_{n}-RR^\top)y\\&=\alpha\|x\|^{2}\|y\|^{2}-\|x\|^{2}\|R^\top y\|^{2}\\&\leq \alpha\|x\|^{2}\|y\|^{2}\end{aligned}$$where the last inequality follows as $\|x\|^2\|R^\top y\|^{2}$ is a square. We also see that the degree is constant. 

---
#### Part 6. SoS identifiability, Part I
As we have that $$\mathcal{A}\vdash Y_{ij}\tilde{z}_{i}\tilde{z}_{j}=G_{ij}\tilde{z}_{i}\tilde{z}_{j},\quad \forall i,j\in[n]$$it follows that:
$$\begin{aligned}\mathcal{A}\vdash n(d(Y)-d(G))&=\braket{Y- G , 11^\top }\\&=\braket{Y- G , 11^\top -\tilde{z}\tilde{z}^\top} \\&=\left\langle\overline{Y}- \overline{G} +\frac{d(Y)-d(G)}{n}11^\top , 11^\top -\tilde{z}\tilde{z}^\top\right\rangle \\&=\braket{ \overline{Y} , 11^\top-\tilde{z}\tilde{z}^\top } -\braket{ \overline{G} , 11^\top-\tilde{z}\tilde{z}^\top } +\frac{d(Y)-d(G)}{n}\braket{11^\top , 11^\top-\tilde{z}\tilde{z}^\top } \\&=\braket{ \overline{Y} , 11^\top-\tilde{z}\tilde{z}^\top } -\braket{ \overline{G} , 11^\top-\tilde{z}\tilde{z}^\top } +n\left( 1-\left( \frac{\braket{ \tilde{z} , 1 } }{n} \right)^{2} \right)(d(Y)-d(G))\end{aligned} $$where the last step follows from:$$\braket{ 11^\top , 11^\top -\tilde{z} \tilde{z}^\top } =n^2-\sum_{i,j}^{}\tilde{z}_{i}\tilde{z}_{j}=n^2-\braket{ \tilde{z} , 1 } ^{2}=n^2\left( 1-\left( \frac{\braket{ \tilde{z} , 1 } }{n} \right)^{2}  \right) $$Therefore, by rearranging:
$$\mathcal{A}\vdash n\left( \frac{\braket{ \tilde{z} , 1 } }{n} \right)^{2}(d(Y)-d(G))=\braket{ \overline{Y} , 11^\top-\tilde{z}\tilde{z}^\top } -\braket{ \overline{G} , 11^\top-\tilde{z}\tilde{z}^\top } $$By squaring both sides, $$\begin{aligned}\mathcal{A}\vdash n^{2}(d(Y)-d(G))^{2}&= \left( \frac{n}{\braket{ \tilde{z} , 1 } }\right)^{4}(\braket{ \overline{Y} , 11^\top-\tilde{z}\tilde{z}^\top } -\braket{ \overline{G} , 11^\top-\tilde{z}\tilde{z}^\top } )^{2}\\&\le 2 \left( \frac{n}{\braket{ \tilde{z} , 1 } }\right)^{4}(\braket{ \overline{Y} , 11^\top-\tilde{z}\tilde{z}^\top }^{2} +\braket{ \overline{G} , 11^\top-\tilde{z}\tilde{z}^\top }^{2} )\end{aligned}$$Now it suffices to show that $\frac{n}{\braket{ \tilde{z} , 1 }}\leq O(1)$.  We have that: $$\mathcal{A}\vdash n\leq \frac{1}{1-2\eta}\braket{ \tilde{z} , 1 } \leq \frac{1}{1-\frac{2}{C}}\braket{ \tilde{z} , 1 } =O(1)\braket{ \tilde{z} , 1 } $$

---
#### Part 7. SoS identifiability, Part II
We have that: $$\begin{aligned}\mathcal{A}\vdash \braket{ \overline{Y} , 11^\top-\tilde{z}\tilde{z}^\top } ^{2}&=(nd(Y) -\braket{ \tilde{z} , \overline{Y}\tilde{z} })^{2}\\&\leq 2(n^{2}\braket{ 1 , \overline{Y}1 } ^2+\braket{ \tilde{z} , \overline{Y} \tilde{z}}^{2} ) \end{aligned}$$We have: $$\mathcal{A}\vdash \braket{ \overline{Y} , 11^\top-\tilde{z}\tilde{z}^\top } =\text{tr}(\overline{Y})$$