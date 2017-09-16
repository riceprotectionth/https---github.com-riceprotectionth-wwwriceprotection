---
layout: post
title: ชื่อสีใน RColorBrewer
excerpt: "หาชื่อของสีของ Brewer"
tags: [Rtips]
modified: 2015-10-9
comments: true
---

เป็นคนนึงที่จะจู้จี้เรื่องสีมาก เวลา จะสร้างกราฟอะไรขึ้นมา ก็มักจะสรรหาสีที่ชอบ แล้วผมก็ชอบสี ของ package RColorBrewer มาก ด้วย ซึ่งเป็นสีที่น่ารักน่าดู ไม่ใช่แค่ผมคนเดียวที่แคร์ เรื่องการเลือกใช้สี ไม่ใช่เหตุเพียเพราะสีสวยอย่างที่เราชอบอย่างเดียว สที่เลือกใช้ ควรคำนึงถืงเรื่อง สีที่เป็นมิตรต่อคนตาบอดสี อันนี้ advisor ผม เนี้ย แค่ร์มาก

แต่เนื่องจากชุดสีที่package นี้ จัดให้ มาเป็นเซท  แต่เราอยากแค่ได้ชื่อสี ไหนเซทนั้นๆ เพียงบางสี เราจะรู้ได้อย่างไรว่า มันชื่ออะไร สุดท้ายผมก็ค้นพบแล้ว ว่า จะรู้ได้อย่างไร ผมเองก็นำมาจาก Stackoverflow[^Stackoverflow]

{% highlight r %}
> library(RColorBrewer)
> display.brewer.pal(10,"Set3")
> brewer.set3 <- brewer.pal(10, "Set3")

{% endhighlight %}

เมื่อเราเห็น สีเหล่านี้แล้ว แต่เราอยากได้แค่บางสีเพื่อเอาไปใช้่

![](http://i.stack.imgur.com/ruR9s.png)

{% highlight r %}
> col.dist  colors()[ apply(col2rgb(brewer.set3), 2, function(z) which.min( sapply(colors(), function(x) col.dist(inp=z, comp=x) ) ) ) ]
> [1] "paleturquoise3"  "moccasin"        "lightsteelblue"  "salmon"
> [5] "lightskyblue3"   "sandybrown"      "darkolivegreen2" "thistle2"
> [9] "gray85"          "orchid3"

{% endhighlight %}

ครับจะเห็นได้เลยว่า สีที่เราอยากได้นั้น มีชื่อว่า อะไร แล้วเราก็สามารถเอาไปใช้ได้เลย
เช่น ผมอยากจะสร้าง


{% highlight r %}
ggplot(mtcars, aes(factor(cyl))) + geom_bar()
{% endhighlight %}

![](/images/blog/2015-10-11-rtips-Rbrewer-post/barwithdefalt.png)

{% highlight r %}
ggplot(mtcars, aes(factor(cyl))) + geom_bar(fill = "sandybrown")
{% endhighlight %}

![](/images/blog/2015-10-11-rtips-Rbrewer-post/barwithsandy.png)

credit: [Stakoverflow]: http://stackoverflow.com/questions/18408333/find-color-names-for-colors-close-to-colorbrewer-palette)
