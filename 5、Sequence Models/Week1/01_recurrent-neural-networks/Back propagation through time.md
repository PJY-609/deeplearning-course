### Back propagation through time

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week1/01_recurrent-neural-networks/images/8.PNG' width='80%' height='80%'>

> $$
> \mathscr{L}(\hat y, y)=\sum_{t=1}^{T_y}\mathscr{L}^{<t>}(\hat y^{<t>}, y^{<t>})
> $$
>
> $$
> \mathscr{L}^{<t>}(\hat y^{<t>},y^{<t>})=-y^{(i)}log( \hat y^{<t>})-(1-y^{<t>})log(1-\hat y^{<t>})
> $$

