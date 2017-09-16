---
layout: post
title: "Import clipboard into R under Mac OS X"
excerpt: "การ copy [ctr+c] จาก excel มาลง ใน R "
tags: [Rtips]
comments: true
---

{% highlight r %}

data <- read.table(pipe("pbpaste"), sep="\t", header=T)
{% endhighlight %}


หวังว่าจะเป็น ทิปที่มีประโยชน์ ไม่ม่ากก็น้อยนะครับ
Hope you enjoyed this useful tip.
<div style = "text-align:center"><img src ="/images/blog/sithsig.png" width = "100"></div>
{% highlight r %}
{% endhighlight %}
