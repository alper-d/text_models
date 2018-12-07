# Grid Search for twitter sentiment detection model

>Project aims a basic hyperparameter search on RCNN model for text classification task. Models are taken from brightmax's text classification models.

## Getting Started

Run the main file and add your embedding into a04_TextRCNN folder with name "wiki.tr". Format should be txt file.

### Prerequisites

Tenorflow 1.10.0 
gensim 3.5.0
word2vec 0.9.4

and their dependencies are required.

Any instance of skopt library import can be eliminated from code if gives error.


## Tests

Table| Negative        | Notr           | Positive  |
|---| ------------- |:-------------:| -----:|
|**experiment: learning_rate= 0.0005, batch_size= 20**| 0.69      | 0.32 | 0.35 |
|**experiment: learning_rate= 0.0005, batch_size= 40** | 0.61     | 0.28     |   0.30 |
|**experiment: learning_rate= 0.0005, batch_size= 80**| 0.59      | 0.25     |    0.24 |
|**experiment: learning_rate= 0.001, batch_size= 20**| 0.74       | 0.46 | 0.41 |
|**experiment: learning_rate= 0.001, batch_size= 40**| 0.71      | 0.45     |   0.37 |
|**experiment: learning_rate= 0.001, batch_size= 80**| 0.70     | 0.41      |   0.35 |
|**experiment: learning_rate= 0.01, batch_size= 20**| 0.42      | 0.33 | 0.35 |
|**experiment: learning_rate= 0.01, batch_size= 40**| 0.48      | 0.29      | - |
|**experiment: learning_rate= 0.01, batch_size= 80**| -   | -   |  - |

Tests are done with dataset:
1509 negative sentence 
1002 notr sentence 
987 positive sentence 

Pretrained word2vec is with shape(200.000x300)
