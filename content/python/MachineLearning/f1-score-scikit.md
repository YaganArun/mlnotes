---

title: "List Comprehension"
author: "TACT"
date: 2019-04-20
description: "-"
type: technical_note
draft: false

---

```python
from sklearn.metrics import f1_score
```


```python
y_true = [0, 1, 2, 0, 1, 2]
y_pred = [0, 2, 1, 0, 0, 1]
```


```python
f1_score_ = f1_score(y_true , y_pred , average='micro')
f1_score_
```




    0.3333333333333333




```python

```
