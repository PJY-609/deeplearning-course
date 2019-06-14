### Language model and sequence generation

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week1/01_recurrent-neural-networks/images/10.PNG' width='80%' height='80%'>

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week1/01_recurrent-neural-networks/images/11.PNG' width='80%' height='80%'>

> * **tokenize**
> * **<EOF>**
> * **<UNK>**



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week1/01_recurrent-neural-networks/images/12.PNG' width='80%' height='80%'>

> * end up setting $x^{<t>}=y^{<t-1>}$
> * $P(y^{<1>},y^{<2>},\cdots,y^{<T_y>})=P(y^{<1>})P(y^{<2>}|y^{<1>})\cdots P(y^{<T_y>}|y^{<T_y-1>}\cdots y^{<1>})$

