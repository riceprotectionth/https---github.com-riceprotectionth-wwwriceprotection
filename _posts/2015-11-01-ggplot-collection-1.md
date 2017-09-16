---
layout: post
title: Distribution of data around the median plot by ggplot
excerpt: "ggplot collection 1"
tags: [ggplot2]
modified: 2015-10-16
comments: true
---

ผมได้แรงบันดาลใจจาก บทความฉบับนี้ **[Beyond Bar and Line Graphs: Time for a New Data Presentation Paradigm](http://journals.plos.org/plosbiology/article?id=10.1371/journal.pbio.1002128)**

เลยอยากจะทำกราฟ ซึ่ง สามารถเอาไปลองใช้ในงานวิจัยหรือรายงานของคุณนะครับ

<div style = "text-align:center"><img src ="/images/blog/journal.pbio.1002128.g001.PNG" width = "600"></div>


คุณลองดูซิครับ Bar graph ด้านซ้าย เมื่อพิจารณาดูแล้ว กราฟประเภทนี้ บอกคุณภาพของจ้อมูลได้แค่สองอย่าง นั้นคือ ค่า mean และ SE (stardard error) แต่ถ้ามองดูดีๆ

The full data may suggest different conclusions from the summary statistics. The means and SEs for the four example datasets shown in Panels B–E are all within 0.5 units of the means and SEs shown in the bar graph (Panel A). p-values were calculated in R (version 3.0.3) using an unpaired t-test, an unpaired t-test with Welch’s correction for unequal variances, or a Wilcoxon rank sum test. In Panel B, the distribution in both groups appears symmetric. Although the data suggest a small difference between groups, there is substantial overlap between groups. In Panel C, the apparent difference between groups is driven by an outlier. Panel D suggests a possible bimodal distribution. Additional data are needed to confirm that the distribution is bimodal and to determine whether this effect is explained by a covariate. In Panel E, the smaller range of values in group two may simply be due to the fact that there are only three observations. Additional data for group two would be needed to determine whether the groups are actually different.


ใครมี ความคิดที่ดีดี สามารถปรับ ประยุกติ์ code ที่ผมเสนอไป ลองไปนำไปใช้ดูนะครับ

[^1](http://journals.plos.org/plosbiology/article?id=10.1371/journal.pbio.1002128)
เป็นตัวอย่าง R code ที่ใช้ในงานวิจัยดังกล่าวครับ
[](https://cdn.rawgit.com/benmarwick/new-data-presentation-paradigm-using-r/582a80eaba654237231fe4b06d3eda5a61587d73/Weissgerber_et_al_supplementary_plots.html)

หลักๆ คือใช้ ```ggplot2``` package ครับในการสร้างกราฟ แต่ก็ที่จะสามารถส้รางกราฟก่อนนั้น ก็จะต้องมีการจัดข้อมูลและคำนวนค่าใหม่เสียก่อน

ผมลองใช้ database ที่คุ้นเคย iris ครับ
เราอยากจะเห็นว่าข้อมูลมีค่าความยาวของ petal ในแต่ละ species เป็นอย่างไร เมื่อเที่ยบกับค่า median อย่างไร

{% highlight r %}
> head(iris)
{% endhighlight %}

หน้าตาของข้อมูลก็จะออกมาเป็นแบบนี้ครับ

 Sepal.Length| Sepal.Width| Petal.Length| Petal.Width|Species |
|------------:|-----------:|------------:|-----------:|:-------|
|          5.1|         3.5|          1.4|         0.2|setosa  |
|          4.9|         3.0|          1.4|         0.2|setosa  |
|          4.7|         3.2|          1.3|         0.2|setosa  |
|          4.6|         3.1|          1.5|         0.2|setosa  |
|          5.0|         3.6|          1.4|         0.2|setosa  |
|          5.4|         3.9|          1.7|         0.4|setosa  |

{% highlight r %}
library(ggplot2)

f <- function(x, height) {
  ans <- median(x)
  data.frame(ymin = ans-height/2, ymax = ans+height/2, y = ans)
}

> ggplot(data = iris, aes(x = Species, y = Petal.Length)) + geom_jitter() +  
  stat_summary(fun.data = f, geom = "crossbar", height = 0.05, colour = NA, fill = "blue", width = 0.8, alpha = 0.5) +
  stat_summary(aes(label=..y..), fun.y=median, geom="text", size=8)
{% endhighlight %}

จากกราฟเราจะก็เห็นการกระจายของข้อมูล Petal length ของแต่ละ Species ว่าเป็นอย่างไร โดยมี medain bar เป็นแบ่ง ทั้งนี้ อยากจะเปลี่ยนเป็น ค่า mean ก็ได้นะครับโดย

{% highlight r %}
> ggplot(data = iris, aes(x = Species, y = Petal.Length)) + geom_jitter() +  
  stat_summary(fun.data = mean, geom = "crossbar", height = 0.05, colour = NA, fill = "blue", width = 0.8, alpha = 0.5) +
  stat_summary(aes(label=..y..), fun.y = mean, geom = "text", size = 8)
{% endhighlight %}

ครับ เท่านี้ ไม่ยากใช่ไหมครับ ผมว่ามันก็เป็นกราฟที่แสดงถึงการจะจายของข้อมูลที่ดี และสามารถอถิบายได้ เห็นภาพมากกว่าตัวเลข ใช่ไหมครับ
[^2](http://stackoverflow.com/questions/14966643/scatter-plot-of-same-variable-across-different-conditions-with-ggplot-facet-grid
http://stackoverflow.com/questions/8269016/ggplot2-boxplot-horizontal-bar-at-median)

[^3](http://stackoverflow.com/questions/5242174/how-to-label-graph-with-the-mean-of-the-values-using-ggplot2)

[^4](https://cdn.rawgit.com/benmarwick/new-data-presentation-paradigm-using-r/582a80eaba654237231fe4b06d3eda5a61587d73/Weissgerber_et_al_supplementary_plots.html)
