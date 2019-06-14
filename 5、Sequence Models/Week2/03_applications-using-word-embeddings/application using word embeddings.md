## application using word embeddings

#### <a name='sentiment'>sentiment classification</a>>

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week2/03_applications-using-word-embeddings/images/1.PNG' width='80%'>

> the training set of sentiment classification would be small



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week2/03_applications-using-word-embeddings/images/2.PNG' width='80%'>

> * directly average all the embeddings of a sentence would work
> * but one downside: it ignores the word order of a sentence



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week2/03_applications-using-word-embeddings/images/3.PNG' width='80%'>

> * many-to-one model

***

#### <a name='debias'>debiasing word embeddings</a>>

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week2/03_applications-using-word-embeddings/images/4.PNG' width='80%'>



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week2/03_applications-using-word-embeddings/images/5.PNG' width='80%'>

> 1. identify the bias and non-bias direction
>
>    average $e_{he}-e_{she}$, $e_{male}-e_{female}$ ... ... to figure out the gender axis 
>
>    and find the non-gender-related direction
>
> 2. find the non-definitional word such as, babysitter, Doctor, ......
>
>    rather than grandfather, grandmother
>
> 3.  equalize distance from the gender-definitional word pairs to the non-gender-related axis

