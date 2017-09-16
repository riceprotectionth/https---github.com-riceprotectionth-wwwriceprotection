---
title: Git and Github
layout: page
comments: true
---

<div style = "text-align:center"><img src="http://jmcglone.com/img/guides/git-basics.png"></div>


หลังจากได้เรียนรู้เกี่ยวกับ R แล้ว ก็จะทราบว่า การทำงานกับ R นั้นคือการสั่งด้วยการ พิมพ์คำสั่ง (script หรือ code)
ว่าด้วยเรื่องของการปฎิบัติ หลังจากที่ code เขียนเสร็จแล้ว ก็จะเก็บหรือ save ไว้ในเครื่องคอมของเรา ใช่ไหมหละครับ สมมุติว่า ขออธิบายตามรูปข้างบน ในแต่ละขั้นตอน เราจะ "save" ถ้าเราไม่มี Git เราก็จะไม่สามารถ กลับไป ก่อนที่เราจะ "save" ได้ ซึ่งโดย คนทั่วไป ก็จะเลือก "save as" กันใช่ไหมครับ เพื่อเลี่ยงการ save ทับ แล้ว เราก็จะมีหลาย version เช่น n เช่น fileAed1.R, fileAed2.R, fileAfinal.R, fileAfinal2.R หลายต่อหลาย version ซึ่งบางครั้ง อาจจะจำไม่ได้ว่าอันไหนเป็น version ที่ต้องการ แล้วถ้าโชคร้ายเราอาจจะเผลอ save ทับลงไปด้วยความบังเอิญ ถ้าเราใช้ Git แล้ว จะทำให้เราปวดหัวน้อยลง


<div style = "text-align:center"><img src ="https://www.prestashop.com/blog/en/files/2014/06/github-logo.png"></div>


Git ก็คือระบบติดตามการเปลี่ยนแปลงของไฟล์ตลอดที่มีการบันทึก ทั้งการลบหรือการเพิ่ม อะไรลงไปในไฟล์ Git จะบันทึกและบอกหมด แรกเริ่มจริงๆแล้ว Git ถูกใช้กันในหมู่ นัก programmer ครับ programmers ใช้ Git เพื่อร่วมกันพัฒนา software หรือ code Git คือ version control system อันหนึ่ง แปลกันตรงๆ คือ ระบบที่ช่วยควบคุมลำดับและขั้นตอนของการพัฒนา code ช่วยให้ผู้พัฒนา code สามารถ บันทึกการพัฒนาลงไปใน code พูดง่ายๆ คือ Git จะช่วยผู้ใช้ทราบถึงการเปลี่ยนแปลงระหว่าง code ดั่งเดิม กับ code ที่พัฒนาขึ้นมา Git ไม่ใช่เจ้าหรือระบบเดียวที่เป็น version control ครับแต่ยังมี เช่น SVN แต่ Git เป็นที่นิยมมากกว่า

 ถ้าไม่มี Github การจะทำงานร่วมกันกับ Git จะต้องพิมพ์ผ่าน command หรือ Terminal เท่านั้น ดังนั้น Github จึงถูกพัฒนาขึ้นมาเพื่อทำให้การทำงานกับ Git สะดวกและง่ายดายมากขึ้น โดยไม่ผ่าน command หรือ Terminal ซึ่ง ส่วนตัวแล้ว ผมชอบ Github แต่บางครั้ง การทำงานบน Github อาจจะมีปัญหาเกิดขึ้นได้ เช่น เกิด file conflict ได้ และ Github จะไม่ยอมให้เรา commit ดังนั้นเราจึงต้อง ทำบน Command หรือ Terminal แทน ผม คิดว่า ทางที่ดี ควรจะเรียนรู้ เกี่ยวกับ Git เบื้อนต้นไว้ ก็เป็นประโยชน์

Github คือ application ทำงานร่วมกันกับ Git โดยมี interface ที่ทำใช้งานง่ายและเป็นผู้ให้บริการเก็บ code ด้วย

## ประโยชน์ของ Github

- ช่วยเก็บ code ของเรา online คล้ายๆ dropbox หรือ google drive นอกจาก code แล้ว ยังสามารถเก็บ อะไรได้หลายอย่างนะครับ แต่ก็ไม่ได้ มาก เหมือน Google Drive Dropbox หรือ Onedrive แต่ก็สามารถเก็บ files ที่เราจะเอาไปวิเคราห์ หรือ รูปภาพ pdf ที่มีขนาดไม่ใหญ่มาก

- ช่วยให้เราเห็นข้อแตกต่างของ code ที่ถูกบันทึกในช่วงเวลาต่างๆ เช่น ก่อนหน้านี้ หรือ ที่ถูกพัฒนาโดยเพื่อนร่วมทีมหรือคนอื่น

