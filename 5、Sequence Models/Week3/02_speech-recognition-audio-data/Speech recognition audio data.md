## Speech recognition audio data

#### <a name='speech'>speech recognition & CTC cost</a>

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week3/02_speech-recognition-audio-data/images/1.PNG' width='80%'>

> *phonemes representation*



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week3/02_speech-recognition-audio-data/images/2.PNG' width='80%'>

> *'blank'* and *'space'* enable 1,000 outputs to represent only 19 characters

***

#### <a name='trig'>trigger word detection</a>

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week3/02_speech-recognition-audio-data/images/3.PNG' width='80%'>



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week3/02_speech-recognition-audio-data/images/4.PNG'>

> When the trigger word is said, the label is set to 1 and that lasts for some time in order to solve the imbalance of 0 and 1.

