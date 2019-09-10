---
title: "LDA Topic Modeling"
date: 2017-12-01
tags: [LDA, Text Mining, Topic Modeling]
header:
  image: "/images/wordcloud.png"
excerpt: "LDA, Text Mining, Topic Modeling"
mathjax: "true"
---

## Introduction

In topic modeling, I followed a structured workflow to build an insightful topic model based on the Latent Dirichlet Allocation (LDA) algorithm. In this post, I will build the topic model using gensim’s native LdaModel and explore multiple strategies to effectively visualize the results using matplotlib plots. I will be using Amazon digital music review dataset for demonstration.
Let’s begin by importing the packages. The following are the packages imported for this project.

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

For this project, I’ll use the review dataset from the [Amazon product data](http://jmcauley.ucsd.edu/data/amazon/) repository of the University of California, San Diego. In this repository, there are small sample dataset of the product reviews for each category. The parser I will develop can be applied to any of the product categories, however, I have selected [Digital Music reviews dataset](http://snap.stanford.edu/data/amazon/productGraph/categoryFiles/reviews_Digital_Music_5.json.gz) for the sake of simplicity.

The following function is to load the dataset from the repository:
```python
"""Function to load dataset"""
def load_data(path):
    data = pd.read_json(path)
    return data
```
The dataset should look something like this:

<img src="{{ site.url }}{{ site.baseurl }}/images/01_LDA/data_head_Sample.png" alt="linearly separable data">

## Clean, Tokenize, & Lemmatize
The following function will remove the special characters from the review text, lowercase the words, tokenize and lemmatize the text.
```python
"""Function to load dataset"""
def remove_characters(self, sentence):
        sentence = re.sub( r"\W", " ", sentence, flags=re.I )
        return sentence

def lower_case(self, sentence):
    sentence = sentence.split()
    x_list = [word.lower() for word in sentence]
    return " ".join( x_list )

def remove_stopwords(self, sentence):
    word_list = [word for word in sentence.split() if word not in self.stop_words]
    sentence = " ".join( word_list )
    return sentence

def word_length(self, sentence):
    word_list = [word for word in sentence.split() if len( word ) > 3]
    sentence = " ".join( word_list )
      return sentence
```



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
