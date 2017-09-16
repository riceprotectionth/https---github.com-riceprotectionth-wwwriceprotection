---
layout: post
title:  Normal distribution
excerpt: "การตรวจสอบการแจกแจงปกติของข้อมูล"
tags: [R, Statistics]
modified: 2015-11-12
comments: true
---

ผมคงไม่กล่าวถึงความหมายของการแจกแจงครับ การทดสอบหรือตรวจสอบดูว่าข้อมูลที่เราจะวิเคราะห์นั้นมีการแจกแจงปกติหรือไม่นั้น มีความสำคัญอันดับแรกๆ ก่อนที่จะลงมือวิเคราะห์ หรือเลือกวิธีวิเคราะห์ ครับ เพราะว่า วิธีวิเคราะห์ทางสถิติหลายๆวิธี  มีข้อสมมุติฐาน ว่า ข้อมูลควรจะมีการแจกแจงปกติ วิธีการเหล่านั้น ก็เช่น ANOVA และ parametric test  ต่างๆ ซึ่ง ข้อมูลที่จะวิเคราะห์ได้ จะต้องมีการแจกแจงปกติ เพราะถ้าไม่แจกแจงปกติ ผลที่ได้จะไม่น่าเชื่อถือ นั้นเอง ดังนั้น เราควรจะต้องพิจารณา หรือบอกให้ได้ หรือหรือแม้แต่ชักจูงผู้อ่าน ว่าข้อมูลนั้นมีการแจกแจงปกติ ถึงได้ดำเนินการวิเคราะห์ วิธีดังกล่าว เพราะว่า มี สมมุติฐานเกี่ยวกับข้อมูลที่ว่า ข้อมูลจะต้องมีการแจกแจงปกติ

#### Dummy Data
{% highlight r %}
> library(MASS)
> Pima.tr
> data2 <- data.frame( name = c("K", "B", "C", "F", "I", "G", "A", "H", "E", "D", "J"),
height = c(120, 148, 153, 155, 158, 160, 163, 163, 167,170, 172)
)
{% endhighlight %}

> Pima.tr
> Diabetes in Pima Indian Women
> Description
> A population of women who were at least 21 years old, of Pima Indian heritage and living near Phoenix, Arizona, was tested for diabetes according to World Health Organization criteria. The data were collected by the US National Institute of Diabetes and Digestive and Kidney Diseases. We used the 532 complete records after dropping the (mainly missing) data on serum insulin.

> data2 ผมได้ ใช้ข้อมูลนี้ จากหนังสือ กราฟ ตาราง และสมการสำหรับการวิจัยทางสุขภาพ ผู้แต่ง : วีระศักดิ์ จงสู่วิวัฒน์วงศ์ (http://www.chulabook.com/description.asp?barcode=9789740318781)

ผม จะขอแนะนำวิธีการตรวจสอบการแจกแจง ด้วยกัน 2 วิธี


- การตรวจสอบดูด้วยกราฟ ที่เรียกว่า Quatile-inverse-normal หรือ QQ plots

{% highlight r %}
> qqnorm(data2$height, pch = as.character(data2$name))
> qqline(data2$height)
{% endhighlight %}

ถ้าจุดที่ plot นั้นห่างไกลจากเส้นนี้มาก การกระจายก็จะห่างไกลจากปกติ ซึ่งจากกราฟ เราจะเห็นว่ามีอยู่จุดหนึ่งที่ห่างไกลจากเส้นกราฟมาก

- Shapiro-Wilk test

{% highlight r %}

> shapiro.test(Pima.tr$bmi)
Shapiro-Wilk normality test

data:  Pima.tr$bmi
W = 0.99104, p-value = 0.2523

> shapiro.test(data2$height)

	Shapiro-Wilk normality test

data:  data2$height
W = 0.8247, p-value = 0.01989
{% endhighlight %}

ใน Pri.tr$bmi นี้ ค่า p-value มากกว่า 0.05 ดังนั้น เราไม่ reject null hypothesis ซึ่งบอกว่า ข้อมูลมีการแจกแจงแบบปกติ แต่ data2$height นั้น ค่า p-value น้อยกว่า 0.05 ดังนั้น เราจึง reject null hypothesis บ่งชี้ว่าตัวแปรนี้ไม่น่าจะแจกแจงแบบปกติ

<div style = "text-align:center"><img src ="/images/blog/2015-11-8.png"></div>

{% highlight r %}
> qqnorm(data2$height, pch = as.character(data2$name))
> qqline(data2$height)
> text(0, 130, paste("Saphiro-Wilk test: P-value =", round(shapiro.test(data2$height)$p.value, digits = 4),
                                                         sep = " "))
{% endhighlight %}
