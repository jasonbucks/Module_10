# Module_10 - Unsupervised Learning

   ![Charts Picture](Images/10-5-challenge-image.png)

Competition in the financial advisory sector is fierce, so I want to propose a novel approach to assembling investment portfolios that are based on cryptocurrencies.  Instead of using only returns and volatility, I'll include other factors that might impact the crypto market leading to a better portfolio performance.  This is a prototype for submitting my crypto portfolio proposal to the company board of directors.  

---

## Technologies

I'll leverage python 3.7.11 with the following packages:

* [pandas](https://pandas.pydata.org) - Use the Pandas library, along with JupyterLab, to collect, prepare and analyze data.

* [scikit-learn](https://scikit-learn.org/stable/user_guide.html) - Simple and efficient tools for data analysis.

* [HoloViz (formerly PyViz)](https://holoviz.org) - Data visualization tool hvPlot.

---

## Installation Guide

Before running the application first import the following libraries:

```python
  import pandas as pd
  import hvplot.pandas
  from path import Path
  from sklearn.cluster import KMeans
  from sklearn.decomposition import PCA
  from sklearn.preprocessing import StandardScaler
```

Before running, make sure that scikit-learn and hvplot are installed on your machine by running:
  
```console  
  conda list scikit-learn
  conda list hvplot
```  
  
If either are not installed, install them while in the Conda dev environment:

```console
  pip install -U scikit-learn
  conda install -c pyviz hvplot
```  

---

## Usage and Conclusions

This project combines financial Python programming skills plus my new unsupervised learning skills.  The primary work product will be a Jupyter notebook that clusters cryptocurrencies by thier performances over different time durations.  These results are then plotted so everyone on the board can see the performance visually.   The main conclusions are
* Whether we use the original data features (8 columns showing returns for periods of varying durations) or reduce these features to just 3 using principal component analysis (PCA), the optimal number of data clusters for analysis is shown to be 4.
* Since the PCA components explain about 90% of the total variance of the original features, it follows that the clustering is nearly identical whether we use the original features or the PCA features in our KMeans analysis.
* These 4 clusters consist of 2 large clusters, each containing about half of the cryptocurrencies in our dataset, plus 2 additional clusters that each contain just one outlier cryptocurrency.
* Of the 2 larger clusters, the primary features that separate them from each other appears to be the short term returns (7day and 14day), with one cluster showing returns above the mean during these two durations and the other cluster showing returns below the mean.  The 24hour returns as well as the mid- and long-term returns (30days and above) are evenly represented in each of these two clusters.
* The first outlier cluster contains only ethlend.  This crypto was an outlier because it had a) by far the largest negative return over the 24hour duration, but also because b) it has the largest postivie returns for the 200day and 1year durations.
* The other outlier was celsius-degree-token.  This crypto earned its outlier status by having by far the largest returns over the mid-term durations (14days, 30days and 60days).

---

## Contributors

Starter code was provided by UW Fintech Bootcamp.  Updates and analysis by Jason Buckholt.  

---

## License

MIT License

Copyright (c) 2022 Jason Buckholt

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
