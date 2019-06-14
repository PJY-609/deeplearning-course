## Recurrent neural network model

#### Sequence model

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week1/01_recurrent-neural-networks/images/1.PNG' width='80%' height='80%'>

***

#### Notation

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week1/01_recurrent-neural-networks/images/2.PNG' width='80%' height='80%'>

> $$
> (x^{<1>}, \cdots ,x^{<T_x>}),(y^{<1>}, \cdots, y^{<T_y>})\\
> x^{(i)<t>}:\ the\ i^{th}\ training\ example's\ t^{th}\ sequence\ element\\
> T_x^{(i)}:\ the\ i^{th}\ traning\ example's\ sequence\ length
> $$



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week1/01_recurrent-neural-networks/images/3.PNG' width='80%' height='80%'>

> $$
> 
> $$



***

#### Recurrent neural network model

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week1/01_recurrent-neural-networks/images/5.PNG' width='80%' height='80%'>

> * a problem of RNN is that it only takes the previous words into consideration
>
>   *Example*
>
>   Knowing Teddy from the previous words 'He said' is no enough to infer this is a person's name



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week1/01_recurrent-neural-networks/images/6.PNG' width='80%' height='80%'>



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week1/01_recurrent-neural-networks/images/7.PNG' width='80%' height='80%'>

> $$
> a^{<t>}=g\left(\underbrace{{W}_{a a}}_{(100,100)} \underbrace{a^{<t-1>}}_{(100,1)}+\underbrace{W_{a x}}_{(100,10000)}\underbrace{x^{<t>}}_{(10000,1)}+b_{a} \right)\\
> \Rightarrow a^{<t>}=g(W_a[a^{<t-1>},x^{<t>}]+b_a)\\
> $$
>
> $$
> \left[
>     \begin{array}{c:c}
>     	W_{aa} & W_{ax}
>     \end{array}
> \right]
> =W_a\\
> \left[
>     \begin{array}{l}
>     	a^{<t-1>} , x^{<t>}
>     \end{array}
> \right]
> =
> \left[
>     \begin{array}{l}
>     	a^{<t-1>} \\ \hline
>         x_{<t>}
>     \end{array}
> \right]
> $$
>
> $$
> \left[
>     \begin{array}{c:c}
>     	W_{aa} & W_{ax}
>     \end{array}
> \right]
> \left[
>     \begin{array}{l}
>     	a^{<t-1>} \\ \hline
>         x_{<t>}
>     \end{array}
> \right]
> ={W}_{a a} a^{<t-1>}+W_{a x}x^{<t>}
> $$



