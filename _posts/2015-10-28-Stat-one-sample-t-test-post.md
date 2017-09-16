---
layout: post
title: One sample t test with R
excerpt: "ทดสอบค่าเฉลี่ยประชากรหนึ่งกลุ่ม"
tags: [R, Statistics]
modified: 2015-10-16
comments: true
---


อาร์มีจุดเด่น อย่างที่เคยกล่าวไปแล้วนะครับ ว่า มี function สำหรับการวิเคราะห์ทางสถิติ ซึ่งบทนี้ผมจะอธิบายใช้อาร์วิเคราะห์ one sample t test กับกลุ่มตัวอย่างเป็นกลุ่มเดียวก่อนนะครับ เพื่อ ทดสอบดูว่าค่าเฉลี่ยของประชากรกลุ่มนี้ มีความแตกต่างกับค่าที่เราตั้งสมมุติฐานไว้หรือไม่ เช่น ผมจะขอยกตัวอย่าง ข้อมูล DDT ครับ คือเรามีโจทย์อยู่ในใจว่า เราอยากจะรู้ว่า ข้อมูลที่เก็บมาได้มาความห่างไกลหรือใกล้เคียงกับค่าเฉลี่ยที่เราคาดไว้หรือไม่ ก่อนที่จะทำการทดสอบ one sample t test นั้น จะต้องจำไว้ว่า อ้างอิงถึงประชากร  mean population ซึ่ง วิธีการถูกกำหนดไว้ว่า ตัวอย่างที่ สุ่มนั้นควรมีการแจกแจงแบบปกติ normal distribution นะคับ เพราะว่า ถ้าไม่ เราจะไปใช้ วิธีอื่น จำพวก non-parametric tests

{% highlight r %}
> library(MASS)
> DDT # query DDT data from MASS package
> ?DDT # what is DDT?  
{% endhighlight %}

ผมขอใช้ ข้อมูล DDT เพื่อเอามาเป็นตัวอย่างอธิบาย นะครับ
คือ DDT dataset อันนี้คือ ข้อมูลของสาร DDT ที่ตรวจพบได้จากคะน้า ที่ได้สุ่มตรวจจำนวน 15 ตัวอย่าง มีหน่วยเป็น ppm (หนึ่งในล้านส่วน)

{% highlight r %}
> str(DDT)
 num [1:15] 2.79 2.93 3.22 3.78 3.22 3.38 3.18 3.33 3.34 3.06 ... 
{% endhighlight %}

สมมุตินะครับว่า มาตราฐาน คือคะน้าในท้องตลาดจะต้องตรวจพบสาร DDT ตกค้างได้ไม่ถึง 3 ppm
ผมเลยอยากรู้ว่า

- คะน้าที่สุ่มมาจากแหล่งนี้ เกินค่าที่กำหนดหรือไม่
- แล้วมีกี่ตัวอย่างที่เกินจากค่านี้
- แล้วค่าเฉลี่ยของDDT จากตัวอย่างชุดนี้คือเท่าไหร่

เรามาดูกันก่อนว่า มีการกระจายตัวอย่างไร
{% highlight r %}
> hist(DDT)
> qqnorm(DDT)
> qqline(DDT)
{% endhighlight %}

เมื่อเราเห็นกราฟ QQ plot แล้ว เราจะเห็นว่ามีอยู่หนึ่งค่าที่โดดจากกลุ่มและทำให้การกระจายของข้อมูบนั้นไม่เป็นการแจกแจงแบบปกติ

{% highlight r %}
>  plot(DDT)
{% endhighlight %}

<div style = "text-align:center"><img src ="/images/blog/2015-11-02-1.png"></div>

เราจะรู้เลยว่า ข้อมูลลำดับที่ 14 นั้น โดดมา เราก็จัดการ remove มันซะเลย

{% highlight r %}
>  new.DDT <- DDT[-14]
{% endhighlight %}

### Parametric method

เมื่อข้อมูลของเราแจกแจงแบบปกติแล้วเราสามารถใช้ ```t.test()``` มาใช้เพื่อวิเคราะห์


แต่มาดูกันก่อนว่า  หน้าตาของ function นี้ มันต้องการอะไรบ้าง

{% highlight r %}
t.test(x, y = NULL,
       alternative = c("two.sided", "less", "greater"),
       mu = 0, paired = FALSE, var.equal = FALSE,
       conf.level = 0.95, ...)
{% endhighlight %}

จะเห็นว่า
function ถามหา ค่า x แต่ ค่า y จะใส่ หรือไม่ใส่ก็ได้

{% highlight r %}
> t.test(new.DDT, mu = 3,)

	One Sample t-test

data:  new.DDT
t = 3.4669, df = 13, p-value = 0.00417
alternative hypothesis: true mean is not equal to 3
95 percent confidence interval:
 3.088293 3.380278
sample estimates:
mean of x
 3.234286
{% endhighlight %}

### Nonparametric method

ผมจะขอยกตัวอย่าง วิธีการนี้โดยใช้  ```wilcox.test```

{% highlight r %}
wilcox.test(x, y = NULL,
            alternative = c("two.sided", "less", "greater"),
            mu = 0, paired = FALSE, exact = NULL, correct = TRUE,
            conf.int = FALSE, conf.level = 0.95, ...)
{% endhighlight %}

จากข้อมูล DDT ไม่มีการตัดค่าที่เกินไปจากกลุ่ม

{% highlight r %}
> wilcox.test(DDT, mu = 3, conf.int = TRUE, exact = FALSE)

	Wilcoxon signed rank test with continuity correction

data:  DDT
V = 111.5, p-value = 0.003751
alternative hypothesis: true location is not equal to 3
95 percent confidence interval:
 3.119970 3.470056
sample estimates:
(pseudo)median
       3.26001
{% endhighlight %}


<div style = "text-align:center"><img src ="/images/blog/sithsig.png" width = "100"></div>
{% highlight r %}
{% endhighlight %}
