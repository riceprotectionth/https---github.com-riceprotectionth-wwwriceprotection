---
layout: post
title: "Wrong data frame format"
excerpt: "ทั้งๆ ที่เราก็ โหลดเข้ามาเข้ามาแล้ว class ก็ถูกต้องแล้ว แต่ทำไม analysis ไม่ได้เวลา ที่คุณ import ไฟล์เข้ามายังโปรแกรม R ได้แล้ว class ก็ถูกต้องเป็น data frame แล้ว แต่ทำไม วิเคราะห์ไม่ได้ นั้นอาจจะเป็นเพราะว่า data frame ของเรานั้นโครงสร้างไม่ถูกต้องเราต้องต้องดูดีๆ ว่า data frame ของเรา มีรูปแบบที่ถูกต้องหรือไม่"
tags: [Rtips]
comments: true
---

เวลา ที่คุณ import ไฟล์เข้ามายังโปรแกรม R ได้แล้ว class ก็ถูกต้องเป็น data frame แล้ว แต่ทำไม วิเคราะห์ไม่ได้ นั้นอาจจะเป็นเพราะว่า data frame ของเรานั้นโครงส้รางไม่ถูกต้อง
เราต้องต้องดูดีๆ ว่า data frame ของเรา มีรูปแบบที่ถูกต้องหรือไม่ เช่น

{% highlight r %}
str(data)
Classes  'data.frame':	6  obs. of  7 variables:
head(data)
        NA        col1     col2    col3   col4       col5      col6
1   samp A        S        R        S        S        S        S
2   samp B        R        R        S        S        S        S
3   samp C        S        R        S        M        S        S
4   samp D        R        R        R        R        R        R
5   samp E        S        R        S        R        S        S
6   samp F        S        R        S        S        S        S
{% endhighlight %}

ทั้งที่จริง แล้ว ผมมี แค่ 6 variables เท่านั้น นั้น แสดงว่า data frame ที่เรามีนั้น มีโครงสร้าง ไม่ถูกต้อง และเมื่อเวลา เราทำไปวิเคราะห์ มันก็จะ ไม่ได้ ผล

จากตรงนี้ column 1 ควรจะเริ่มที่ col1 อันนี้ ไม่ใช่ data frame ที่ถูกต้อง ดังนั้น จะต้อง ล้าง column ที่ 1 แล้ว แทน column1 ด้วย rowname

{% highlight r %}
data
data1 <- data[,-1] # remove the coulmn1
rownames(data1) <- data[,1] # insert name of rows with column1
data1
              col1     col2     col3     col4     col5     col6
samp A        S        R        S        S        S        S
samp B        R        R        S        S        S        S
samp C        S        R        S        M        S        S
samp D        R        R        R        R        R        R
samp E        S        R        S        R        S        S
samp F        S        R        S        S        S        S
{% endhighlight %}

เห็นไหมหละครับว่า data frame เหมือนกัน แต่โครงสร้าง ต่างกัน ต้องระมัดระวัง

<div style = "text-align:center"><img src ="/images/blog/sithsig.png" width = "100"></div>
{% highlight r %}
{% endhighlight %}
