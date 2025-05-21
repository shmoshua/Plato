#Series #Algorithms 

#### Part 1. Degree concentration
Let $H=(V,E)$ be any undirected graph. We first claim that $d(H)=2\left| E \right| / \left| V \right|$. Indeed, from the handshake lemma, $$\left| E \right| =\frac{1}{2}\sum_{v\in V}^{}d(v)=\frac{1}{2}d(G)\left| V \right| $$

Now, for $G\sim G\left( n, \frac{d}{n} \right)$. For any edge $e\in E(K_{n})$, et $X_{e}=\mathbb{1}_{e\in E(G)}$. By definition, $X_{e}\sim \text{Ber}( d /n)$ i.i.d. Now from the above claim, $d(G)=\frac{2}{n}X$ where $X:=\sum_{e}^{}X_{e}$. Further, we have that $\mathbb{E}[X]=\sum_{e}^{} \frac{d}{n}=\frac{n-1}{2}\cdot d$. Therefore, for $\varepsilon:=20\sqrt{ \frac{d\log n}{n} }$. $$\begin{aligned}\mathbb{P}\left( \left| d(G)-d \right| \geq  \varepsilon\right)&=\mathbb{P}\left( \left| \frac{2}{n}X-\frac{2}{n-1}\mathbb{E}[X] \right| \geq  \varepsilon \right)\leq \mathbb{P}\left( \left| \frac{2}{n}X-\frac{2}{n}\mathbb{E}[X] \right| \geq  \varepsilon\right)\\&\leq \mathbb{P}\left( \left| X-\mathbb{E}[X] \right| \geq \frac{\varepsilon n}{2}\right)\leq \mathbb{P}\left( \left| X-\mathbb{E}[X] \right| \geq \frac{\varepsilon}{d} \frac{ n}{n-1}\mathbb{E}[X]\right)\end{aligned}$$where $\frac{\varepsilon}{d}\frac{n}{n-1}=\frac{20}{n-1} \sqrt{ \frac{n\log n}{d} }<1$ as $d\geq C\log n$ for large enough constant. Hence, by Chernoff, $$\mathbb{P}(\left| d(G)-d \right| \geq \varepsilon)\leq 2\exp\left( -\frac{400}{6} \frac{n}{n-1}\log n\right)\leq n^{-10} $$

#### Part 2. Spectral norm bound
We use the matrix bernstein inequality. For $i<j$ let: $$Z_{ij}:=\left( X_{ij}-\frac{d(G)}{n-1} \right)(E_{ij}+E_{ji})$$Then, $\overline{G}=-\frac{d(G)}{n}I+\sum_{i<j}^{}Z_{ij}$. We have that $Z_{ij}$ are symmetric and: $$\mathbb{E}[Z_{ij}]=\left( \mathbb{E}[X_{ij}]-\frac{\mathbb{E}[d(G)]}{n-1} \right) (E_{ij}+E_{ji}) =\left( \frac{d}{n}-\frac{\frac{n-1}{n}d}{n-1} \right)(E_{ij}+E_{ji})=0 $$Further, $$\left\| Z_{ij} \right\| =\left( X_{ij}-\frac{d(G)}{n-1} \right)\leq 1$$and $$\left\| \sum_{i<j}^{}\mathbb{E}[Z_{ij}Z_{ij}^\top] \right\| =\left\| \sum_{i<j}^{}\mathbb{E}\left[ \left( X_{ij}-\frac{d(G)}{n-1} \right)^{2}(E_{ii}+E_{jj}) \right] \right\|=\left\| \sum_{i<j}^{}\mathbb{E}\left[ \left( X_{ij}-\frac{d(G)}{n-1} \right)^{2} \right] (E_{ii}+E_{jj})\right\| $$


---
#### Part 3. Median fails
Let $G\sim G(n, d /n)$. We construct an adversary that takes $\eta n$ vertices in $G$ with the highest degree and deletes all edges incident to them. 

---
#### Part 4. Spectral certificate
Notice that $d(G)=\frac{1}{n}\sum_{v}^{}\text{deg}_{G}(v)=\frac{1}{n}\sum_{v}^{}\sum_{u}^{}G_{uv}=\frac{1}{n}\braket{ G , 11^\top }$. Similarly, $d(Y)=\frac{1}{n}\braket{ Y , 11^\top }$. Hence, $$\left| d(G)-d(Y) \right| =\frac{1}{n}\left| \braket{ G-Y , 11^\top }  \right| $$

---
#### Part 5. Using spectral certificates inside SOS
We have that: $$$$