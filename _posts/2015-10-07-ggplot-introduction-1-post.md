---
layout: post
title: ggplot2 part 1
excerpt: "เบื้องต้นเกี่ยวกับ ggplot2 และ graphic grammar"
tags: [ggplot2]
modified: 2015-10-16
comments: true
---

ggplot2 เป็น package ที่ถือว่ายอดนิยมหนึ่ง ใน R ggplot2 เป็น package ที่ใช้เพื่อการสร้างกราฟ เขียนโดย Hadley Wickham เป็นคนที่มีบทบาทและมีอิทธิพลต่อการพัฒนา R อย่างมากคนหนึ่ง เขาเขียน package ที่สำคัญๆ หลายๆ package ใน R เช่น plyr, dplyr, reshape, reshape2 และอยู่เบื้อหลัง package ที่สำคัญหลายๆ package ggplot2 package มีหลักการในสร้างกราฟด้วยการเขียนคำสั่ง โดย ลักษณะการเขียนโดยอิงกับหลักการ grammar of graphic โดย Leland Wilkinson หลักการ คือ การสร้างกราฟแบบ layer หรือ ซ้อนทับกันเป็นชั้นๆ

ผมจะอธิบายหลักการด้วยตัวอย่าง ลอง ทำกันดูนะครับ
สำคัญ ggplot2 นะครับ ไม่ใช่ ggplot

{% highlight r %}
> library(ggplot2)
{% endhighlight %}

ผมจะขอเล่นกับ ข้อมูล การทดลองเรื่องชนิดของอาหาร(feed) นั้น มีผลต่อน้ำหนักของไก่ หรือไม่อย่างไร

{% highlight r %}
> data(chickwts)
> head(chickwts)
weight feed
1 179 horsebean
2 160 horsebean
3 136 horsebean
4 227 horsebean
5 217 horsebean
6 168 horsebean
> str(chickwts)
'data.frame': 71 obs. of 2 variables:
$ weight: num 179 160 136 227 217 168 108 124 143 140 ...
$ feed : Factor w/ 6 levels "casein","horsebean",..: 2 2 2 2 2 2 2 2 2 2 ...
{% endhighlight %}

เอาหละ ที นี้ เราเห็นลักษณะของโครงสร้างข้อมูลแล้วใช่ไหมครับ ว่า เรามีลักษณะของอาหารเลี้ยงไก่อยู่ หก ชนิด ซึ่งเราอย่างจะเปรียบเทียบว่าอาหารชนิดไหน นะ ที่ ให้น้ำหนักไก่มากที่สุด

ผมเลือกที่จะสร้าง boxplot ครับ

เอาหละ เรามาสร้าง ด้วย ggplot กันเลย

{% highlight r %}
> ggplot()
Error: No layers in plot
{% endhighlight %}

เห็นไหมหละครับ ว่า โปรแกรมฟ้องส่า เรายังไม่ใส่ layer เลย เอา เราจะใส่ layer ครับ

{% highlight r %}
> ggplot(data = chickwts, aes(x = feed, y = weight)) + geom_boxplot()
> # เหมือนกัน
> ggplot() + geom_boxplot(aes(x = feed, y = weight), data = chickwts)
{% endhighlight %}

`ggplot()` เป็นการบอกว่าเราจะใช้ ggplot นะ หลังจากนั้น `geom_boxplot()` บอกว่าเราจะสรา้งกราฟ boxplot นะ

บอกก่อนเลยนะครับ ว่า ส่วนตัวผม ผมจะ ใส่คำสั่งแต่แรกเลยว่า จะส้รางกราฟด้วยข้อมูลอะไร
เช่น

{% highlight r %}
> ggdata <- ggplot(                                                )
>                   data =           ,
>                          chickwts
>                                     aes(                      )
>                                          x = feed
>                                                   , y = weight
{% endhighlight %}

`aes ` ย่อมากจาก aesthetics ครับ โดยเราจะต้องบอกว่า จะให้แกน X คืออะไร และแกน Y คืออะไร
แต่ แค่นี้ เราจะไม่ได้บอกว่าเราจะสรา้งกราฟอะไร
ดีงนั้น ต้องใส้ `layer`

{% highlight r %}
> ggdata
Error: No layers in plot
{% endhighlight %}

เห็นไหม ว่าเราสร้างกราฟยังไม่ได้ จะต้องใส่ layer

{% highlight r %}
> ggdata + geom_boxplot()
{% endhighlight %}

<div style = "text-align:center"><img src="/images/blog/box.png"></div>

เราไม่ชอบพื้นหลังสีขาว

{% highlight r %}
> ggdata + geom_boxplot() + theme.gray()
{% endhighlight %}

<div style = "text-align:center"><img src="/images/blog/boxtheme.png"></div>

{% highlight r %}
> ggdata + geom_boxplot(aes(fill = feed) + theme.gray()
{% endhighlight %}

<div style = "text-align:center"><img src="/images/blog/boxcolor.png"></div>

อยากรู้ว่า ข้อมูล กระจายตัวอย่างไร บน boxplot ก็ใส่ได้

{% highlight r %}
> ggdata + geom_boxplot(aes(fill = feed)) + geom_point() + theme_gray()
{% endhighlight %}

<div style = "text-align:center"><img src="/images/blog/boxwithpoint.png"></div>
