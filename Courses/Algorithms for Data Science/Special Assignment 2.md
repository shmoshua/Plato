#Series #Algorithms 

#### Part 1. Degree concentration
Let $H=(V,E)$ be any undirected graph. We first claim that $d(H)=2\left| E \right| / \left| V \right|$. Indeed, from the handshake lemma, $$\left| E \right| =\frac{1}{2}\sum_{v\in V}^{}d(v)=\frac{1}{2}d(G)\left| V \right| $$

Now, for $G\sim G\left( n, \frac{d}{n} \right)$. For any edge $e\in E(K_{n})$, et $X_{e}=\mathbb{1}_{e\in E(G)}$. By definition, $X_{e}\sim \text{Ber}( d /n)$ i.i.d. Now from the above claim, $d(G)=\frac{2}{n}X$ where $X:=\sum_{e}^{}X_{e}$. Further, we have that $\mathbb{E}[X]=\sum_{e}^{} \frac{d}{n}=\frac{n-1}{2}\cdot d$. Therefore, for $\varepsilon:=20\sqrt{ \frac{d\log n}{n} }$. $$\begin{aligned}\mathbb{P}\left( \left| d(G)-d \right| \geq  \varepsilon\right)&=\mathbb{P}\left( \left| \frac{2}{n}X-\frac{2}{n-1}\mathbb{E}[X] \right| \geq  \varepsilon \right)\leq \mathbb{P}\left( \left| \frac{2}{n}X-\frac{2}{n}\mathbb{E}[X] \right| \geq  \varepsilon\right)\\&\leq \mathbb{P}\left( \left| X-\mathbb{E}[X] \right| \geq \frac{\varepsilon n}{2}\right)\leq \mathbb{P}\left( \left| X-\mathbb{E}[X] \right| \geq \frac{\varepsilon}{d} \frac{ n}{n-1}\mathbb{E}[X]\right)\end{aligned}$$where $\frac{\varepsilon}{d}\frac{n}{n-1}=\frac{20}{n-1} \sqrt{ \frac{n\log n}{d} }<1$ as $d\geq C\log n$ for large enough constant. Hence, by Chernoff, $$\mathbb{P}(\left| d(G)-d \right| \geq \varepsilon)\leq 2\exp\left( -\frac{400}{6} \frac{n}{n-1}\log n\right)\leq n^{-10} $$

---
#### Part 2. Spectral norm bound
We use the Matrix Bernstein inequality. For $i<j$ let: $$Z_{ij}:= \left( X_{ij}-\frac{d(G)}{n-1} \right)(E_{ij}+E_{ji})$$Then, $G=\sum_{i<j}^{}Z_{ij}$. We have that $Z_{ij}$ are symmetric and: $$\mathbb{E}[Z_{ij}]=\left( \mathbb{E}[X_{ij}]-\frac{\mathbb{E}[d(G)]}{n-1} \right) (E_{ij}+E_{ji}) =\left( \frac{d}{n}-\frac{\frac{n-1}{n}d}{n-1} \right)(E_{ij}+E_{ji})=0 $$Further, $$\left\| Z_{ij} \right\| =\left( X_{ij}-\frac{d(G)}{n-1} \right)\leq 1$$and $$\mathbb{E}[Z_{ij}Z_{ij}^\top] =\mathbb{E}\left[ \left( X_{ij}-\frac{d(G)}{n-1} \right)^{2}\right](E_{ii}+E_{jj}) =\left( \underbrace{ \mathbb{E}[X_{ij}^{2}] }_{ \frac{d}{n}\left( 1-\frac{d}{n} \right)  }+\frac{d(G)^{2}}{(n-1)^{2}} \right)(E_{ii}+E_{jj})$$Therefore, $$\left\| \sum_{i<j}^{}\mathbb{E}[Z_{ij}Z_{ij}^\top] \right\| \leq (n-1)\left( \frac{d}{n}\left( 1-\frac{d}{n} \right)+\frac{d(G)^{2}}{(n-1)^{2}} \right)\leq  $$


---
#### Part 3. Median fails
Let $G\sim G(n, d /n)$. We construct an adversary as follows. 
1. If $\widehat{d}_{\text{med}}< d$, then 

that takes $\eta n$ vertices in $G$ with the highest degree and deletes all edges incident to them. Then, any node in 

---
#### Part 4. Spectral certificate
Notice that $d(G)=\frac{1}{n}\sum_{v}^{}\text{deg}_{G}(v)=\frac{1}{n}\sum_{v}^{}\sum_{u}^{}G_{uv}=\frac{1}{n}\braket{ G , 11^\top }$. Similarly, $d(Y)=\frac{1}{n}\braket{ Y , 11^\top }$. Hence, $$\left| d(G)-d(Y) \right| =\frac{1}{n}\left| \braket{ G-Y , 11^\top }  \right| $$

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