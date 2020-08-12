---
title: "Useful operations on a DataFrame"
author: "Yagan Arun"
date: 2020-08-12
description: "-"
type: technical_note
draft: false
---

```python
import pandas as pd
```


```python
cars = [['Audi' , 10] , ['Apple' , None] , ['Lambhorghini',10] , ['Bens',9] , ['Samsung',None] , ['Google',None] , ['Apple',None]]
df = pd.DataFrame(data = cars , columns = ['Cars' , 'Rating'])
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Cars</th>
      <th>Rating</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Audi</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Apple</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Lambhorghini</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Bens</td>
      <td>9.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Samsung</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Google</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Apple</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Operation 1 : finding columns in a dataframe
df.columns
```




    Index(['Cars', 'Rating'], dtype='object')




```python
# Operation 2 : knowing the row and columns in a dataframe
row , column = df.shape[0] , df.shape[1]
print('no of rows : {} , no of columns : {} '.format(row , column))
```

    no of rows : 7 , no of columns : 2 



```python
# Operation 3 : Knowing first 5 rows in a dataframe 
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Cars</th>
      <th>Rating</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Audi</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Apple</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Lambhorghini</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Bens</td>
      <td>9.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Samsung</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Operation 4 : Knowing last 5 rows in a dataframe 
df.tail()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Cars</th>
      <th>Rating</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2</th>
      <td>Lambhorghini</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Bens</td>
      <td>9.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Samsung</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Google</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Apple</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Operation 5 : To know unique values in a dataframe ==> df.column_name.unique()
df.Cars.unique()
```




    array(['Audi', 'Apple', 'Lambhorghini', 'Bens', 'Samsung', 'Google'],
          dtype=object)




```python
# Operation 6 : getting count of each entities in a column.
df['Cars'].value_counts()
```




    Apple           2
    Lambhorghini    1
    Samsung         1
    Bens            1
    Google          1
    Audi            1
    Name: Cars, dtype: int64




```python
# Operation 7 : grouping data in a data frame
# here dataframe is grouped based on rating 
df.groupby(['Rating'])['Cars'].count()
```




    Rating
    9.0     1
    10.0    2
    Name: Cars, dtype: int64




```python

```
