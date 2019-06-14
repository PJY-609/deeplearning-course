## learning word embeddings word2vec

#### <a name='learn'>learning word embeddings</a>

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week2/02_learning-word-embeddings-word2vec-glove/images/1.PNG' width='80%'>

> * **hyperparameter** the length of context window



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week2/02_learning-word-embeddings-word2vec-glove/images/2.PNG' width='80%'>

***

#### <a name='word2vec'>word2vec</a>

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week2/02_learning-word-embeddings-word2vec-glove/images/3.PNG' width='80%'>

> * randomly pick a target word within some window 
> * use the context word to predict the target
> * the task per se is no the goal, but use that to learn word embeddings  



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week2/02_learning-word-embeddings-word2vec-glove/images/4.PNG' width='80%'>

> $$
> o_c \rightarrow E \rightarrow e_c=E \cdot o_c\rightarrow softmax \rightarrow \hat y
> $$
>
> $$
> softmax: \ p(t|c)=\frac{e^{\theta_t^Te_c}}{\sum^{10,000}_{j=1}e^{\theta_j^Te_c}}, \ \theta_t:\ parameters\ associated\ with\ output\ t
> $$
>
> $$
> \mathscr{L}(\hat y, y)=-\sum^{10,000}_{i=1}y_ilog(\hat y_i)
> $$



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week2/02_learning-word-embeddings-word2vec-glove/images/5.PNG' width='80%'>

> * problem of large computation work
> * one solution: hierarchical softmax
>   * more frequent words occupy the head of the softmax tree
> * How to sample the context c to balance the less frequent words against common words

***

#### <a name='neg'>negative sampling</a>

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week2/02_learning-word-embeddings-word2vec-glove/images/6.PNG' width='80%'>

> * pick a word appear in the same sentence as the context word, and label the target as 1
> * randomly choose *k* words from the dictionary and label the target as 0
>   * though it is likely that those words would end up in the same sentence as the context word
> * use the word pair as input x and target as label y to form a supervised learning problem
> * *k* = 5 - 20 for small datasets
> * *k* = 2 - 5 for large datasets



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week2/02_learning-word-embeddings-word2vec-glove/images/7.PNG' width='80%'>

> * instead of learning a 10, 000 classes softmax algorithm
> * turn the task into a 10, 000 binary classification problem\
> * each time train *k* negative samples and 1 positive sample



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week2/02_learning-word-embeddings-word2vec-glove/images/8.PNG' width='80%'>

> $$
> P(w_i)=\frac{f(w_i)^{\frac{3}{4}}}{\sum_jf(w_j)^{\frac{3}{4}}}
> $$

***

#### <a name='glove'>glove word vectors</a>

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week2/02_learning-word-embeddings-word2vec-glove/images/9.PNG' width='80%'>

> $$
> X_{ij}=\# times\ i\ (t)\ appears\ in\ context\ of\ j\ (c)
> $$
>
> * It is possible that $X_{ij}=X_{ji}$:word i and word j have a symmetric relationship
>
> * $X_{ij}​$ capture how many times word i and word j appear together



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week2/02_learning-word-embeddings-word2vec-glove/images/10.PNG' width='80%'>

> $$
> minimize\ \sum_i \sum_j f(X_{ij})(\theta^T_ie_j+b_i+b_j^\prime-log(X_{ij}))^2
> $$
>
> $$
> weighting\ term: f(X_{ij})=0 \quad if\ X_{ij}=0
> $$
>
> * $f(X_{ij})$ avoids $log(X_{ij})$ going to negative infinity when $X_{ij}=0$
> * $f(X_{ij})$ balances the frequent words and the infrequent words
> * $\theta_i$ and $e_i$ are symmetric
>   * $e^{(final)}_{w}=\frac{e_w+\theta_w}{2}$  for every optimization step, $e^{(final)}_{w}$ can be obtained by the average of $e_w$ and $\theta_w$ get from gradient descent



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week2/02_learning-word-embeddings-word2vec-glove/images/11.PNG' width='80%'>

> * $\theta_i^T e_j = (A\theta_i)^T(A^{-T}e_j)=\theta_i^TA^TA^{-T}e_j$
>   * the embedding may learn some human-incomprehensible features along some axis rather than 'gender' , 'royal', and 'age'.
>   * but the parallelogram to deduce analogies still remains 

