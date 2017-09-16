---
title: Research
layout: page
comments: true
---

# Let's speak R

<div style = "text-align:center"><img src ="https://www.r-project.org/Rlogo.png"></div>

R programing environment  หรือ อาร์ คือ
หลายๆ คนที่เข้ามาอ่าน ผมคิดว่า คงรู้จักกันมาบ้างแล้วใช่ไหมครับ ว่า โปรแกรม R คือ โปรแกรมประเภทไหน แต่จะขอสรุปเกี่ยวกับโปรแกรมไว้สักหน่อย

โปรแกรม R เป็นภาษาทางคอมพิวเตอร์และโปรแกรมเพื่อการคำนวนทางสถิติและกราฟ สามารถดาวร์โหลดใช้งานได้ฟรี แต่สามารถติดตั้ง ทุกระบบปฎิบัติการ ไม่ว่าจะเป็น Windows, Mac OS, หรือ Linux

### ประวัติ

ภาษา R ถูกสรา้งขึ้นในปี 1993 โดยถูกพัฒนามาจากภาษา S   โดยเริ่มต้น ภาษา S ซึ่งพัฒนาขึ้นมาเพื่อใช้ในงานทางสถิติ จนกลายเป็น S+ แต่เนื่องจากโปรแกรมนี้มีราคาสูง  ภายหลัง นักสถิติสองคน ชื่อ Ross Ihaka  และ Robert Gentleman ได้ ช่วยกันเขียนซอฟ์ตแวร์ตามแบบ S+ แต่ดึงมาบางส่วนเพื่อ สำหรับการสอนวิชาสถิติและตั้งชื่อว่า R มีนัยยะว่ามาก่อน S โปรแกรม R มีการเผยแพร่แบบ General Public License  หรือเปิดให้ใช้ทั่วไป ในปี 1995 โปรแกรม R จึงเป็น open source ที่พัฒนามาจาก S+ นั้นเอง และเป็น โปรแกรมวิเคราะห์ทางสถิติที่เขียนโดยนักสถิติ โดยไม่มีข้อกังขา

### ความนิยม

R เป็นที่นิยมใช้กันในวงวิชาการเพื่อคำนวณด้านสถิติ เพราะมี built-in function ที่เกี่ยวข้องกับการคำนวณทางสถิติมาก และมีความสามารถแสดง ผลทางด้านกราฟฟิก แม้โปรแกรม R ดูเหมือนไม่มี interface ให้ใช้ง่ายๆ แบบ SPSS ต้องสั่งงานผ่าน command line แต่หากได้รู้จักและคุ้นเคยกับ R แล้ว จะเห็นว่า R มี ประสิทธิภาพและทำงานได้เร็วกว่า และทำได้มากกว่าการคำนวณสถิติ และที่สำคัญ เป็นโปรแกรมฟรี จึงเป็นที่นิยมใช้ของนักวิชาการจำนวนมาก

### การติดตั้งโปรแกรม

อันที่จริง การโหลด โปรแกรม R นั้น ไม่มีอะไรยากเลย

