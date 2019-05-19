### multi-task learning 

<img src='images\3.png'>
$$
Y=\begin{bmatrix}
\vdots & \vdots & &\vdots\\
y^{(1)}& y^{(2)}& \cdots & y^{(m)}\\
\vdots & \vdots & &\vdots
\end{bmatrix}
,\ 
(c,m)
$$




<img src='images\4.png'>

$Given\ \hat y^{(i)}\ is\ (c,1)\\$
$$
Loss=\frac{1}{m}\sum^m_{i=1}\sum^c_{j=1}\mathscr{L}(\hat y^{(i)}_{j},y^{(i)}_{(j)}),\ sum\ over\ only\ when\ the\ label\ makes\ sense\\
\mathscr{L}(\hat y^{(i)}_{j},y^{(i)}_{(j)})=-y^{(i)}_{(j)}log(\hat y^{(i)}_{(j)})-(1-y^{(i)}_{(j)})log(1-\hat y^{(i)}_{(j)})
$$
$Unlike\ softmax$



<img src='images\5.png'>

