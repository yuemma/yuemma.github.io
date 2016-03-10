---
layout: post
title: movies data analysis
category: python
tags: python
description: movies data analysis
---


```python
import pandas as pd
unames = ['user_id', 'gender', 'age', 'occupation', 'zip']
users = pd.read_table('..pydata/ch02/movielens/users.dat', sep='::', header=None, names=unames, engine='python')

rnames = ['user_id', 'movie_id', 'rating', 'timestamp']
ratings = pd.read_table('..pydata/ch02/movielens/ratings.dat', sep='::', header=None, names=rnames, engine='python')

mnames = ['movie_id', 'title', 'genres']
movies = pd.read_table('..pydata/ch02/movielens/movies.dat', sep='::', header=None, names=mnames, engine='python')

#合并三个表格
data = pd.merge(pd.merge(ratings, users), movies)
#按性别计算每部电影的平均得分
mean_ratings = data.pivot_table(values='rating', index='title', columns='gender', aggfunc='mean')

```


```python
mean_ratings
```

##运行结果如下


<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th>gender</th>
      <th>F</th>
      <th>M</th>
    </tr>
    <tr>
      <th>title</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>$1,000,000 Duck (1971)</th>
      <td>3.375000</td>
      <td>2.761905</td>
    </tr>
    <tr>
      <th>'Night Mother (1986)</th>
      <td>3.388889</td>
      <td>3.352941</td>
    </tr>
  </tbody>
</table>
<p>3706 rows × 2 columns</p>
</div>




```python

```
