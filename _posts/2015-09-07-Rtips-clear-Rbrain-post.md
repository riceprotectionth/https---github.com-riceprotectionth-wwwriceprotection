---
layout: post
title: Clear R's brain
excerpt: "ล้างไฟล์ต่างๆ ก่อนเริ่มต้นทำงาน"
tags: [Rtips]
modified: 2015-10-9
comments: true
---

ทิปอันนี้ ที่จริงแล้ว ผมไม่เคยใส่ใจและไม่คิดว่าสำคัญ แต่ ครั้งนึง ผมกำลังวิเคราะห์ข้อมูลอยู่ ด้วยความที่เป็นคน คิดโน้น คิดนี้ ไม่ค่อยเป็นขั้นเป็นตอน สลับวิเคราะห์กับข้อมูลอีกชุดนึก ปรากฎว่า function ที่ใช้อยู่ กลับ run ไม่ผ่าน โดยฟ้อง ซึ่งผมเองก็แก้ ไปเรียบร้อยแล้ว แต่ทำอย่างไร ก็ run ไม่ผ่านสักที จนต้องเปิดปิด โปรแกรมแล้ว เริ่ม run ใหม่ทั้งหมด จนผมนึกขึ้นได้ว่า เคยมีคนแนะนำว่า ก่อนที่จะทำการ วิเคราะห์ ให้ล้าง ข้อมูลก่อน ดังนั้น ถ้าไม่อยากเจอเรื่องหงุดหงิดแบบผมก็ อย่าลืมล้าง ข้อมูล ก่อนนะครับ

{% highlight r %}
> rm(list = ls()) #Reset R's brain
{% endhighlight %}

ซึ่งผมเองได้ เทคนิคนี้ จาก [Getting Started with R: An introduction for biologists](http://www.r4all.org/)
