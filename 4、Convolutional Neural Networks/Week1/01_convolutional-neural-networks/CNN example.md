### CNN example

<img src='images\18.png' width='70%' height='70%'>
$$
32 \times 32 \times 3 
\xrightarrow[\substack{f=5\\s=1}]{} 
\underbrace{
\underset{conv1}{28\times 28 \times 6}
\xrightarrow[\substack{f=2\\s=2}]{maxpool} 
\underset{pool1}{14\times 14 \times 6}
}_{Layer\ 1}
\xrightarrow[\substack{f=5\\s=1}]{} 
\underbrace{
\underset{conv2}{10\times 10 \times 16}
\xrightarrow[\substack{f=2\\s=2}]{maxpool} 
\underset{pool2}{5\times 5 \times 16}
}_{Layer\ 2}
=400\times1\\
\xrightarrow[\substack{W^{[2]}(120, 400)\\b^{[2]}=(120)}]{} 
\underset{FC3}{120 \times 1}
\rightarrow
\underset{FC4}{84 \times 1}
\rightarrow
softmax
$$

* $n_W,n_H \downarrow\ and\ n_c\uparrow$



<img src='images\19.png'>

