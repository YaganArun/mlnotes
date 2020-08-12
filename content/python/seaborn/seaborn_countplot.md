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
```


```python
vehicle = [['audi',1] , ['appache',2] , ['benz',1] , ['lambhorghini',1]]
custom = pd.DataFrame(data=vehicle , columns=['vehicle','class'])
```


```python
# x must a column from your dataset
sns.countplot( x = 'class' , data = custom)
```




    <AxesSubplot:xlabel='class', ylabel='count'>




![png](seaborn_countplot_3_1.png)



```python

```
