---
title: "Seaborn bar plot"
author: "Yagan Arun"
date: 2020-08-12
description: "-"
type: technical_note
draft: false
---

```python
import seaborn as sns 
import pandas as pd
```


```python
vehicle = [['audi',1] , ['appache',2] , ['benz',1] , ['lambhorghini',1] , ['Fazer' , 2]]
custom = pd.DataFrame(data=vehicle , columns=['vehicle','class'])
```


```python
# x must a column from your dataset
sns.barplot( x = custom['class'] , y = custom['vehicle'])
```




    <AxesSubplot:xlabel='class', ylabel='vehicle'>




![png](seaborn_barplot_3_1.png)



```python

```
