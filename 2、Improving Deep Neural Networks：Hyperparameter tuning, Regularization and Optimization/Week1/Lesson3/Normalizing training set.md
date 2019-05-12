### Normalizing training set

* <img src='images\4.png'>

* $Subtract\ mean:$
  * $\mu=\frac{1}{m}\sum^m_{i=1}x^{(i)}$
  * $x:=x-\mu$
  * <img src='images\5.png'>
* $Normalize\ variance:$
  * $\sigma^2=\frac{1}{m}\sum^m_{i=1}x^{(i)}\underbrace{**}_{elementwise\ power}2$
  * $x/=\sigma^2$
  * <img src='images\6.png'>

* ==**use the same $\mu$ and $\sigma^2$ to test and dev set**==
  * want the data in dev and test set go through the same transformation

***

### Why normalize inputs?

<img src='images\7.png' style='zoom:30'>

