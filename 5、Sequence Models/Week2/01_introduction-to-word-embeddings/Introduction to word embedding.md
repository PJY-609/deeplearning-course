## Introduction to word embedding

#### <a name='word-repre'>word representation</a>

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week2/01_introduction-to-word-embeddings/images/1.PNG' width='80%' height='80%'>

> * the inner product of one-hot vectors is always zero
>   * cannot represent relation between two related words



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week2/01_introduction-to-word-embeddings/images/2.PNG' width='80%' height='80%'>



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week2/01_introduction-to-word-embeddings/images/3.PNG' width='80%' height='80%'>

***

#### <a name='emb'>using word embeddings</a>

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week2/01_introduction-to-word-embeddings/images/4.PNG' width='80%'>



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week2/01_introduction-to-word-embeddings/images/5.PNG' width='80%'>

> * difference between image encoding and word embedding
>   * word inputs are fixed vocabulary
>   * image inputs are arbitrary images

***

#### <a name='prop'>properties of word embeddings</a>

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week2/01_introduction-to-word-embeddings/images/6.PNG' width='80%'>

> * how word embeddings help reasoning analogies
>   $$
>   e_{man}-e_{woman}\approx \begin{bmatrix}-2\\0\\0\\0 \end{bmatrix}\\
>   e_{king}-e_{queen}\approx \begin{bmatrix}-2\\0\\0\\0 \end{bmatrix}
>   $$
>
>   $$
>   e_{man}-e_{woman}\approx e_{king}-e_{?}
>   $$



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week2/01_introduction-to-word-embeddings/images/7.PNG' width='80%'>

> $$
> Find\ word\ w:\ \mathop{argmax}_{w} sim(e_w, e_{king}-e_{man}+e_{woman})
> $$
>
> * cannot count on t-SNE to remain the parallelogram relationship
>   * t-SNE is a non-linear mapping



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week2/01_introduction-to-word-embeddings/images/8.PNG' width='80%'>

> $$
> sim(u,v)=\frac{u^Tv}{\|u\|_2\|v\|_2} \ or\ sim(u,v)=\|u-v\|^2
> $$

***

#### <a name='mat'>embedding matrix</a>

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week2/01_introduction-to-word-embeddings/images/9.PNG' width='80%'>

> $$
> E\cdot o_j=e_j=embedding\ for\ word\ j
> $$
>
> * in keras a special Embedding layer for word embedding
> * won't calculate the matrix multiplication

