---
title: Research
layout: page
---
<div style = "text-align:center"><img src ="http://farm4.static.flickr.com/3308/3314007686_9564a38d68_o.gif"></div>

# Research

#### Network analysis: Network analysis for characterizing the patterns of pests and diseases occurrence in lowland rice growing areas, South and Southeast Asia

## Summary

Briefly, what I am doing is to develop network theory to  produce the network models of pests and diseases co-occurrence . The aim of the network model
is to capture the patterns and the relationships between the injury variables, compare the structure of network models constructed by different locations and different cropping practices. The results potentially support the crop management improvement and optimize the crop

I did my PhD research project on Crop Health Management under the supervision of [Dr. Adam H. Sparks](https://about.me/adamhsparks).


![](https://tenureshewrote.files.wordpress.com/2013/12/phd121003s-1.gif)

Thank you very much paying the attention to my research and my poster. If you are opening this page, It means that you are attending the APPS (Australasian Plant Society) conference 2015.

The contents of this page provide you details of the sources of data, materials and methods with Rscripts. You can download the pdf file of [my poster](https://github.com/sithjaisong/sithjaisong.github.io/raw/master/img/APPS_Poster_Sith.pdf) and [my abstract](https://github.com/sithjaisong/sithjaisong.github.io/raw/master/img/APPS_Abstract_Sith.pdf) .

## objective
The main objective of this study is to propose the criteria of choosing the suitable correlation measures, then the correlation coefficients will be used for network construction.

### Survey Data collection

These are R scripts used to perform co-occurrence analysis following the poster submitted to the APPS conference, Demonstrating co-occurrence pattern analyzes of crop health survey data.

``data``  in the scripts is the survey data that we use in the analysis.
The data tables of crop health are organized as the following:

#### Survey data

<div style = "text-align:center"><img src ="/images/blog/injury_profiles.jpg" width = "600"></div>



**Injuries on leaves** are represented by number of damaged leaves counted in each of the 10 sampled hills or quadrats represented by caused by leaf-feeding insects, such as whorl maggots (WM), leaffolders (LF), and foliar disease such as bacterial leaf blight (BLS), bacterial leaf streak (BLS), brown spot (BS), leaf blast (LB).

**Sucking or grain-damaging insects** are represented by number of individuals: brown planthoppers (BPH), whitebacked planthoppers (WPH), rice bugs (RB) and green leafhoppers (GLH)

**Systemic diseases** are represented by the number of infected hills out of a total of 50 hills. Rice tungro disease (RTD), ragged stunt disease (RSD).

**Injuries on panicle** counted as number per hill or quadrat consists deadhearts (DH), whiteheads (WH), silver shoot (SS) disease on panicle; false smut (FSM), sheath blight (SHB), sheath rot (SHR), dirty panicle (DP), neck blast (NB) including damages from rats.


## Survey data structure

Collected survey data are showed as the table below. Each column are represented the variables and each rows are represented the farmers' fields.



|Field |BB |HB | GSD |RSD | RTD| TSD |...|
|:---|:---|:---|:---|:---|:---|:---|:---|
|1  |20 |30 |17 |11 |30 |10 |...|
|2  |20 |20 |10 |12 |17 |12 |...|
|3  |15 |12 |20 |21 |0 |13 |...|
|4  |15 |7 |22 |20 |20 |20 |...|
|5  |15 |12 |20 |20 |20 |20 |...|


## Choosing the suitable correlation measures
The objective of this study is to select the suitable correlation measures for this survey data. To construct the proper network and network analysis, I proposed three criteria to determine which correlation measures.

- #### check
- #### compare
- #### identify


I aim to find the relationships among pests. There are three possible outcomes of combined pest infestation. no interactions, synergistic interactions, anagogic interactions

The evaluation of correlation measures is needed before performing network analysis because the correlation coefficients affect the behavior and topological properties of the network model.


### 1. Check by explore the survey data

The data distribution should be explored first. Because many statistic approaches assume that the data should be normally distributed.

#### **Histograms**
{% highlight R %}
ggplot(data, aes(x = value)) + geom_histogram(stat = "bin")
{% endhighlight %}

<div style = "text-align:center"><img src= "/images/blog/histoallre.jpg" width="580"/></div>

The histograms were shown that the collected data of each variable are not fit the normal distribution very well. The structure of data was mostly at zero and sparsely scatter.

Parametric tests assume that your data fit the normal distribution. If your measurement variable is not normally distributed, you may be increasing your chance of a false positive result if you analyze the data with a test that assumes normality.

#### **Shapiro-Wilk normality test**

<script src="https://gist.github.com/sithjaisong/edcbe94ace6e5d790917.js"></script>

### 2. Compare the similarity of different correlation measures

There are several correlation measures to come up with. Pearson, Spearman, Kendall correlation, Biweight midweight are selected because they can yield the correlation coefficients ranging from -1 to 1. If  -1 means the negative correlation of pairwise relationships, 0 means no relationships between a pair of variables, and 1 means positive relationships.


<div style = "text-align:center"><img src ="/images/blog/cluster.jpg"></div>

From heatmap and dendrograms, two groups emerge.

1. Spearman and Kendall correlation group (Nonparametric correlation)
2. Pearson and Biweight midcorrelation (Parametric correlation)

From the previous step would give the clue that which one should be selected. Parametric correlation assume that data normally distributed. Therefor, Nonparametric correlation measures seem suitable with this data. However, there still are Spearman and Kendall correlation.

### 3. Identify

From the previous step, Spearman correlation measure can detect the relationships between brown planthoppers and whitebacked planthoppers but not by other correlation measures.

<script src="https://gist.github.com/sithjaisong/8b513036147518b35c7e.js"></script>

<div style = "text-align:center"><img src= "/images/blog/bphwbph.jpg" width="580"/></div>


### Network visualization

From three criteria, finally Spearman's correlation measure is the most suitable approach for this data because
-  data are not normal distributed,
- correlation coefficient from nonparametric and parametric correlation, and
- it can detect the biological relationship of this data.


<div style = "text-align:center"><img src ="/images/blog/network.jpg" width="580"></div>