- เข้าเวปไซด์ [Download](https://cran.r-project.org/mirrors.html)
- เลือก CRAN mirror จะมีรายชื่อประเทศ ที่ ให้ดาวน์โหลด เลือก**ประเทศไทย**  [Prince of Songkla University, Hatyai](http://mirrors.psu.ac.th/pub/cran/)  เพื่อความรวดเร็วของการดาวน์โหลด ต้องขอบคุณ ม.สงขลานครินทร์ ที่ให้ยืม server เพื่อดาวน์โหลด
- หลังจากนั้นเลือก ดาวน์โหลด ตามระบบปฎิบัติการที่เรามี ใช้ใช้ mac ก็โหลดของ mac ใครใช้ window ก็ โหลดของ window กันไป
- โหลดมาแล้วก็ RUN โปรแกรม

โปรแกรม R จะเลือกระบบที่เหมาะสมกับ คอมพิวเตอร์ให้เราเอง แต่เพื่อความมั่นใจ สามารถเลือกได้ว่า จะ 32 หรือ 64 bit

### ข้อดี

- ข้อดีข้อที่ หนึ่ง คือ Open source software และมีข้อได้เปรียบหลายอย่างเมื่อเทียบกับโปรแกรมลิขสิทธิ์อย่างโปรแกรมที่ใช้วิเคราะห์ข้อมูลทางสถิติ อย่างที่เราคุ้นเคยกัน คือ SPSS, SAS, Genstat เป็นต้น โปรแกรม R ยังใช้งานได้ทุกระบบปฎิบัติการ GNU/Linux OSX หรือ Window

- ข้อดีข้อที่สอง คือ R จุดกำเนิดและพัฒนาขึ้นมาจากกลุ่มนักสถิติ จึงมี คำกล่าวว่า "created by statisticians for statisticians" มันจึงสะท้อนให้เห็นถึงการออกแบบ ภาษา ที่ มุ่งไปเพื่อการวิเคราะห์ข้อมูลเชิงสถิติ และ code ที่เขียนใน R นั้น ถ้าเทียบกับภาษาอื่นแล้ว มีขนาดหรือจำนวนที่น้อย เมื่อสั่ง function ให้ทำเหมือนกัน

- ข้อดีข้อที่สาม คือ โปรแกรม R นั้นสามารถใช้ได้ ทั้งที่อยู่ในรูปแบบ interactive หรือ non-interactive หรือ interface ซึ่ง มีหลาย software ถูกพัฒนาขึ้นมาเพื่อทำงานร่วมกับ โปรแกรม R เพื่อใช้งานได้ง่ายขึ้นหรือไม่ต้องเขียน code ก็สามารถใช้วิเคราะห์ทางสถิติได้

- ข้อดีข้อที่สี่ ข้อนี้อาจจะเป็นข้อที่ทำให้ โปรแกรม R นั้น ได้รับ ความนิยม นั้นคือ มี package สำหรับวิเคราะห์มากขึ้นและมากขึ้นเรื่อยๆ ซึ่ง เราเรียก package library หรือแหล่งรวบรวม package ต่างๆ ว่า Comprehensive R Archive Network หรือ CRAN

<hr/>
<div style = "text-align:center"><script async class="speakerdeck-embed" data-id="6db208007d6c0131ee49025a303c0b4c" data-ratio="1.33333333333333" src="//speakerdeck.com/assets/embed.js"></script></div>

<hr/>
#### การติดตั้ง R สำหรับระบบปฎิบัติการ Window

<div style = "text-align:center"><iframe width="560" height="315" src="https://www.youtube.com/embed/Ohnk9hcxf9M" frameborder="0" allowfullscreen></iframe></div>

<hr/>

#### การติดตั้ง R สำหรับระบบปฎิบัติการ Mac OS X
<div style = "text-align:center"><iframe width="560" height="315" src="https://www.youtube.com/embed/uxuuWXU-7UQ" frameborder="0" allowfullscreen></iframe></div>

<hr/>

ทำไมภาษาอาร์ถึงเหมาะกับการใช้เพื่อวิเคราะห์ข้อมูล

[playlist STAT202](https://www.youtube.com/playlist?list=PLA4B3B4CB6949A800)
R as the main implementation of S (and one that happens to be proper Open Source and a GNU project as well).

Not only as the S language designed precisely for this purpose (see the books by John Chambers), but the rather rich support of domain-specific packages at CRAN is second to none: over 2000 packages with proper quality control, often authored by experts in the field.

No question that R is the best language for statistics, as Dirk says. I just want to add a few points to this:

First, I think that the primary reason that you should use R is because of the community. It is used so heavily by experts in academia and industry at this stage, that no other language even comes close to rivalling the wealth on CRAN.

Second, it should be acknowledged that R the language is a joy to work with. It is my primary language, and having tried alternatives, I have no intention of abandoning it any time soon. But it also doesn't have a monopoly on it's strength for programming with data and this claim can be taken too far. All the Lisp and Functional languages are strong at data programming. Lisp, after all, was derived from "list programming", and it is Lisp's influence on R that make the language what it is.

There are members of the R community (eg. Ross Ihaka) who are actually viewing Lisp as the statistical languge of the future (see the "back to the future" paper for a reference) due to some deep design problems in the R language (eg. no multithreading).

So while R is undoubtedly the best language for statistical computing, I see some value in being familiar with another language like OCaml, Haskell, or (possibly) Clojure/Incanter.

ref http://stackoverflow.com/questions/2200460/what-programming-languages-are-good-for-statistics

## โปรแกรมอาร์ จากแหล่งต่างๆ ทั้งในและต่างประเทศ

ในตอนนี้ หลายสถาบัน ในประเทศไทย ที่สอน การใช้ R ก็มีเพิ่มขึ้นเรื่อยๆ ผมจะรวบรวมมา ไว้ เผื่อไว้จะลองไปซึ่งศึกษาเอง

### Facebook

ตาม Facebook ก็มีการตั้งกลุ่มผู้ใช้เช่นเดียวกัน

- [page:วิเคราะห์สถิติ ใช้ โปรแกรม R](https://www.facebook.com/%E0%B8%A7%E0%B8%B4%E0%B9%80%E0%B8%84%E0%B8%A3%E0%B8%B2%E0%B8%B0%E0%B8%AB%E0%B9%8C%E0%B8%AA%E0%B8%96%E0%B8%B4%E0%B8%95%E0%B8%B4-%E0%B9%83%E0%B8%8A%E0%B9%89-%E0%B9%82%E0%B8%9B%E0%B8%A3%E0%B9%81%E0%B8%81%E0%B8%A3%E0%B8%A1-R-556524057784946/)

- [R-blogger](https://www.facebook.com/rbloggers?fref=ts)

- [One R Tip a day](https://www.facebook.com/rtipaday?fref=ts)

<hr/>

### Websites ต่างประเทศ

เวปไซด์ต่างๆ ที่ผมเห็นว่าได้มีการเขียนบทความเกี่ยวกับอาร์ หรือเป็นเวปไซด์ที่รวบรวมเรื่องเกี่ยวกับอาร์ไว้เช่นเดียวกัน

- [Rstatistics](http://rstatistics.net/?)

- [R-blogger](http://www.r-bloggers.com/)

- [Learing R materials updated Oct 2015](http://blog.revolutionanalytics.com/2015/10/learning-r-oct-2015.html) อัพเดทใหม่ล่าสุด แหล่งความรู้เกี่ยวกับอาร์

- [Getting started with R](http://scs.math.yorku.ca/index.php/R:_Getting_started_with_R)

- [Stackoverflow](http://stackoverflow.com/tags/r/info) จาก stackoverflow เวปนี้เป็นเวปที่ผมใช้บริการทุกครั้งเมื่อเจอปัญหา หรืออยากได้ เทคนิคใหม่ๆ ในการเขียน แถมด้วยว่า stackoverflow ยังได้รวบรวม เอกสาร สื่อการสอน และทุกอย่างที่เกี่ยวกับอาร์ หรือผู้ใช้อาร์ควรจะรู้จัก เหม ทำไม สมัยที่ผมเริ่มต้น เนี้ย ไม่เห็นมีอะไรแบบนี้เลย


<hr/>

### R blogs
- [dataschool](http://www.dataschool.io/) **Most recommended**

- [Working with data](http://mazamascience.com/WorkingWithData/)

- [Jeromy Anglim's blog psychology and statistics](http://jeromyanglim.blogspot.com/)

- [The Chemical Statistician](https://chemicalstatistician.wordpress.com/category/r-programming/)


<hr/>

### Youtube channel

- [dataschool](https://www.youtube.com/user/dataschool/featured)

- [Roger Peng](https://www.youtube.com/channel/UCZA0RbbSK1IXeeJysKYRWuQ)

- [Jeff Leek](https://www.youtube.com/user/jtleek2007)

- [MarinStatLectures](https://www.youtube.com/user/marinstatlectures)

- [Christoph Scherber](https://www.youtube.com/user/phrygos)

- [How to R](https://www.youtube.com/channel/UCAeWj0GhZ94wuvOIYu1XVrg)

- [LearnR](https://www.youtube.com/user/TheLearnR)

<hr/>

### Websites ของคนไทย

- [Pairach Piboonrungroj](http://pairach.com/)

<hr/>

### R Tutorials

เป็นเวปไซด์ที่การสอบเกี่ยวกับอาร์แบบ online ที่ ผมเลยลองเข้าไปใช้แล้วประทับใจ

- [Try r](http://tryr.codeschool.com/) เหมาะสำหรับผู้ที่เริ่มต้นเรียนเกี่ยวกับอาร์

- [Udemy](https://www.udemy.com/user/charlesredmond/)

- [DataCamp](https://www.datacamp.com)

- [R in Coursera](http://pairach.com/2012/12/22/learn-to-use-r-for-free-with-coursera/) รวบรวมโดย Pairach

- [R in edX](https://www.edx.org/course/introduction-r-programming-microsoft-dat204x-0) มีหลาย วิชาเลยนะครับ

<hr/>

### Communities

- [Chiangmai - R: The first R user group in Thailand](http://chiangmair.wordpress.com/events/) ชุมชนคนใช้โปรแกรม R แรกของไทย แต่น่าเสียดายที่ยังไม่ค่อยได้มีการ update เท่าที่ควร

- [FB :Chiang Mai R](https://www.facebook.com/pages/Chiang-Mai-R/362933103793288)

<hr/>

### Documents เอกสาร

- [การใช้และสถิติพื้นฐาน](http://pioneer.chula.ac.th/~awirote/courses/res-tech-ling/statistics-and-r.pdf)

- [แนะนำโปรแกรมสำเร็จรูป R by KKU](home.kku.ac.th/weera/exp-design/R-introtro1.pdf‎)

- [แนะนำ package epicalc โดย มหาวิทยาลัยสงขลานครรินท์](hsmi.psu.ac.th/upload/forum/Intor2epicalcThai.pdf)

- [สถิติสำหรับการวิจัยทางการเกษตร : การวิเคราะห์ข้อมูลด้วยโปรแกรม R](www.natres.psu.ac.th/office/co_operative/co9/R.pdf)

- [โปรแกรมอาร์ (R) โดย อ.ดร.เฉลิมพงษ์ คงเจริญ](www.econ.tu.ac.th/doc/news/409/econtu_59_Chaleampong.pdf‎)

<hr/>

### Books

เป็นที่ผมสะสมเองครับ สามารถโหลดไปได้เลยครับ

1. [R in practice](http://1drv.ms/1KGB0Gl) หนังสือเล่นนี้เป็นเล่มโปรดของผมเล่มนึง แต่อาาจะไม่เหมาะกับ ผู้เริ่มต้นเท่าไหร่นัก


2. [R in action](http://1drv.ms/1KGAVT6) หนังสือเล่มนี้ครับ เหมาะกับผู้เริ่มต้นใช้ R อ่านเข้าใจง่าย มีตัวเอง ให้ทำตาม


3. [R for Dummies](http://1drv.ms/1KGB6ha) หนังสือนี้ผมคิดว่าเป็นหนังสือที่น่าอ่านอีกเล่มนึงนะครับ เหมาะสำหรับผู้เริ่มต้นจริง


4. [The R book](http://1drv.ms/1KGBe02) เล่มนี้ถือว่าเป็นหน้งมือเกี่ยวกับ R ที่ถือว่าครบเครื่อง แต่ก็ออกมาน่าแล้วพอสมควร ถ้าเทียบกับ R ในปัจจุบันแล้วถือว่าเก่าไปแล้วหละครับ แต่ถ้ามีไว้ก็ไม่ถือว่าเสียหายหรอกจริองไหมครับ


5. [R in nutshell](http://1drv.ms/1KGBfRE) เป็นเล่มที่เอาไว้ใช้เป็นคู่มือ มีประโยชน์มากๆครับ


6. [R graphics Cookbook](http://1drv.ms/1JkNcqZ) อีกเล่มที่สำคัญ นั้นคือ  หลักๆจะเป็นการใช้ ggplot2 package เพื่อการสร้างกราฟ ครับ


7. [Learning R](http://1drv.ms/1OrteTm) เป็นอีกเล่มครับ ที่น่าอ่าน อ่านง่าย เหมาะสำหรับผู้เริ่มต้น จริงๆครับ


<hr/>

### R Cheatsheet collection

Cheatsheet เหล่านี้ มีประโยชน์มากๆ เลยนะครับ ติดไว้ฝาผนังห้องทำงาน เวลานึกไม่ออก ก็ดูเพื่อเป็น reference

<div style = "text-align:center">[DOWNLOAD](https://www.rstudio.com/wp-content/uploads/2015/08/ggplot2-cheatsheet.pdf)
<div style = "text-align:center"><img src ="https://www.rstudio.com/wp-content/uploads/2015/03/ggplot2-cheatsheet.png"></div>

<div style = "text-align:center">[DOWNLOAD](https://www.rstudio.com/wp-content/uploads/2015/02/data-wrangling-cheatsheet.pdf)</div>

<div style = "text-align:center"><img src ="https://www.rstudio.com/wp-content/uploads/2015/03/data-wrangling-cheatsheet.png"></div>


<div style = "text-align:center">[DOWNLOAD](https://www.rstudio.com/wp-content/uploads/2015/02/rmarkdown-cheatsheet.pdf)</div>
<div style = "text-align:center"><img src = "https://www.rstudio.com/wp-content/uploads/2015/03/rmarkdown-reference-guide.png"></div>




Refererece:[Cheat sheet](https://www.rstudio.com/resources/cheatsheets/) from RStudio
