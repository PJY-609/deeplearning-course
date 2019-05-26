### multi-task learning 

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/3%E3%80%81Structuring%20Machine%20Learning%20Projects/02_ml-strategy-2/03_learning-from-multiple-tasks/images/3.PNG' height="90%" width="90%">

> $$
> Y=\left[ \begin{array}{cccc}{\vdots} & {\vdots} & {\vdots} & {\vdots} \\ {y^{(1)}} & {y^{(2)}} & {\cdots} & {y^{(m)}}  \\ {\vdots} & {\vdots}  & {\vdots} & {\vdots}\end{array}\right],(c, m)
> $$



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/3%E3%80%81Structuring%20Machine%20Learning%20Projects/02_ml-strategy-2/03_learning-from-multiple-tasks/images/4.PNG' height="90%" width="90%">

> $Given\ \hat{y}^{(i)}\ is\ (c,1)$
>
> ​	$Loss=\frac{1}{m} \sum_{i=1}^{m} \sum_{j=1}^{c} \mathcal{L}\left(\hat{y}_{j}^{(i)}, y_{j}^{(i)}\right),\ sun\ over\ only\ when\ the\ label\ makes\ sense$
>
> ​	$\mathcal{L}\left(\hat{y}_{j}^{(i)}, y_{j}^{(i)}\right)=-y_{j}^{(i)} \log \left(\hat{y}_{j}^{(i)}\right)-\left(1-y_{j}^{(i)}\right) \log \left(1-\hat{y}_{j}^{(i)}\right)$



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/3%E3%80%81Structuring%20Machine%20Learning%20Projects/02_ml-strategy-2/03_learning-from-multiple-tasks/images/5.PNG' height="90%" width="90%">

