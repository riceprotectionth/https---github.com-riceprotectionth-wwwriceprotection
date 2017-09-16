---
layout: post
title: Rtips (31-10-2015) specific column selection
excerpt: "บอกให้ชัดเจนเลยว่าจะเลือก column ไหน"
tags: [R, Rtips]
modified: 2015-10-16
comments: true
---

เคยเป็นไหม ที่คุณเขียน script แล้วกลับมาอ่านที่คุณเขียนไป เมื่ออาทิตย์ที่แล้ว แล้วลืมหรือไม่เข้าใจว่าที่เขียนไป เราต้องการอะไร การเขียน script ให้อ่านแล้วเข้าใจเลยว่าต้องการ หรือกำลังทำอะไรจะ ดีแล้วสะดวกกับคนที่อ่านทั้งตัวคุณเองและคนอื่น

ในการวิเคราะห์ข้อมูลนั้น บางครั้งเราเพียงแค่สนใจ บางตัวแปรเท่านั้น ฉะนั้นเราจึกอยากจะเลือก เพียงสองหรือสามจากสิบตัวแปรที่เราเก็บการเลือกนั้นทำได้หลายวิธี


{% highlight r %}
> library(plyr) #  ผมจะใช้ขอ้มูลจาก package นี้
> library(dplyr)
> data("baseball")
> baseball <- as.tbl(baseball)
{% endhighlight %}

เอาหละเรามาดูข้อมูลกัน

{% highlight r %}
> baseball
Source: local data frame [21,699 x 22]

          id  year stint  team    lg     g    ab     r     h   X2b   X3b    hr   rbi    sb    cs
       (chr) (int) (int) (chr) (chr) (int) (int) (int) (int) (int) (int) (int) (int) (int) (int)
1  ansonca01  1871     1   RC1          25   120    29    39    11     3     0    16     6     2
2  forceda01  1871     1   WS3          32   162    45    45     9     4     0    29     8     0
3  mathebo01  1871     1   FW1          19    89    15    24     3     1     0    10     2     1
4  startjo01  1871     1   NY2          33   161    35    58     5     1     1    34     4     2
5  suttoez01  1871     1   CL1          29   128    35    45     3     7     3    23     3     1
6  whitede01  1871     1   CL1          29   146    40    47     6     5     1    21     2     2
7   yorkto01  1871     1   TRO          29   145    36    37     5     7     2    23     2     2
8  ansonca01  1872     1   PH1          46   217    60    90    10     7     0    50     6     6
9  burdoja01  1872     1   BR2          37   174    26    46     3     0     0    15     0     1
10 forceda01  1872     1   TRO          25   130    40    53    11     0     0    16     2     2
..       ...   ...   ...   ...   ...   ...   ...   ...   ...   ...   ...   ...   ...   ...   ...
Variables not shown: bb (int), so (int), ibb (int), hbp (int), sh (int), sf (int), gidp (int)
{% endhighlight %}


การเลือก column วิธีแรกคือ
{% highlight r %}
> baseball[, 1]  # select column 1
{% endhighlight %}

ขอออกนอกเรื่องนิดนึง ใน [ , ] อาจจะงงว่า อันไหน เป็น row อันไหน เป็น column  ผมให้เทคนิคไว้ว่า มันเหมือนกับ แกน  x  แกน y นั้นแหละครับ (x,y) x เป็นแนวนอน นั้นคือ row ส่วน  y แนวตั้ง ก็จะเป็น column

ถ้าอยากเลือกมากกว่าหนึ่งหละ

การเลือก column วิธีแรกคือ
{% highlight r %}
> baseball[, c(1,2)]  # select column 1 and 2
> baseball[, c(1:5)] # select column 1,2,3,4,5
{% endhighlight %}

แล้วทีนี้เกิดคุณเขียนไว้นานแล้ว แล้วกลับมาอ่าน คุณก็จะรู้แต่ว่าคุณได้เลือก column ที่เท่าไหร่ แต่คุณจะไม่รู้ว่าคุณเลือก ตัวแปรอะไร ใช่ไหมหละครับ

ส่วนตัวถ้าผมจะเขียนผมจะไม่ค่อยชอบเขียนแบบลำดับที่ ผมจะเขียนชื่อ column ไปแลย มันจะทำให้ คนอื่นอ่านก็จะรู้เลยว่าเรากำลังทำกับตัวแปรอะไร

{% highlight r %}
> baseball[, "id"] # select column named "id"
> baseball["id"] # I dont like it because it is confusing. I dont know whather I select row or column
> baseball[, c("id", "year")] # select column named "id" and "year"
{% endhighlight %}

การเขียน script ให้อ่านแล้วเข้าใจง่าย ก็ถือเป็นเรื่องสำคัญเรื่องหนึ่ง เลยนะครับ

ผมเลยขอเสนอ ```dply``` package

{% highlight r %}
> select(baseball, id, year)
> baseball %>% select(id)
> select(baseball, id)
> baseball %>% select(id, year)
{% endhighlight %}

code นั้น สั้นอย่างเดียวไม่ได้ต้องอ่านง่าย เข้าใจง่ายด้วยนะครับ
