---
layout: post
title: Let’s the words present yourself
excerpt: "มาลองเล่น wordcloud กับงานเขียนของตัวเองเพื่อดูว่า งานเขียนของตัวเองนั้นเกี่ยวข้องกับอะไรมากที่สุด"
tags: [R for Fun]
modified: 2015-10-31
comments: true
---

Recently, after a small achievement on the proposal, I would like to know what my research is all about, and I would like to present what my proposal is, and who I am. I decided to analyses my proposal.

For practicing my R skill, I also used R to analyses my proposal. R program are very supportive to word cloud from the text in my proposal.

มีช่วงเวลาหนึ่งที่ว่างๆ และกำลังหัดเขียนโปรแกรมอาร์ และก็เขียน Proposal เสร็จ เลยอยากจะลองดูซิว่า ที่ตัวเองเขียนและกลังทำอยู่นั้น มันเกี่ยวกับอะไร มากที่สุด โดยการวิเเคราะห์ด้วย ```wordcloud``` package ซึ่งผมก็ทำตามนี้[^1]
 ยังไงก็ลองเข้าไปอ่านและทำตามดูก็ได้นะครับ


เริ่มต้นตามนี้เลยนะครับ โดยการแปลง ไฟล์ word ที่เราเขียนนั้น ให้เป็น ไฟล์ text  ก่อนนะครับ  หลังจากนั้นก็นำเข้า อาร์ แล้ว ทำตาม script ที่ผมให้เลยนะครับ

{% highlight r %}
> word <- readLines("Proposal.txt") # read file text
> word.cloud <- Corpus(DataframeSource(data.frame(word)))
> word.cloud <- tm_map(word.cloud, removePunctuation) # remove punctuation
> word.cloud <- tm_map(word.cloud, removeWords, stopwords("english"))
> tdm <- TermDocumentMatrix(word.cloud)
> m <- as.matrix(tdm)
> v <- sort(rowSums(m),decreasing=TRUE)
> d <- data.frame(word = names(v),freq=v)
> wordcloud(d$word, d$freq, scale = c(8,.5), min.freq = 2, max.words = Inf, random.order = FALSE, rot.per = .15,) # Show the wordcloud
{% endhighlight %}

<div style = "text-align:center"><img src = "/images/blog/wcloud1.jpeg"></div>

{% highlight r %}
> library(RColorBrewer)
> pal <- brewer.pal(8,"Dark2")
> pal <- pal[-(1:4)]
> wordcloud(d$word,d$freq, scale=c(8,.5),min.freq=2,max.words=Inf, random.order=FALSE, rot.per=.15,pal)
{% endhighlight %}


{% highlight r %}
> pal <- brewer.pal(6,"BuGn")
> pal <- pal[-(1)]
> wordcloud(d$word,d$freq,c(8,.3),2,,TRUE,,.15,pal)
> wordcloud(d$word,d$freq,c(8,.3),2,,TRUE,TRUE,.15,pal) #random colors
{% endhighlight %}

<div style = "text-align:center"><img src ="/images/blog/wordcloud.jpg"></div>

[^1]:<https://georeferenced.wordpress.com/2013/01/15/rwordcloud>
