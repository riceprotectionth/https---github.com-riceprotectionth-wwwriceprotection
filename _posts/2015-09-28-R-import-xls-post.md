---
layout: post
title: import ไฟล์ xlsx ใน โปรแกรม R
excerpt: ""
tags: R
modified: 2015-10-16
comments: true
---

เมื่อครั้งก่อน ผมได้ เสนอ package XLConnect ซึ่งให้อ่านและเขียนไฟล์ .xls และ .xlsx แต่ตอนนี้ ผมคิดว่า package "readxl" ดูท่าจะดีกว่า และ มันก็เข้าไปอยู่ในใจ เรียบร้อยแล้ว ด้วย คำสั่งที่เขียนที่สั้นจนจดจำได้ง่าย

ผมลองเปรีนยเทียบความเร็วในการทำงาน ```read_excel()``` อ่านได้เร็วกว่ามาก สามารถอ่านไฟล์ได้เร็วกว่า

```readWorksheetFromFile``` ของ XLConnect package และ ```read.xls```  ของ gdata package

อันนี้ผมเอามาลองเทียบให้ดูนะครับ

{% highlight r %}
system.time(read_excel(f)) # readxl package
#user system elapsed
#0.020 0.001 0.021
{% endhighlight %}


{% highlight r %}
system.time(readWorksheetFromFile(f, sheet =1)) # XLConnect package
#user system elapsed
#0.319 0.005 0.157
{% endhighlight %}


{% highlight r %}
system.time(read.xls(f)) # gdata package
#user system elapsed
#1.576 0.044 1.632
{% endhighlight %}

เห็นไหมหละครับ ว่า น่าใช้แค่ไหน อ่านก็เร็วแถมประหยัดทรัพยากร ด้วย
