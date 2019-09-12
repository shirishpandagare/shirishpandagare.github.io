---
title: "NLP with Deep Learning"
date: 2019-09-11
tags: [Deep Learning, LSTM, RNN]
header:
  image:
excerpt: "Deep Learning, LSTM, RNN"
mathjax: "true"
---

## Introduction

Human language is a method to convey where words are a *signifier* that maps to a *signified* idea or thing. NLP method is to design algorithms that ables a machine to learn "natural language" to perform the assigned task. There are different levels of tasks in NLP like speech processing to semantic interpretation and discourse processing. There are various levels of difficulties in the process of NLP.  

1. Easy:
* Spell Checking
* Keyword Search
* Finding Synonyms
2. Medium:
* Parsing information from websites, documents, etc.
3. Hard:
* Machine Translation (One language to another)
* Semantic Analysis (Meaning of the query statement)
* Coreference (what is the reference of "He" or "it" in the document.)
* Question Answering

Representing words is always a challenge in NLP. In a typical bag-of-words model, each word is a unique token with no relationship with other words. For example, words like "snow" and "boarding" will be assigned as unique tokens without any association even though they may frequently appear in the same sentence or context. Word2vec model can learn one iteration at a time and eventually be able to encode the conditional probability of a word given its context. The following is the idea for this model:

1. Design a model whose parameters are the word vectors.
2. Train this model on a certain dataset with an objective.
3. At every iteration, we shall evaluate the errors, penalize the model parameters that caused the error using update rule.
4. Thus we will learn our word vectors.




```python
from nltk import FreqDist
from nltk.corpus import stopwords
import pandas as pd
import re
import spacy
import matplotlib.pyplot as plt
import seaborn as sns
```

## Import Amazon Music Review Dataset


## Build the LDA Model


Here's some basic text.

And here's some *italics*

Here's some **bold** text.

What about a [link](https://github.com/dataoptimal)?

Here's a bulleted list:
* First item
+ Second item
- Third item

Here's a numbered list:
1. First
2. Second
3. Third

Python code block:
```python
    import numpy as np

    def test_function(x, y):
      z = np.sum(x,y)
      return z
```

R code block:
```r
library(tidyverse)
df <- read_csv("some_file.csv")
head(df)
```

Here's some inline code `x+y`.

Here's an image:
<img src="{{ site.url }}{{ site.baseurl }}/images/perceptron/linsep.jpg" alt="linearly separable data">

Here's another image using Kramdown:
![alt]({{ site.url }}{{ site.baseurl }}/images/perceptron/linsep.jpg)

Here's some math:

$$z=x+y$$

You can also put it inline $$z=x+y$$
