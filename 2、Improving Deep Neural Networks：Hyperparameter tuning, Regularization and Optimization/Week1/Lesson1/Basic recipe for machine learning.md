### Basic recipe for machine learning

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