- เอื้ออำนวยให้การร่วมกันพัฒนา code หรือ project นั้นๆ ได้อย่างราบรื่น ยกตัวอย่างเช่น project A มีนักพัฒนาสามคนร่วมกันพัฒนาจาก original code แต่ละคนก็พัฒนาจาก original code แตกกิ่งก้านการพัฒนาออกไป เมื่อมีนักพัฒนาอยากจะพัฒนาต่อจากที่นักพัฒนาทำไว้แล้วก็สามารถทำได้ หรืออยากจะพัฒนาจาก original code ก็สามารถทำได้เช่นกัน

- บันทึก code ได้ทั้งในเครื่องคอมพิวเตอร์ และ บน github ในเวลาเดียวกัน ง่ายๆ คือ การ backup

- การสมัครนั้นก็แสนจะง่ายครับ เข้าไปลงทะเบียน Github แล้วก็สามารถ download application ไว้ในเครื่องได้ครับ

### อ่านเพิ่มเติมเกี่ยวกับ Git และ Github

- ภาษาไทย Blog ของคุณ วัชรเมธน์ ชิษณุคุปต์ ศรีเนธิโรทัย [Git คืออะไร](http://www.select2web.com/git/git-1.html) ซึ่งอธิบายได้อย่างดีมาก

- English จาก Data School [Git and Github for Beginner](http://www.dataschool.io/git-and-github-videos-for-beginners/) อันนี้ก็ดีงามด้วยประการทั้งปวงครับ
ปล.ถ้าพบว่าข้อมีจุดใดไม่ถูกต้อง หรืออธิบายไม่ถูกต้องสามารถเขียนแนะนำเข้ามาได้ครับ จะขอบคุณอย่างมาก

<hr/>

## การ setup Github กับ Rstudio ได้ที่

<div style = "text-align:center"><img src = "http://38.media.tumblr.com/tumblr_mbsea7csd11qbchbvo1_500.gif" width = "580"></div>

การทำงานร่วมกันระหว่าง R ใน text editor ที่มี ขื่อว่า RStudio นั้น ช่วยสร้างความสะดวกหลายอย่าง ทำให้การใช้งานกับ อาร์นั้นไม่เป็นที่น่าหงุดหงิด แต่ความพิเศษนั้น ยังมีอีกคือ มี function ที่สามารถทำงานร่วมกันกับ Github desktop ซึ่ง เชื่อมต่อกับ Github

## สมัคร Github
[Click](https://github.com/) เข้าไปที่เวป https://github.com/ ครับ แล้วก็เข้าไป sign up เลยครับ อันนี้ สำหรับคนที่ยังไม่มี account

<div style = "text-align:center"><img src ="/images/blog/signupgithub.png" width = "580"></div>

##  โหลด Github desktop

คลิ้ก โหลด ได้ ที่นี่เลยครับ [Github Desktop](https://desktop.github.com/)  มี ทั้ง  Mac และ Window ครับ หน้านี้ก็จะมีอธิบายไว้นะครับ เอาหละครับ ผมจะไม่อธิบายในส่วนนี้นะครับ เพราะว่า เราโหลดเพราะว่า เราจะใช้แค่ Function ของมันเท่านั้น แต่เราจะเชื่อมต่อ Github desktop กับ RStudio แล้วเราจะ ใช้งาน Github จากโปแกรม RStudio ครับ คงไม่งงนะครับ

ก่อนที่จะเข้าไป set ใน RStudio เราจะต้องเข้ามา set ใน Github ก่อน นั้นคือ sign in account Github desktop ก่อนให้เรียบร้อย

โดย ของ Mac ก็ คล้ายๆ กับโปรแกรมทั่วๆไป คือ เข้าไป ที่ Preference > Accounts ใส่ email address และ  password ให้เรียบร้อย

ส่วน Window ไปที่ setting แล้วก็เข้า ไปใส่ email address และ password เช่นกัน

<hr/>

## Setup RStudio

เมื่อเสร็จเรียบร้อยแล้ว ก็ ทำการเปิด RStudio ครับ ถ้าใครมาหน้านี้แล้วยังไม่รู้จัก RStudio ขอให้กลับไปอ่าน เกี่ยวกับการโหลด และใช้งานกันก่อนนะครับ

เปิด Studio ไปที่ tool bar ข้างบน จะเจอคำว่า Tools -> Global Options แล้วก็จะเห็นอย่างภาพข้างล่าง

<div style = "text-align:center"><img src ="/images/blog/globaloption.png" width = "580"></div>

ทีนี้ หา Git/SVN แล้ว คลื้ก ช่องที่ผม ทำสีแดงไว้นะครับ เท่านี้ โปรแกรมก็จะหาที่อยู่ ที่จะไว้ใช้เรียก Github ได้แล้วครับ

ถ้าเป็น Mac ตัวสุดท้าย จะปรากฎ  git


ถ้าเป็น Window จะต้องปรากฎ git.exe นะครับ


แล้วโปรแกรมจะขอให้เรา restart ครับ ก็ restart


ถ้ามีปัญหาลองเข้าไปอ่านที่นี่ก่อนครับ [click](https://support.rstudio.com/hc/en-us/articles/200532077-Version-Control-with-Git-and-SVN)

### การใช้งาน How to use

1.New repository เรื่มต้น จะต้อง สร้าง Project ก่อนครับ ใน อาร์ จะเรียกว่า Project แต่ พอ เข้าไปใน Github เขาจะเรียกว่า repository หรือเรียกสั้นๆ เขาก็จะเรียกกันว่า repo เข้าไปที่ github.com ใน account ของเรา มองหาปุ๋ม สีเขียว ที่เขียนว่า new repository ครับ

<div style = "text-align:center"><img src ="/images/blog/newrepo.png" width = "400"></div>


2.Name repository คลิ้กแล้วก็ สร้าง repo ชื่อว่า test แล้วกัน ครับ

<div style = "text-align:center"><img src ="/images/blog/namerepo.png" width = "580"></div>


3.Copy repo URL หลังจากนั้น จะเห็นหน้านี้ขึ้นมาอย่าเพิ่งตกใจครับ เพราะว่า เรายังไม่มีอะไรอยู่ใน repo นี้เลย copy ที่ผมทำสีแดงนี้ไว้นะครับ

<div style = "text-align:center"><img src ="/images/blog/github.png" width = "580"></div>

พอมาถึงตอนนี้ ในส่วนของ github เสร็จไปเรียบร้อยแล้ว เอาหละครับ ทีนี้ ก็จะเข้ามาทำในส่วน จอง RStudio กันต่อ


4.create new project in RStudio เปิด RStudio ครับ เข้าไปที่ ขวาบน ครับ จะเจอคำว่า  Project คลิ้ก ครับ  > New Project

<div style = "text-align:center"><img src ="/images/blog/createproject.png" width = "580"></div>


5.select Project > Version Control แล้วหน้าต่าง  นี้ก็จะโผล่ขึ้นมา แล้วเลือก Version Control แล้ว เลือก  Git

<div style = "text-align:center"><img src ="/images/blog/selectproject.png" width = "580"></div>



6.Version Control เลือก Git


<div style = "text-align:center"><img src ="/images/blog/gitproject.png" width = "580"></div>



7.paste repo url เข้ามาหน้านี้ URL ที่ ผมบอกให้ copy มาจาก  github มาใส่ ลงในช่วง Repository URL ตรงนี้ เลย ครับ แล้วก็ คลิ้ก Create Project ครับ เท่านี้ ก็เรียบร้อยแล้ว

<div style = "text-align:center"><img src ="/images/blog/projectsetup.png" width = "580"></div>


### การทำงาน

ผมลองเขียน code และ  save บันทึกชื่อ file ว่า test1.R นะครับ ตอนนี้ file ของเรา ยังอยู่ในเครื่อง นะครับ ยังไม่ได้ ถูกบันทึก ใน github

<div style = "text-align:center"><img src ="/images/blog/test1.png" width = "600"></div>


แล้วลอง click ที่คำว่า Git เราก็เพียงเลือก ทำเครื่องหมายถูก ข้างหน้า file1 ของเรา ครับ แล้ว click commit ครับ แล้วบันทึกลงไป ว่าอะไรก็ได้ครับ เพื่อ เป็น note ของเรา เมื่อเราอยากจะรู้ว่า code นี้ เราได้ทำอะไรไป ขั้นตอนนี้ สำคัญนะครับ ต้อง commit นะครับ code ที่เราเขียน ถึงจะบันทึกใน Github

<div style = "text-align:center"><img src ="/images/blog/commit1.png" width = "600"></div>

เมื่อ ขึ้นตอนทุกอย่าง ไม่มีปัญหา ก็จะปรากฎ อย่างข้างล่างนี่นะครับ

<div style = "text-align:center"><img src ="/images/blog/finishcommit.png" width = "600"></div>


ถ้าผมมีการ แก้ไข  code แล้ว  save

<div style = "text-align:center"><img src ="/images/blog/commit2.png" width = "600"></div>


สมมุติว่า ผม เปรียบเทียบดูได้ว่า ที่ผม commit ใหม่นั้น แตกต่างกับ ที่ commit ไปครั้งที่แล้ว อย่างไร แต่ ถ้าสมมุติว่า ผมไม่พอใจ ที่ผมเพิ่ง commit ไป ผมสามารถย้อน กลับไป เมื่อไหร่ก็ได้ โดย คลื้ก ที่  View file แล้วสามารถ save กลับมาก็ได้ ครับ

<hr/>

ภาพนี้ ก็เป็นภาพการ์ตูน ที่แสดงให้เห็นว่า เมื่อเราทำงานกับ Git เราจะสามารถเห็นความเปลี่ยนแปลงของ script โดยที่เราไม่จำเป็นจะต้องเปลี่ยนชื่อไฟล์

<div style = "text-align:center"><img src ="http://imgs.xkcd.com/comics/git_commit.png"></div>
