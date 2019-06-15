### train, dev, test distribution

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/3%E3%80%81Structuring%20Machine%20Learning%20Projects/01_ml-strategy-1/02_setting-up-your-goal/images/1.PNG' width='70%' height='70%'>

> * try different ideas to  improve the performance on dev set and finally pick the best one
>
> * dev set + metric
>   * the target for optimization
> * dev and test set should come from the same disribution



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/3%E3%80%81Structuring%20Machine%20Learning%20Projects/01_ml-strategy-1/02_setting-up-your-goal/images/2.PNG' width='70%' height='70%'>

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/3%E3%80%81Structuring%20Machine%20Learning%20Projects/01_ml-strategy-1/02_setting-up-your-goal/images/3.PNG' width='70%' height='70%'>

***

### Size of the dev and test sets

<img src="https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/3%E3%80%81Structuring%20Machine%20Learning%20Projects/01_ml-strategy-1/02_setting-up-your-goal/images/4.PNG" width='70%' height='70%'>

<img src="https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/3%E3%80%81Structuring%20Machine%20Learning%20Projects/01_ml-strategy-1/02_setting-up-your-goal/images/5.PNG" width='70%' height='70%'>

***

### when to change dev test sets and metrics

<img src="https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/3%E3%80%81Structuring%20Machine%20Learning%20Projects/01_ml-strategy-1/02_setting-up-your-goal/images/6.PNG" width='70%' height='70%'>

> Algorithm A though outperforms B but let through a lot of porn images
>
> * metric + dev set: prefer A
> * developers + users: prefer B
>
> change the metric to a weighted error
>
> or change the dev and test set



<img src="https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/3%E3%80%81Structuring%20Machine%20Learning%20Projects/01_ml-strategy-1/02_setting-up-your-goal/images/7.PNG" width='70%' height='70%'>

> * the first aim is to set the target (metric)
> * the second is to worry about the optimization on this metric independently



<img src="https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/3%E3%80%81Structuring%20Machine%20Learning%20Projects/01_ml-strategy-1/02_setting-up-your-goal/images/8.PNG" width='70%' height='70%'>