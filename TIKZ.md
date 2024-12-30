##### DAGS
```tikz
\usepackage{tikz}
\usetikzlibrary{arrows}

\begin{document}

\begin{tikzpicture}

\tikzset{vertex/.style = {shape=circle,draw,minimum size=1.5em}}
\tikzset{edge/.style = {->,> = latex'}}
% vertices
\node[vertex] (a) at  (4,2) {$w$};
\node[vertex] (b) at  (0,0) {$y_1$};
\node[vertex] (b1) at (1.5,0) {$y_2$};
\node[vertex] (b2) at (3,0) {$y_3$};
\node[vertex] (c) at  (8,0) {$y_n$};


%edges
\draw[edge] (a) to (b);
\draw[edge] (a) to (b1);
\draw[edge] (a) to (b2);
\draw[edge] (a) to (c);

\path (b2) to node {\dots} (c);

\end{tikzpicture}
\end{document} 
```

> ```tikz
>\usepackage{tikz}
>\usetikzlibrary{arrows}
>\usetikzlibrary{fit}
>
>\begin{document}
>
>\begin{tikzpicture}
>
>\tikzset{vertex/.style = {shape=circle,draw,minimum size=1.5em}}
>\tikzset{dot/.style = {minimum size=1.5em}}
>\tikzset{edge/.style = {->,> = latex'}}
>% vertices
>\node[vertex] (a) at  (4,2) {$w$};
>\node[vertex] (b) at  (0,0) {$y_1$};
>\node[vertex] (b1) at (1.5,0) {$y_2$};
>\node[vertex] (b2) at (3,0) {$y_3$};
>\node[vertex] (c) at  (8,0) {$y_n$};
>
>\node[dot] (d) at (2,2) {$\sigma_p^2$};
>\node[dot] (d1) at (0,1.5) {$\sigma_n^2$};
>\node[dot] (x1) at (0,-1.5) {$x_1$};
>\node[dot] (x2) at (1.5,-1.5) {$x_2$};
>\node[dot] (x3) at (3,-1.5) {$x_3$};
>\node[dot] (x) at (8,-1.5) {$x_n$};
>
>\node[vertex] (aa) at  (13,2) {$w$};
>\node[vertex] (ba) at  (13,0) {$y_i$};
>
>\node[dot] (da) at (11,2) {$\sigma_p^2$};
>\node[dot] (d1a) at (11,0) {$\sigma_n^2$};
>\node[dot] (x1a) at (13,-1.5) {$x_i$};
>\node[dot] (ta) at (14.05,-1.6) {$\footnotesize{i\in[n]}$};
>
>
>%edges
>\draw[edge] (a) to (b);
>\draw[edge] (a) to (b1);
>\draw[edge] (a) to (b2);
>\draw[edge] (a) to (c);
>\draw[edge] (d) to (a);
>\draw[edge] (d1) to (b);
>\draw[edge] (d1) to (b1);
>\draw[edge] (d1) to (b2);
>\draw[edge] (d1) to (c);
>\draw[edge] (x1) to (b);
>\draw[edge] (x2) to (b1);
>\draw[edge] (x3) to (b2);
>\draw[edge] (x) to (c);
>\draw[edge] (aa) to (ba);
>\draw[edge] (da) to (aa);
>\draw[edge] (d1a) to (ba);
>\draw[edge] (x1a) to (ba);
> \node[draw,dotted,fit=(ba)(x1a)] {};
>
>
>\path (b2) to node {\dots} (c);
>\path (x3) to node {\dots} (x);
>
>\end{tikzpicture}
>\end{document} 
>```

```tikz
>    \usepackage{tikz}
>    \usetikzlibrary{decorations.markings}
>    \newcommand{\midarrow}{\tikz \draw[-triangle 90] (0,0) -- +(.1,0);}
>    \begin{document}
>    \begin{tikzpicture}
>    \begin{scope}[very thick,decoration={markings,mark=at position 0.55 with {\arrow{>}}}] 
>    \draw[postaction={decorate}] (0,-1)--(1.73,0);
>    \draw[postaction={decorate}] (1.73,0)--(0,1);
>    \draw[postaction={decorate}] (0,-1)--(0,1);
>    \end{scope}
>    
>    \tikzset{edge/.style = {->,> = latex'}}
>    \path[draw, ultra thick] (0,1) node[anchor=east]{$e_{2}$}
>    --node[left]{$f*g$} (0,-1)  node[anchor=east] {$e_{0}$}
>    --node[below right]{$f$} (1.73,0) node[anchor=west]{$e_{1}$}
>    --node[above right]{$g$} cycle;
>    \path[clip] (0,1) -- (0,-1) -- (1.73,0) -- cycle; 
>    \foreach \y in{-1,-0.9,...,1}
> 	   \draw (0,\y) -- (10,\y);
>    
>    \node (a) at  (0,1) {};
>    \node (b) at  (0,-1) {};
>    \node (c) at  (1.73,0) {};
>    
>    
>    \end{tikzpicture}
>    \end{document} 
>    ```