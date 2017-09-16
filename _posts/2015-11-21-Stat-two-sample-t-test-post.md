---
layout: post
title: Two sample test (paired data)
excerpt: "ทดสอบ ตัวอย่างจากสองกลุ่มว่าแตกต่างกันหรือไม่"
tags: [R, Statistics]
modified: 2015-11-16
comments: true
---

หลังจาหที่ เขียนไปเกี่ยวกับการทดสอบค่าเฉลี่ยของกลุ่มตัวอย่างเดียวไปแล้ว ทีนี้ งานวิจัยของเรา เพื่อตอบจุกประสงค์การวิจัย เรามักจะอยากทราบว่าตัวอย่างที่ทดสอบจากทั้งสองกลุ่มนั้น มีความแตกต่างกันหรือ ไม่

ก่อนอื่น ก่อนที่เราจะเข้า หรือว่า ด้วย การทดสอบทางสถิติ เราจะต้องถามตัวเองก่อนว่า ลักษณะงานวิจัยของเรานั้น กลุ่มตัวอย่างที่เราทดสอบนั้น มีลักษษระอย่าางไร

- paired test
ผม เรียวกการทดสอบ ในลักษณะนี้ว่า before and after test  โดยที่กลุ่มตัวอย่าง ที่ทดสอบ ซึ่งคือ  experimental unit เป็น ชุดเดียวกัน ถูกทดสอบ แล้วเก็ยผล แล้ว หลังจากนั้น ทดสอบอีก แล้ว เก็บค่า ส่วนใหญ่ จะเป็น การทดลองประเภทที่อยากจะทราบว่า ก่อนและหลังทดสอบนั้น เป็นอย่างไร

มี วิธีทดสอบหลักๆ อยู่ สามอย่างที่ มักพูดถึงกัน คือ

- Paired t - test
ข้อมูลที่จะนำมาวิเคราะห์ด้วยวิธีนี้ จะต้องเป็น continuous data
{% highlight r %}
> before <- c(34.6, 38.2, 37.6)
> after <- c(41.3, 39.6, 41.0)
> t.test(before, after, paired = TRUE)

	Paired t-test

data:  before and after
t = -2.4807, df = 2, p-value = 0.1313
alternative hypothesis: true difference in means is not equal to 0
95 percent confidence interval:
 -10.481980   2.815313
sample estimates:
mean of the differences
              -3.833333
{% endhighlight %}

- Wilcoxon signed rank test

จัดเป็น non-pparametric test หลักการทดสอบก็ คล้ายๆ กับ paired t test แต่ข้อมูลที่จะทอสอบนั้นไม่จำเป็นต้องเป็น continuous data การทสอบนี้  ค่อนข้าง powerful กว่า paired t test ข้อมูลที่จะทดสอบ จะต้องมี จำนวนไม่น้อยกว่า 6 (n > 6)
{% highlight r %}
>wilcox.test( , , paired = TRUE
{% endhighlight %}

- sign test.

แนะนำให้ใช้ก็ต่อเมื่อ จำนวน observation มีขนากใหญ่
{% highlight r %}
> binom.test(sum(Day1>Day2), length(Day1))
{% endhighlight %}


<div style = "text-align:center"><img src ="/images/blog/sithsig.png" width = "100"></div>
{% highlight r %}
{% endhighlight %}
