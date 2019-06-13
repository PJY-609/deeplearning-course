### Basic recipe for machine learning

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/2%E3%80%81Improving%20Deep%20Neural%20Networks%EF%BC%9AHyperparameter%20tuning%2C%20Regularization%20and%20Optimization/Week1/Lesson1/images/basic_recipe.PNG' width='80%'>

```flow
st=>start: start
cond1=>condition: high bias?
op1=>operation: bigger network
op2=>operation: train longer
op3=>operation: NN architecture
st->cond1(yes)->op1->op2->op3->cond1
cond2=>condition: high variance?
op4=>operation: more data
op5=>operation: regularization
op6=>operation: NN architecture
cond1(no)->cond2(yes)->op4->op5->op6->cond2
e=>end: end
cond2(no)->e
```

