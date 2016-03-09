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
    <tr>
      <th>'Til There Was You (1997)</th>
      <td>2.675676</td>
      <td>2.733333</td>
    </tr>
    <tr>
      <th>'burbs, The (1989)</th>
      <td>2.793478</td>
      <td>2.962085</td>
    </tr>
    <tr>
      <th>...And Justice for All (1979)</th>
      <td>3.828571</td>
      <td>3.689024</td>
    </tr>
    <tr>
      <th>1-900 (1994)</th>
      <td>2.000000</td>
      <td>3.000000</td>
    </tr>
    <tr>
      <th>10 Things I Hate About You (1999)</th>
      <td>3.646552</td>
      <td>3.311966</td>
    </tr>
    <tr>
      <th>101 Dalmatians (1961)</th>
      <td>3.791444</td>
      <td>3.500000</td>
    </tr>
    <tr>
      <th>101 Dalmatians (1996)</th>
      <td>3.240000</td>
      <td>2.911215</td>
    </tr>
    <tr>
      <th>12 Angry Men (1957)</th>
      <td>4.184397</td>
      <td>4.328421</td>
    </tr>
    <tr>
      <th>13th Warrior, The (1999)</th>
      <td>3.112000</td>
      <td>3.168000</td>
    </tr>
    <tr>
      <th>187 (1997)</th>
      <td>2.428571</td>
      <td>2.791667</td>
    </tr>
    <tr>
      <th>2 Days in the Valley (1996)</th>
      <td>3.488889</td>
      <td>3.244813</td>
    </tr>
    <tr>
      <th>20 Dates (1998)</th>
      <td>2.620690</td>
      <td>2.918182</td>
    </tr>
    <tr>
      <th>20,000 Leagues Under the Sea (1954)</th>
      <td>3.670103</td>
      <td>3.709205</td>
    </tr>
    <tr>
      <th>200 Cigarettes (1999)</th>
      <td>3.169014</td>
      <td>2.700000</td>
    </tr>
    <tr>
      <th>2001: A Space Odyssey (1968)</th>
      <td>3.825581</td>
      <td>4.129738</td>
    </tr>
    <tr>
      <th>2010 (1984)</th>
      <td>3.446809</td>
      <td>3.413712</td>
    </tr>
    <tr>
      <th>24 7: Twenty Four Seven (1997)</th>
      <td>5.000000</td>
      <td>3.750000</td>
    </tr>
    <tr>
      <th>24-hour Woman (1998)</th>
      <td>2.000000</td>
      <td>1.600000</td>
    </tr>
    <tr>
      <th>28 Days (2000)</th>
      <td>3.209424</td>
      <td>2.977707</td>
    </tr>
    <tr>
      <th>3 Ninjas: High Noon On Mega Mountain (1998)</th>
      <td>1.400000</td>
      <td>1.351351</td>
    </tr>
    <tr>
      <th>3 Strikes (2000)</th>
      <td>NaN</td>
      <td>2.750000</td>
    </tr>
    <tr>
      <th>301, 302 (1995)</th>
      <td>3.000000</td>
      <td>2.857143</td>
    </tr>
    <tr>
      <th>39 Steps, The (1935)</th>
      <td>3.965517</td>
      <td>4.107692</td>
    </tr>
    <tr>
      <th>400 Blows, The (Les Quatre cents coups) (1959)</th>
      <td>4.489362</td>
      <td>4.264286</td>
    </tr>
    <tr>
      <th>42 Up (1998)</th>
      <td>3.966667</td>
      <td>4.362069</td>
    </tr>
    <tr>
      <th>52 Pick-Up (1986)</th>
      <td>3.304348</td>
      <td>3.299145</td>
    </tr>
    <tr>
      <th>54 (1998)</th>
      <td>2.701754</td>
      <td>2.782178</td>
    </tr>
    <tr>
      <th>7th Voyage of Sinbad, The (1958)</th>
      <td>3.409091</td>
      <td>3.658879</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>Wrongfully Accused (1998)</th>
      <td>2.666667</td>
      <td>2.540541</td>
    </tr>
    <tr>
      <th>Wyatt Earp (1994)</th>
      <td>3.147059</td>
      <td>3.283898</td>
    </tr>
    <tr>
      <th>X-Files: Fight the Future, The (1998)</th>
      <td>3.489474</td>
      <td>3.493797</td>
    </tr>
    <tr>
      <th>X-Men (2000)</th>
      <td>3.682310</td>
      <td>3.851702</td>
    </tr>
    <tr>
      <th>X: The Unknown (1956)</th>
      <td>2.250000</td>
      <td>3.125000</td>
    </tr>
    <tr>
      <th>Xiu Xiu: The Sent-Down Girl (Tian yu) (1998)</th>
      <td>3.821429</td>
      <td>3.536585</td>
    </tr>
    <tr>
      <th>Yankee Zulu (1994)</th>
      <td>3.000000</td>
      <td>3.000000</td>
    </tr>
    <tr>
      <th>Yards, The (1999)</th>
      <td>2.687500</td>
      <td>3.360656</td>
    </tr>
    <tr>
      <th>Year My Voice Broke, The (1987)</th>
      <td>4.000000</td>
      <td>3.705882</td>
    </tr>
    <tr>
      <th>Year of Living Dangerously (1982)</th>
      <td>3.951220</td>
      <td>3.869403</td>
    </tr>
    <tr>
      <th>Year of the Horse (1997)</th>
      <td>NaN</td>
      <td>3.250000</td>
    </tr>
    <tr>
      <th>Yellow Submarine (1968)</th>
      <td>3.714286</td>
      <td>3.689286</td>
    </tr>
    <tr>
      <th>Yojimbo (1961)</th>
      <td>4.423077</td>
      <td>4.402116</td>
    </tr>
    <tr>
      <th>You Can't Take It With You (1938)</th>
      <td>4.192308</td>
      <td>3.921569</td>
    </tr>
    <tr>
      <th>You So Crazy (1994)</th>
      <td>3.666667</td>
      <td>2.300000</td>
    </tr>
    <tr>
      <th>You've Got Mail (1998)</th>
      <td>3.542424</td>
      <td>3.275591</td>
    </tr>
    <tr>
      <th>Young Doctors in Love (1982)</th>
      <td>1.923077</td>
      <td>2.742424</td>
    </tr>
    <tr>
      <th>Young Frankenstein (1974)</th>
      <td>4.289963</td>
      <td>4.239177</td>
    </tr>
    <tr>
      <th>Young Guns (1988)</th>
      <td>3.371795</td>
      <td>3.425620</td>
    </tr>
    <tr>
      <th>Young Guns II (1990)</th>
      <td>2.934783</td>
      <td>2.904025</td>
    </tr>
    <tr>
      <th>Young Poisoner's Handbook, The (1995)</th>
      <td>4.000000</td>
      <td>3.532258</td>
    </tr>
    <tr>
      <th>Young Sherlock Holmes (1985)</th>
      <td>3.514706</td>
      <td>3.363344</td>
    </tr>
    <tr>
      <th>Young and Innocent (1937)</th>
      <td>2.500000</td>
      <td>3.500000</td>
    </tr>
    <tr>
      <th>Your Friends and Neighbors (1998)</th>
      <td>2.888889</td>
      <td>3.536585</td>
    </tr>
    <tr>
      <th>Zachariah (1971)</th>
      <td>NaN</td>
      <td>3.500000</td>
    </tr>
    <tr>
      <th>Zed &amp; Two Noughts, A (1985)</th>
      <td>3.500000</td>
      <td>3.380952</td>
    </tr>
    <tr>
      <th>Zero Effect (1998)</th>
      <td>3.864407</td>
      <td>3.723140</td>
    </tr>
    <tr>
      <th>Zero Kelvin (Kj�rlighetens kj�tere) (1995)</th>
      <td>NaN</td>
      <td>3.500000</td>
    </tr>
    <tr>
      <th>Zeus and Roxanne (1997)</th>
      <td>2.777778</td>
      <td>2.357143</td>
    </tr>
    <tr>
      <th>eXistenZ (1999)</th>
      <td>3.098592</td>
      <td>3.289086</td>
    </tr>
  </tbody>
</table>
<p>3706 rows × 2 columns</p>
</div>




```python

```
