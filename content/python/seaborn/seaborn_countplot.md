---
title: "Seaborn count plot"
author: "Yagan Arun"
date: 2020-08-11
description: "-"
type: technical_note
draft: false
---

```python
import seaborn as sns 
import pandas as pd
DATA_PATH = '/Users/yaganarun/Documents/TACTII/kaggle_learnathon/mlnotes/content/python/heart.csv'
```


```python
df = pd.read_csv(DATA_PATH)
```


```python
# x must a column from your dataset
sns.countplot( x = 'target' , data = df)
```




    <AxesSubplot:xlabel='target', ylabel='count'>




![png](seaborn_countplot_3_1.png)



```python

```
