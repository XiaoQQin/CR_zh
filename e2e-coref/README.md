# chinese e2e-coref

## Introduction
chinese e2e-coref model,the base model is [e2e-coref](https://github.com/kentonl/e2e-coref).  
there are some changes:
- use [Chinese-Word-Vectors](https://github.com/Embedding/Chinese-Word-Vectors) replace the english [glove.840b.300d](https://nlp.stanford.edu/projects/glove/)
- as for **glove_50_300_2.txt** in original model,it use for head embedding.It's also glove embedding, 50 refers to the threshold for the minimum frequency of the vocabulary and 2 is the 
  windows size.you can see [e2e-coref/issues/30](https://github.com/kentonl/e2e-coref/issues/30) for detial.To be lazy，I use the same word embedding from [Chinese-Word-Vectors](https://github.com/Embedding/Chinese-Word-Vectors)
    :)
- use simplified-Chinese ELMo from [ELMoForManyLangs](https://github.com/HIT-SCIR/ELMoForManyLangs) replace english elmo
  
  

**Note!**: if you want to run the model,you must change some configurations int the **experiments.conf**  file

## Getting Started
- download the ontonotes5.0 dataset from LDC
- build custom kernels by running like the [kentonl/e2e-coref](https://github.com/kentonl/e2e-coref): ```./setup_all.sh```. If has a error like con't find file coref_kernels.cc ,you can change other kernels
- change to py2 environment and change the ontonode5.0 file path, run ```./setup_data.sh```
- change the embedding file path and run ```./setup_embedding.sh```

## Training Instructions

see the [kentonl/e2e-coref](https://github.com/kentonl/e2e-coref)


## result
I run the model in titan xp for 12 hours,the eval result as follow:
```
Average F1 (conll): 63.40%
Average F1 (py): 63.41%
Average precision (py): 71.28%
Average recall (py): 57.13%
```
