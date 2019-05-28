### Object localization

***

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/4%E3%80%81Convolutional%20Neural%20Networks/Week3/images/1.PNG'>

***

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/4%E3%80%81Convolutional%20Neural%20Networks/Week3/images/2.PNG'>

> **b~x~, b~y~, b~w~, b~h~ define the bounding box**

***

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/4%E3%80%81Convolutional%20Neural%20Networks/Week3/images/3.PNG'>

> $$
> y=
> \begin{bmatrix}
> p_c\ (is\ there\ any\ object)\\
> b_x\\
> b_y\\
> b_w\\
> b_h\\
> c_1\ (class\ 1)\\
> c_2\ (class\ 2)\\
> c_3\ (class\ 3)
> \end{bmatrix}
> $$
>
> $$
> \mathscr{L}(\hat y, y)
> =
> \cases
> {
>  (\hat y_1-y_1)^2+ (\hat y_2-y_2)^2+ \cdots+ (\hat y_8-y_8)^2 \quad \ \ if\ \hat y=1\\
>   (\hat y_1-y_1)^2 \qquad \qquad \qquad \qquad \qquad \qquad \quad \quad \quad \, if\ \hat y=0    
> }
> $$

