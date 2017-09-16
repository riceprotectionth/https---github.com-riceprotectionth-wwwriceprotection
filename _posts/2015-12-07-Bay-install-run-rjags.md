---
layout: post
title: "Installation and Run JAGS on Mac"
excerpt: "ช่วงนี้ ผม มีความรู้สึกสนใจเกี่ยวกับ bayesian statistics อยู่ เลยอยากจะลง R packages ที่เกี่ยวข้องกับการคำนวน bayesian statistics อยู่ แล้วมี packages อันนึงที่ มีปัญหา เกิด ลงไม่ได้ นั้น คือ `rjags`"
tags: [Bayesian]
comments: true
---

ช่วงนี้ ผม มีความรู้สึกสนใจเกี่ยวกับ bayesian statistics อยู่ เลยอยากจะลง R packages ที่เกี่ยวข้องกับการคำนวน bayesian statistics อยู่ แล้วมี packages อันนึงที่ มีปัญหา เกิด ลงไม่ได้ นั้น คือ `rjags` ผมเลย ลองหาอ่านใน ผมจึงพบเวปนี้เข้า [Quantitative Ecology](http://quantitativeecology.blogspot.com/2012/03/installing-and-running-jags-on-mac-os.html?showComment=1448873695680#c2452926838659261108) แล้วก็ได้ลอง ทำตาม ดู ปรากฎว่า ใช้ได้ผลเป็นอย่างดี

ลองทำตามกันดูนะครับ

อันนี้ ของผมนะครับ
My specification

- Mac OS 10.10.5
- R 3.3.2
- JAGS 4.0.1
- rjags 4-4

จะอย่างไรก็ตามถ้ามี version ที่ใหม่กว่านี้ก็แนะนำให้​ โหลด ไปจะดีกว่านะครับ

เริ่มกันเลยครับ

1. เข้าไปดาวน์โหลด JAGS 4.0.1 [Download](http://sourceforge.net/projects/mcmc-jags/files/JAGS/4.x/Mac%20OS%20X/JAGS-4.0.1.dmg/download) และ download JAGS 4.0.1.dmg แล้วก็ดำเนิน


2. หลังจากนั้นดาวน์โหลด [Here](http://sourceforge.net/projects/mcmc-jags/files/rjags/4/rjags_4-4.tar.gz/download) `rjags_4-4.tar.gz` ไว้บนหน้า desktop


3. โหลดเสร็จก็มาถึงขั้นการ install `rjags` package. เพื่อนๆ อาจจะลอง install ในโปรแกรม R โดย

{% highlight r %}
install.packages('/Users/sithjaisong/Desktop/rjags_2.2.0-1.tar.gz', repos = NULL, type = "source")
{% endhighlight %}
install.packages('/Users/sithjaisong/Desktop/rjags_2.2.0-1.tar.gz', repos = NULL, type = "source")

แต่เมื่อผมลองเรียก `library(rjags)` ผมได้ error message:
{% highlight r %}
library(rjags)
Error: package 'rjags' is not installed for 'arch=x86_64'
{% endhighlight %}

ถ้าเจอเหมือนกันอย่างผมก็มาที่ข้อสี่

4. ช่วยไม่ได้ครับ ที่จะต้องลงผ่าน Terminal

- เปิด Terminal /Applications/Utilities/Terminal.app) ขึ้นมา
- สมมุติว่า เราวางไฟล์ ที่ Desktop พิมพ์ `cd /Users/sithjaisong/Desktop/` เพราะว่าเครื่องของผมชื่อ `sithjaisong`
- พิมพ์ `R --arch x86_64 CMD INSTALL rjags_2.2.0-1.tar.gz`

5. หลังจากนั้นลง ปิด และ เปิด โปรแกรม R ใหม่อีกครั้ง แล้วลองเรียก

{% highlight r %}
> library(rjags)
Loading required package: coda
Linked to JAGS 4.0.1
Loaded modules: basemod,bugs
{% endhighlight %}

ถ้าขึ้นอย่างนี้ก็แสดงว่า คุณทำสำเร็จแล้ว
<div style = "text-align:center"><img src ="/images/blog/sithsig.png" width = "100"></div>
