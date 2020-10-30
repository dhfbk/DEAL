# DEAL
DEAL (Detector of Abusive Language)

DEAL is a BERT-based classifier able to recognise abusive messages online. It is available for English and Italian, but more models will follow.
For English, the system is based on BERT tuned on a subset of 15k tweets from the Founta et al. (2018) dataset and evaluated on 3k domain-specific tweets annotated by three colleagues in the DH group and covering the death of George Floyd and the following period.
The classifier achieved the following results:

                     
|                |      P        |    R       |      F1     |
|----------------|---------------|------------|-------------|
|Non-Hate        |      0.975    |    0.794   |      0.875  |
|Hate            |      0.599    |    0.937   |      0.731. |


The English model can be dowloaded [here](https://drive.google.com/file/d/1CnEch1RVpydmPT-3GMttRh_0tNNNexku/view?usp=sharing)
  

For Italian, the model has been trained on the HaSpeeDe 2020 training set, for more details on the data and the task please check the task website (http://www.di.unito.it/~tutreeb/haspeede-evalita20/index.html).
The results obtained on HaSpeeDe test sets are reported below. The in-domain test contains tweets annotated as hateful or not. The out-of-domain test set includes instead news headlines, with the same kind of annotation.



|DocType   |    P Hate      |  R Hate      |  F1 Hate      |    P non-Hate     |  R non-Hate     |  F1 non-Hate      |     F1 average   |
|----------|-----------|---------|----------|----------|--------|----------|-----------|
|Tweets    |    0.727  |  0.800  |  0.762   |    0.785 |  0.708 |  0.745   |     0.753 |
|News      |    0.691  |  0.519  |  0.593   |    0.761 |  0.868 |  0.811   |     0.702 | 


BERT versions: for English we useuncased_L-12_H-768_A-12 model (https://github.com/google-research/bert) while for Italian we use AlBERTo (https://github.com/marcopoli/AlBERTo-it).
The pre-processing pipeline is the same for both the languages and includes tokenization, link and user mention replacement with URL and USER respectively, hashtag splitting with the Ekphrasis tool  (customized for Italian) and replacement of emojis with a textual description in the same language of the text. Code for pre-processing to be uploaded soon.

If you use this system please cite the paper:

```
Elisa Leonardelli, Stefano Menini and Sara Tonelli “Italian Hate Speech Detection via Self-Training and Oversampling”  
In Proceedings of the Seventh Evaluation Campaign of Natural Language Processing  (EVALITA 2020). 
```
