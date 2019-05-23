### Simple convolutional network example

<img src='images\14.PNG'>




$$
\underbrace{39 \times 39 \times 3}_{\substack{n^{[0]}_H=n^{[0]}_W=39\\ n^{[0]}_c=3}} \xrightarrow[\substack{f^{[1]}=3 \\ s^{[1]}=1 \\p^{[1]}=0\\ 10\ filters}]{}
\underbrace{37 \times 37 \times 10}_{\substack{n^{[1]}_H=n^{[1]}_W=37\\ n^{[1]}_c=10}} 
\xrightarrow[\substack{f^{[2]}=5 \\ s^{[2]}=2 \\p^{[1]}=0\\ 20\ filters}]{}
\underbrace{17 \times 17 \times 20}_{\substack{n^{[2]}_H=n^{[2]}_W=17\\ n^{[2]}_c=20}} 
\xrightarrow[\substack{f^{[3]}=5 \\ s^{[3]}=2 \\p^{[3]}=0\\ 40\ filters}]{}
\\
\\
7 \times 7 \times 40
\xrightarrow[flatten]{}
1960 \times 1
\xrightarrow[logistic\ or\ softmax]{}
\cdots
$$

$$
e.g.\ 39 \rightarrow 37 \Rightarrow\biggl\lfloor \frac{39+0-3}{1}+1 \biggr\rfloor =37
$$

