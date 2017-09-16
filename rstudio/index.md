---
title: RStudio
layout: page
commets: true
---

<div style = "text-align:center"><img src ="https://www.rstudio.com/wp-content/uploads/2015/01/rstudiosticker.png"></div>

## การทำงานของ RStudio

หลายๆคนคงสงสัยว่า ทำไมโหลด R แล้ว ทำไมต้องโหลด RStudio อีกด้วย นั้นเป็นเพราะว่า นักพัฒนาเห็นถึงความลำบากของการทำงานบนโปรแกรม R ดังนั้นจึงออกแบบ RStudio IDE " integrated development environment" นั้นคือ การทำงานร่วมกับ R โดยในส่วนของการทำงาน การคำนวน หน้าที่ อยู่ที่ R แต่ การสื่อสาร การแสดงออก จะปรากฎ ผ่าน RStudio

## Download RStudio

สุดแสนจะง่าย ทำตามขั้นตอนเลยครับ

1. เข้าไปที่เวปไซด์ [http://www.rstudio.com/ide/download/](http://www.rstudio.com/ide/download/)
2. คลิก ที่ พิมพ์ว่า Download RStudio Desktop
3. เลือกโหลดตามระบบของเครื่อง
4. Run ไฟล์

## การปรับแต่ง Customization

โดยปกติ โปรแกรมจะตรวจสอบและเลือก R รุ่นที่ใหม่ที่สุดและเหมาะสมกับเจ้าของเครื่องโดยอัติโนมัติ
งั้น เข้าไปดูกัน เลือก Tools ⇒ Options to open the Options pane

<div style = "text-align:center"><img src ="https://support.rstudio.com/hc/en-us/article_attachments/202195257/Screen_Shot_2015-06-25_at_4.54.27_PM.png" width="580"/></div>


## หน้าต่างของโปรแกรม RStudio

<div style = "text-align:center"><img src= "http://wiki.awf.forst.uni-goettingen.de/wiki/images/f/f6/02-RStudio.jpg" width="580"/></div>


สามารถแบ่งหน้าที่ ออกเป็น 4 ส่วน

1. R source

2. R console

3. R environment and history

4. file, plot, package, help and view หรือ Graphic output

## หน้าต่าง R source ##

หน้าต่างนี้ถึงได้ว่าเป็นหน้าที่หลักที่เราจะสื่อสารกับโปรแกรม คำสั่งต่างๆ จะถูกสั่งจากตรงนี้
เช่น

{% highlight r %}

> 1 + 1 # สั่งให้ คำนวน 1 บวก หนึ่ง
> a <- c(1, 2, 3, 4, 5) # กำหนดให้ a ประกอบด้วย vector 1, 2, 3, 4 และ 5
> b <- c(5, 10, 15, 20, 25) # กำหนดให้ b ประกอบด้วย vector 5, 10, 15, 20 และ 25
> a + b # สั่งให้ คำนวน a บวก b
> plot(a,b)

{% endhighlight %}

## หน้าต่าง R console ##
เมื่อเราเขียนคำสั่งในหน้า source แล้ว highlight คำสั่งทั้งหมด แล้ว กด ctr+enter

{% highlight r %}

> 1 + 1 # สั่งให้ คำนวน 1 บวก หนึ่ง
[1] 2
> a <- c(1, 2, 3, 4, 5) # กำหนดให้ a ประกอบด้วย vector 1, 2, 3, 4 และ 5
> b <- c(5, 10, 15, 20, 25) # กำหนดให้ b ประกอบด้วย vector 5, 10, 15, 20 และ 25
> a + b # สั่งให้ คำนวน a บวก b
[1] 6 12 18 24 30
plot(a,b)

{% endhighlight %}


จะปรากฎที่หน้าต่าง console นั้นหมายความว่า คำสั่ง ถูกสั่ง แล้ว โปรแกรมตอบสนอง ดังที่แสดง ข้างล่าง

[1] หมายถึง โปรแกรมแสดงผลจากคำสั่ง ว่า บรรทัดที่หนึ่ง [1] ผลลัพพท์คือ 2 จาก 1+1 และ บรรทัดที่หนึ่ง[1] ผลลัพพท์คือ 6 (1+5) 12 (2+10) 18(3+15) 24(4+5) 30(5+25)

## หน้าต่าง R Environment, History ##

ถ้าลองสังเกตดู จะปรากฎ a และ b ที่หน้าต่างนี้ และบอกคุณสมบัติของ a และ b เช่น

Value

a num[1:5] 1 2 3 4 5

b num[1:5] 5 10 15 20 25

นั้นหมายความว่า หน้าต่างนี้ แสดงผลของค่าที่กำหมด และเก็บไว้โดยโปรแกรม และเพื่อให้เราได้ ดูอีกว่า ตอนนี้ิ โปรแกรม รู้จักค่าอะไรบ้าง แต่ถ้าเป็นการทำงานบนโปรแกรม R เราจะต้องเรียกมาดู ถ้าเราจำไม่ได้ว่าเคยกำหนดค่าอะไรไปแล้วบ้าง

### หน้าต่าง File, Plot, Package, Help and View 

เมื่อลองคำสั่ง ที่กล่าวมาแล้ว จะพบว่า มีกราฟปรากฎ ขึ้นที่หน้าต่างนี้ ที่ Tab Plot นั้นหมายความว่า หน้าต่างนี้ ทำหน้าที่แสดงผลเชิงกราฟฟิก เช่น กราฟ ต่างๆ

![](http://rthaisblog.files.wordpress.com/2014/02/rplot-ba.jpeg)


Tap File ยังแสดง file directory เราจะทำงาน ทำงานอยู่ ได้ด้วย

Tap Package แสดง Package ที่มีอยู่ แล้วยังสามารถ คลิ้กเพื่อ load package เพื่อให้งาน หรือ install package และ update package ได้ด้วยการ คลิ้ก

### ปรับแต่งหน้าต่าง

หน้าต่าง ต่างๆ เหล่านี้ คุณสามารถปรับเปลี่ยนตามความพึงพอใจได้นะครับ โดยเข้าไปที่ Tools > Global Options แล้วเลือก Pane layout อันที่จริงแล้ว ผมมองว่า แต่แต่สไตล์เลยนะครับ ว่าจะชอบ Pane แบบไหน  แล้วอีกอย่างที่ผมอยากจะแนะนำคือ

<div style = "text-align:center"><img src= "/images/blog/panelset.png" width="580"/></div>


คุณอาจจะไม่ชอบพื้นหลังสีขาว ก็อาจจะลองเข้าไปปรับแต่เพื่อความไม่จำเจและอีกอยาก เวลาเขียน code เอง ก็จะไม่สำสน เพราะว่า โปรแกรม highlight code ที่ มีหน้าที่หรือ ประเภทต่างๆไว้คนละสี ทำให้อ่านง่าย และแยกแยะได้ง่ายขึ้น ซึ่งผมจะแนะนำให้ ลองปรับเล่นด้วย

<div style = "text-align:center"><img src= "/images/blog/appearance.png" width="580"/></div>

<hr/>

<iframe width="540" height="304" src="https://www.youtube.com/embed/mFXRIav9vkQ" frameborder="0" allowfullscreen></iframe>

<hr/>

RStudio and Organization

<iframe width="540" height="304" src="https://www.youtube.com/embed/812ruYN4PZQ" frameborder="0" allowfullscreen></iframe>


#### อ่านเพิ่มเติมได้ตาม links นะครับ

- [working with console](https://support.rstudio.com/hc/en-us/articles/200404846-Working-in-the-Console)

- [Editing and Executing Code](https://support.rstudio.com/hc/en-us/articles/200484448-Editing-and-Executing-Code)


