---
layout: post
title: การใช้ R ระดับต้น บทที่ 2
excerpt: "เนื้อหาจะเป็นการ import files  ทีละมากๆ"
tags: [R]
modified: 2015-10-16
comments: true
---

ตอนนี้ จากบนความที่แล้วที่เกี่ยวข้องกับความรู้พื้นฐานเกี่ยวกับไฟล์และการอ่านไฟล์ด้วยอาร์ มาถึงตอนนี้ จะเป็นการสอนเทคนิค เกี่ยวกับการนำไฟล์เข้าอาร์ ในกรณีที่ต้องการนำเข้าหลายไฟล์ ในหลายๆ ครั้ง เรามักจะเป็นไฟล์ ไว้หลายไฟล์ เช่น ไฟล์ file2013, fil2014, file2015 ซึ่งมีโครงสร้างของการจำเก็บข้อมูลแบบเดียวกันแต่เป็นคนละปี เพื่อนๆ อาจจะลองทำดูเล่นเองก็ได้นะครับ ลอง สร้าง file2000 จนถึง file2005 ขึ้นมา
ถ้าเรามาดู นะครับ ใน folder เราจะมี

- file2000
- file2001
- file2002
- file2003
- file2004
- file2005


file2000 file2001 file2002 file2003 file2004 file2005

{% highlight r %}
> ?read.csv #แปลว่า สงสัย read.csv
{% endhighlight %}

{% highlight r %}

> # หน้าตาคำสั่งของ read.csv ครับ
> read.csv(file, header = TRUE, sep = ",", quote = "\"", dec = ".", fill = TRUE, comment.char = "", ...)

{% endhighlight %}

file = the name of the file which the data are to be read from.

เห็นไหมหละครับ ว่า คำสั่งนี้ สามารถอ่านไฟล์ได้แค่ครั้งละไฟล์

เอาหละ เรามาดู วิธีวิธีที่ดีกว่านี้ ครับ แต่ก็จะต้องเรียนรู้เพิ่มไปอีกระดับหนึ่ง
เรามาเรียนรู้เกี่ยวกับอาร์เพิ่มขึ้นอีกสักนิดนึง
เมื่อ เรามีไฟล์ที่ต้องการวิเคราะห์ หรือ ต้องการให้อาร์ทำงานด้วย มากกว่าหนึ่ง วิธีการที่สะดวกและง่ายนั้นคือ จะต้อง สร้าง list ผมขอไม่อธิบายว่า list คืออะไร แต่ถ้าอย่างรู้ว่ามาคืออะไร ลองย้อนกลับไปบทความของผมเก่าๆ ที่มี ลองเรียนรู้ เกี่ยวกับอาร์เบื้อต้นกัน

1. สร้าง list Of Files

2. แต่ละ list ก็จะสามารถอ่าน read the file

เอาหละครับ เรามาสร้าง list กันก่อน

เนื่องจากเรา ให้ชื่อไฟล์ของเรา โดยมี ```file``` นำหน้าแล้วเปลี่ยน แค่ 2001 ถึง 2005

{% highlight r %}
> seq(2001, 2005)
[1] 2001 2002 2003 2004 2005
> year <- paste("file", 2001, ".csv", sep = "")
[1] "file2001.csv"
{% endhighlight %}


{% highlight r %}
> filenames
[1] "file2001.csv" "file2002.csv" "file2003.csv" "file2004.csv" "file2005.csv"
> filenames[1]
{% endhighlight %}


{% highlight r %}
> for (i in filenames) {
read.csv(i)
}
{% endhighlight %}

หรือ อาจจะใช้ ```list.file``` function แล้ว อาจจะ ใส่ pattern เพื่อ ให้โปรแกรม หาไฟล์ที่มีชื่อ ''file''

{% highlight r %}
> list.files()
> list.files("document/CSV")
> list.files(pattern = "file")
{% endhighlight %}
