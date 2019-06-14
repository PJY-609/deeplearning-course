## Various Seq-2-Seq models

####   <a name='basic'>basic models</a>

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week3/01_various-sequence-to-sequence-architectures/images/1.PNG' width='80%'>

> * encoder-decoder



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week3/01_various-sequence-to-sequence-architectures/images/2.PNG' width='80%'>

***

#### <a name='pick'>picking the most likely sentence</a>

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week3/01_various-sequence-to-sequence-architectures/images/3.PNG' width='80%'>

> * conditioned language model $P(y^{<1>},\cdots,y^{<T_y>}|x^{<1>},\cdots,x^{<T_x>})$



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week3/01_various-sequence-to-sequence-architectures/images/4.PNG' width='80%'>



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week3/01_various-sequence-to-sequence-architectures/images/5.PNG' width='80%'>

> *greedy search*
>
> ​	Since *'going'* is a much more common word, $P('Jane'\ 'is'\  'going'|x)>P('Jane'\ 'is'\ 'visiting'|x)$ is possible. Therefore, the second sentence is more likely to be chosen, if *greedy search* applied.

***

#### <a name='beam'>beam search</a>

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week3/01_various-sequence-to-sequence-architectures/images/6.PNG' width='80%'>

> *Step 1*
>
> ​	Get the softmax output $\hat y^{<1>}$ , and memorize the top $\# beam\ width$ words



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week3/01_various-sequence-to-sequence-architectures/images/7.PNG' width='80%'>

> *step 2*
>
> ​	Instantiate $\#beam\ width$ copies of networks to evaluate all $\#beam\ width \times\ vocab\  size$ possibilities.
>
> ​	Calculate $P(y^{<1>}, y^{<2>}|x)=P(y^{<1>}|x)P(y^{<2>}|x, y^{<1>})$ 
>
> ​	Select the top $\# beam\ width$ from all $\#beam\ width \times \ vocab\ size$
>
> ​	Reject the $1^{st}$ option *september* if the sequence selected contains that word already 



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week3/01_various-sequence-to-sequence-architectures/images/8.PNG' width='80%'>

***

#### <a name='refine'>refinements to beam search</a>

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week3/01_various-sequence-to-sequence-architectures/images/9.PNG' width='80%'>

> $\arg \max _{y} \sum_{y}^{T_{y}} \log P\left(y^{<t>} | x, y^{<1>}, \ldots, y^{<t-1>}\right)$ tends to prefer shorter sequences, as long sequences tends to get more negative in the objective function
>
> Use *normalized log likelihood objective* to evaluate all the possible sequences



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week3/01_various-sequence-to-sequence-architectures/images/10.PNG' width='80%'>

***

#### <a name='error'>error analysis in beam search</a>>

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week3/01_various-sequence-to-sequence-architectures/images/11.PNG' width='80%'>

> Find whether *RNN* or *Beam Search* is to blame



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week3/01_various-sequence-to-sequence-architectures/images/12.PNG' width='80%'>



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week3/01_various-sequence-to-sequence-architectures/images/13.PNG' width='80%'>

***

#### <a name='bleu'>BLEU score </a>

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week3/01_various-sequence-to-sequence-architectures/images/14.PNG' width='80%'>

> $Precision=\frac{7}{7}$ : counting the number of times when words of the output appear in references
>
> $Modified\ Precision= \frac{2}{7}$ for example, the word *'the'* only appear twice at most in references



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week3/01_various-sequence-to-sequence-architectures/images/15.PNG' width='80%'>

> *Bigrams*: 2 words appear together
>
> $Count$ & $Count_{clip}$



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week3/01_various-sequence-to-sequence-architectures/images/16.PNG'  width='80%'>

> $$
> unigram:\quad p_1=\frac{\sum_{unigrams \in \hat y}Count_{clip}(unigram)}{\sum_{unigram \in \hat y}Count(unigram)}
> $$
>
> $$
> n-gram: \quad p_n=\frac{\sum_{n-gram \in \hat y}Count_{clip}(n-gram)}{\sum_{n-gram \in \hat y}Count(n-gram)}
> $$



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week3/01_various-sequence-to-sequence-architectures/images/17.PNG' width='80%'>

> *Brevity penalty*: penalize shorter output
>
> *BLEU score* is a useful single row sentence evaluation to see whether the generated piece of text have the similar meanings of the references

***

#### <a name='att'>attention model</a>

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week3/01_various-sequence-to-sequence-architectures/images/18.PNG' width='80%'>



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week3/01_various-sequence-to-sequence-architectures/images/19.PNG' width='80%'>

> attention weights $\alpha^{<t,t^{\prime}>}$ based on $a^{<t>}$ and $S^{<t-1>}$



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week3/01_various-sequence-to-sequence-architectures/images/21.PNG' width='80%'>

> $$
> a^{<t^\prime>}=(\overrightarrow{a^{<t^\prime>}},\overleftarrow{a^{<t^\prime>}})
> $$
>
> $$
> \sum_{t^\prime}\alpha^{<t,t^\prime>}=1
> $$
>
> $$
> c^{<t>}=\sum_{t^{\prime}}\alpha^{<t,t^\prime>}a^{<t^\prime>}
> $$



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week3/01_various-sequence-to-sequence-architectures/images/22.PNG' width='80%'>

> train a neural network the deduce $e^{<t,t^\prime>}$ from $s^{<t-1>}$ and $a^{<t^\prime>}$

