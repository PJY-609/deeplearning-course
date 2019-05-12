### RMSprop

$On\ iteration\ t:$

​	$Compute\ dW,db\ on\ mini-batch$

​	$s_{dW}=\beta s_{dW}+(1-\beta)dW^2$ **element-wise square calculation**

​	$s_{db}=\beta s_{db}+(1-\beta)db^2$

​	$W:=W-\alpha \frac{dW}{\sqrt{s_{dW}}+\epsilon}$ **add a small number to avoid divide by zero**

​	$b:=b-\alpha \frac{db}{\sqrt{s_{db}}+\epsilon}$

