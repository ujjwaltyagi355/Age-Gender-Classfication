# Age and Gender prediction Model (Trained on Indian Faces)

This is the Age and Gender prediction model built using Convolutional Neural Networks in Python.
The model was insitially built on the basis of Research Paper by [Gil Levi and Tal Hassner](https://talhassner.github.io/home/publication/2015_CVPR "Age and Gender Classification Using Convolutional Neural Networks").
<br />
But the achitecture of the pretrained model did not perform well on Indian Dataset.<br />
So the model was Re-trained Using VGG-16 as the backbone for the model.<br />
The dataset used are [UTKFace Dataset](https://susanqq.github.io/UTKFace/ "Large Scale Face Dataset") and [FairFace Dataset](https://arxiv.org/abs/1908.04913 "FairFace: Face Attribute Dataset for Balanced Race, Gender, and Age") out of which Indian Race faces were seperated and the model was trained with.

## Repository Structure

This Repository contains the notebook and Python code used for building the Age model, the Gender model and the notebook used for testing thier performance.<br /> The _Pretrained-Model_ folder contains the links to the pretrained model of Age and Gender which could be used for testing and re-training purposes. The weights are saved in `.h5` format and the model is saved in `.json` format.

## Frameworks used

-   Tensorflow &nbsp;&nbsp; `pip install tensorflow`
-   Numpy &nbsp;&nbsp; `pip install numpy`
-   Keras &nbsp;&nbsp; `pip install keras`
-   Pillow &nbsp;&nbsp; `pip install pillow`

## Performance of model

The output of the model consists of:<br />
2 classes for Gender Prediction, namely `Male` and `Female` <br /> 
9 classes for the Age Prediction, which are `(0-2)`, `(3-9)`, `(10-19)`, `(20-29)`, `(30-39)`, `(40-49)`, `(50-59)`, `(60-69)`, `(70+)`. <br />
The table below shows the performance of model when tested on `13835` images containing Indian faces only.

**Naming Convention used**: _True_ or _False_ represent whether the prediction is Right or Wrong Respectively. _Male_ or _Female_ represents what the model predicted.
For eg: _False Female_ means the model predicted Wrong and Prediction was Female. Which means actually it was Male.

| Age Group   | True Male | False Male | True Female | False Female |
| ----------- | --------- | ---------- | ----------- | ------------ |
| **(0-2)**   | 72        | 15         | 77          | 23           |
| **(3-9)**   | 711       | 71         | 738         | 193          |
| **(10-19)** | 945       | 55         | 602         | 113          |
| **(20-29)** | 1844      | 79         | 1438        | 99           |
| **(30-39)** | 1263      | 60         | 1725        | 71           |
| **(40-49)** | 718       | 28         | 1039        | 49           |
| **(50-59)** | 424       | 23         | 628         | 39           |
| **(60-69)** | 228       | 18         | 236         | 19           |
| **(70+)**   | 102       | 16         | 63          | 11           |

The Accuracy achieved in Gender Prediction is `92.9%`

Below shown is the Confusion matrix of Age Prediction
|Age Group|(0-2)|(3-9)|(10-19)|(20-29)|(30-39)|(40-49)|(50-59)|(60-69)|(70+)|
| --- | --- | --- | --- | --- |---| --- | --- | --- | --- |
|**(0-2)**|**102**|3|3|0|1|0|0|0|0|
|**(3-9)**|5|**1471**|121|72|17|17|4|1|5|
|**(10-19)**|2|132|**1270**|214|41|42|8|4|2|
|**(20-29)**|72|43|118|**2909**|178|187|18|5|2
|**(30-39)**|2|37|68|581|**1966**|389|57|15|4|
|**(40-49)**|0|14|14|137|94|**1484**|72|19|0
|**(50-59)**|1|3|9|51|45|237|**737**|27|4|
|**(60-69)**|0|6|5|15|9|83|52|**321**|10|
|**(70+)**|1|0|2|4|4|25|9|17|**130**|

The Accuracy achieved in Age Prediction is `75.09%`(exact) and `91.09%`(1-off).

<h3> Do 🌟 the Repo Is you like It...</h3>
