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

In topic modeling, we followed a structured workflow to build an insightful topic model based on the Latent Dirichlet Allocation (LDA) algorithm.In this post, we will build the topic model using gensim’s native LdaModel and explore multiple strategies to effectively visualize the results using matplotlib plots. I will be using Amazon music review dataset since the focus is more on approaches to visualizing the results.

Let’s begin by importing the packages and the loading the dataset.
## Import Amazon Music Review Dataset
## Clean, Tokenize, & Lemmatize
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
