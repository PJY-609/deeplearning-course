###  human performance 

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/3%E3%80%81Structuring%20Machine%20Learning%20Projects/01_ml-strategy-1/03_comparing-to-human-level-performance/images/1.PNG' width="70%" height="70%">

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/3%E3%80%81Structuring%20Machine%20Learning%20Projects/01_ml-strategy-1/03_comparing-to-human-level-performance/images/2.PNG' width="70%" height="70%">

***

### avoidable bias

| human error | training error | dev error |                                  |
| :---------: | :------------: | :-------: | -------------------------------- |
|     1%      |       8%       |    10%    | focus on bias reduction tech     |
|    7.5%     |       8%       |    10%    | focus on variance reduction tech |

- human-level error viewed as a proxy for Bayes error
  - earlier assumed to be 0, but most cases can't be 0
- <img src="https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/3%E3%80%81Structuring%20Machine%20Learning%20Projects/01_ml-strategy-1/03_comparing-to-human-level-performance/images/gif.gif" />

<img src="https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/3%E3%80%81Structuring%20Machine%20Learning%20Projects/01_ml-strategy-1/03_comparing-to-human-level-performance/images/3.PNG" width="70%" height="70%">

***

### understanding human performance 

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/3%E3%80%81Structuring%20Machine%20Learning%20Projects/01_ml-strategy-1/03_comparing-to-human-level-performance/images/4.PNG' width="70%" height="70%">

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/3%E3%80%81Structuring%20Machine%20Learning%20Projects/01_ml-strategy-1/03_comparing-to-human-level-performance/images/5.PNG' width="70%" height="70%">

> * In the first case, the avoidable bias is 4%~4.5%, and the variance is 1%. In this case, it doesn't matter which human performance is used
> * In the second case, the avoidable bias is 0~0.5%. The variance 4% $\gg$ bias.
> * In the third case, if 0.7% is chosen as the *Bayes error*, then room for improvement in avoidable bias won't be recognized. 
> * It is also hard to optimize when the model already reach human-level performance.

***

### improving model performance

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/3%E3%80%81Structuring%20Machine%20Learning%20Projects/01_ml-strategy-1/03_comparing-to-human-level-performance/images/6.PNG' width="70%" height="70%">

