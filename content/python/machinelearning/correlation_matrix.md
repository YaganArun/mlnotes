---

title: "Correlation Matrix"
author: "TACT"
date: 2019-04-20
description: "-"
type: technical_note
draft: false

---
# Source
1.) Correlation Matrix => https://www.displayr.com/what-is-a-correlation-matrix/ <br>
2.) HeatMaps => https://towardsdatascience.com/better-heatmaps-and-correlation-matrix-plots-in-python-41445d0f2bec


```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
DATA_PATH = '/Users/yaganarun/Documents/TACTII/kaggle_learnathon/mlnotes/content/python/heart.csv'
```


```python
df = pd.read_csv(DATA_PATH)
df.head(3)
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
      <th>age</th>
      <th>sex</th>
      <th>cp</th>
      <th>trestbps</th>
      <th>chol</th>
      <th>fbs</th>
      <th>restecg</th>
      <th>thalach</th>
      <th>exang</th>
      <th>oldpeak</th>
      <th>slope</th>
      <th>ca</th>
      <th>thal</th>
      <th>target</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>63</td>
      <td>1</td>
      <td>3</td>
      <td>145</td>
      <td>233</td>
      <td>1</td>
      <td>0</td>
      <td>150</td>
      <td>0</td>
      <td>2.3</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>37</td>
      <td>1</td>
      <td>2</td>
      <td>130</td>
      <td>250</td>
      <td>0</td>
      <td>1</td>
      <td>187</td>
      <td>0</td>
      <td>3.5</td>
      <td>0</td>
      <td>0</td>
      <td>2</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>41</td>
      <td>0</td>
      <td>1</td>
      <td>130</td>
      <td>204</td>
      <td>0</td>
      <td>0</td>
      <td>172</td>
      <td>0</td>
      <td>1.4</td>
      <td>2</td>
      <td>0</td>
      <td>2</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
correlation_mat = df.corr() #df.corr returns the correlation matrix of the dataframe
correlation_mat
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
      <th>age</th>
      <th>sex</th>
      <th>cp</th>
      <th>trestbps</th>
      <th>chol</th>
      <th>fbs</th>
      <th>restecg</th>
      <th>thalach</th>
      <th>exang</th>
      <th>oldpeak</th>
      <th>slope</th>
      <th>ca</th>
      <th>thal</th>
      <th>target</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>age</th>
      <td>1.000000</td>
      <td>-0.098447</td>
      <td>-0.068653</td>
      <td>0.279351</td>
      <td>0.213678</td>
      <td>0.121308</td>
      <td>-0.116211</td>
      <td>-0.398522</td>
      <td>0.096801</td>
      <td>0.210013</td>
      <td>-0.168814</td>
      <td>0.276326</td>
      <td>0.068001</td>
      <td>-0.225439</td>
    </tr>
    <tr>
      <th>sex</th>
      <td>-0.098447</td>
      <td>1.000000</td>
      <td>-0.049353</td>
      <td>-0.056769</td>
      <td>-0.197912</td>
      <td>0.045032</td>
      <td>-0.058196</td>
      <td>-0.044020</td>
      <td>0.141664</td>
      <td>0.096093</td>
      <td>-0.030711</td>
      <td>0.118261</td>
      <td>0.210041</td>
      <td>-0.280937</td>
    </tr>
    <tr>
      <th>cp</th>
      <td>-0.068653</td>
      <td>-0.049353</td>
      <td>1.000000</td>
      <td>0.047608</td>
      <td>-0.076904</td>
      <td>0.094444</td>
      <td>0.044421</td>
      <td>0.295762</td>
      <td>-0.394280</td>
      <td>-0.149230</td>
      <td>0.119717</td>
      <td>-0.181053</td>
      <td>-0.161736</td>
      <td>0.433798</td>
    </tr>
    <tr>
      <th>trestbps</th>
      <td>0.279351</td>
      <td>-0.056769</td>
      <td>0.047608</td>
      <td>1.000000</td>
      <td>0.123174</td>
      <td>0.177531</td>
      <td>-0.114103</td>
      <td>-0.046698</td>
      <td>0.067616</td>
      <td>0.193216</td>
      <td>-0.121475</td>
      <td>0.101389</td>
      <td>0.062210</td>
      <td>-0.144931</td>
    </tr>
    <tr>
      <th>chol</th>
      <td>0.213678</td>
      <td>-0.197912</td>
      <td>-0.076904</td>
      <td>0.123174</td>
      <td>1.000000</td>
      <td>0.013294</td>
      <td>-0.151040</td>
      <td>-0.009940</td>
      <td>0.067023</td>
      <td>0.053952</td>
      <td>-0.004038</td>
      <td>0.070511</td>
      <td>0.098803</td>
      <td>-0.085239</td>
    </tr>
    <tr>
      <th>fbs</th>
      <td>0.121308</td>
      <td>0.045032</td>
      <td>0.094444</td>
      <td>0.177531</td>
      <td>0.013294</td>
      <td>1.000000</td>
      <td>-0.084189</td>
      <td>-0.008567</td>
      <td>0.025665</td>
      <td>0.005747</td>
      <td>-0.059894</td>
      <td>0.137979</td>
      <td>-0.032019</td>
      <td>-0.028046</td>
    </tr>
    <tr>
      <th>restecg</th>
      <td>-0.116211</td>
      <td>-0.058196</td>
      <td>0.044421</td>
      <td>-0.114103</td>
      <td>-0.151040</td>
      <td>-0.084189</td>
      <td>1.000000</td>
      <td>0.044123</td>
      <td>-0.070733</td>
      <td>-0.058770</td>
      <td>0.093045</td>
      <td>-0.072042</td>
      <td>-0.011981</td>
      <td>0.137230</td>
    </tr>
    <tr>
      <th>thalach</th>
      <td>-0.398522</td>
      <td>-0.044020</td>
      <td>0.295762</td>
      <td>-0.046698</td>
      <td>-0.009940</td>
      <td>-0.008567</td>
      <td>0.044123</td>
      <td>1.000000</td>
      <td>-0.378812</td>
      <td>-0.344187</td>
      <td>0.386784</td>
      <td>-0.213177</td>
      <td>-0.096439</td>
      <td>0.421741</td>
    </tr>
    <tr>
      <th>exang</th>
      <td>0.096801</td>
      <td>0.141664</td>
      <td>-0.394280</td>
      <td>0.067616</td>
      <td>0.067023</td>
      <td>0.025665</td>
      <td>-0.070733</td>
      <td>-0.378812</td>
      <td>1.000000</td>
      <td>0.288223</td>
      <td>-0.257748</td>
      <td>0.115739</td>
      <td>0.206754</td>
      <td>-0.436757</td>
    </tr>
    <tr>
      <th>oldpeak</th>
      <td>0.210013</td>
      <td>0.096093</td>
      <td>-0.149230</td>
      <td>0.193216</td>
      <td>0.053952</td>
      <td>0.005747</td>
      <td>-0.058770</td>
      <td>-0.344187</td>
      <td>0.288223</td>
      <td>1.000000</td>
      <td>-0.577537</td>
      <td>0.222682</td>
      <td>0.210244</td>
      <td>-0.430696</td>
    </tr>
    <tr>
      <th>slope</th>
      <td>-0.168814</td>
      <td>-0.030711</td>
      <td>0.119717</td>
      <td>-0.121475</td>
      <td>-0.004038</td>
      <td>-0.059894</td>
      <td>0.093045</td>
      <td>0.386784</td>
      <td>-0.257748</td>
      <td>-0.577537</td>
      <td>1.000000</td>
      <td>-0.080155</td>
      <td>-0.104764</td>
      <td>0.345877</td>
    </tr>
    <tr>
      <th>ca</th>
      <td>0.276326</td>
      <td>0.118261</td>
      <td>-0.181053</td>
      <td>0.101389</td>
      <td>0.070511</td>
      <td>0.137979</td>
      <td>-0.072042</td>
      <td>-0.213177</td>
      <td>0.115739</td>
      <td>0.222682</td>
      <td>-0.080155</td>
      <td>1.000000</td>
      <td>0.151832</td>
      <td>-0.391724</td>
    </tr>
    <tr>
      <th>thal</th>
      <td>0.068001</td>
      <td>0.210041</td>
      <td>-0.161736</td>
      <td>0.062210</td>
      <td>0.098803</td>
      <td>-0.032019</td>
      <td>-0.011981</td>
      <td>-0.096439</td>
      <td>0.206754</td>
      <td>0.210244</td>
      <td>-0.104764</td>
      <td>0.151832</td>
      <td>1.000000</td>
      <td>-0.344029</td>
    </tr>
    <tr>
      <th>target</th>
      <td>-0.225439</td>
      <td>-0.280937</td>
      <td>0.433798</td>
      <td>-0.144931</td>
      <td>-0.085239</td>
      <td>-0.028046</td>
      <td>0.137230</td>
      <td>0.421741</td>
      <td>-0.436757</td>
      <td>-0.430696</td>
      <td>0.345877</td>
      <td>-0.391724</td>
      <td>-0.344029</td>
      <td>1.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
plt.figure(figsize = (10,7))
sns.heatmap(correlation_mat)
```




    <AxesSubplot:>




![png](correlation_matrix_5_1.png)



```python

```
