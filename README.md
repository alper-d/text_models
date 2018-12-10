# Grid Search for twitter sentiment detection model

>Project aims a basic hyperparameter search on RCNN model for text classification task. Models are taken from brightmax's text classification models.

## Getting Started

Run the main file and add your embedding into a04_TextRCNN folder with name "wiki.tr". Format should be txt file. Following word2vec is used.
https://github.com/facebookresearch/fastText/blob/master/pretrained-vectors.md

### Prerequisites

Tenorflow 1.10.0 
gensim 3.5.0
word2vec 0.9.4
For conda package manager

'''
conda create --name tw_sentiment

conda install --name tw_sentiment tensorflow=1.10.0

conda install --name tw_sentiment gensim=3.5.0

conda install --name tw_sentiment word2vec=0.9.4
'''

Any instance of skopt library import can be eliminated from code if gives error.

To download word2vec
wget -P 'directory_of_twitter_sentiment' https://s3-us-west-1.amazonaws.com/fasttext-vectors/wiki.tr.vec

##Usage
Activate your environment in anaconda shell by
'activate tw_sentiment'

navigate the each model's main.py file and write:
'python main.py'
Make sure that python is added to your path variable.


## Tests
F1 scores for RCNN model is obtained as in the table. Unfortunately, no worthy progress is obtained for other models.

Table| Negative        | Notr           | Positive  |
|---| ------------- |:-------------:| -----:|
|**experiment: learning_rate= 0.0005, batch_size= 20**| 0.69      | 0.32 | 0.35 |
|**experiment: learning_rate= 0.0005, batch_size= 40** | 0.61     | 0.28     |   0.30 |
|**experiment: learning_rate= 0.0005, batch_size= 80**| 0.59      | 0.25     |    0.24 |
|**experiment: learning_rate= 0.001, batch_size= 20**| 0.74       | 0.46    | 0.41 |
|**experiment: learning_rate= 0.001, batch_size= 40**| 0.71      | 0.45     |   0.37 |
|**experiment: learning_rate= 0.001, batch_size= 80**| 0.70     | 0.41      |   0.35 |
|**experiment: learning_rate= 0.01, batch_size= 20**| 0.42      | 0.33      | 0.35 |
|**experiment: learning_rate= 0.01, batch_size= 40**| 0.48      | 0.29      |   -  |
|**experiment: learning_rate= 0.01, batch_size= 80**|   -   |   -   |  -     |

Tests are done with dataset:
1509 negative sentence 
1002 notr sentence 
987 positive sentence 

95% percent of the data allocated for training, remaining is for testing.

Pretrained word2vec is with shape(200.000x300)
