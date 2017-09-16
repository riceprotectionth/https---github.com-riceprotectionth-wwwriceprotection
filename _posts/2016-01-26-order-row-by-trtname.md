---
layout: post
title: "Order row data frame following the factor names"
excerpt: "เรียง แถวของ data frameใหม่ตาม factor ที่เรียงตามที่เราต้องการ"
tags: [Rtips]
comments: true
---

{% highlight r %}
> dat <- read_csv("/Users/sithjaisong/Desktop/ycom.csv") # โหลดไฟล์ที่ต้องการ
> # ตอนนี้ข้อมูลที่ผมมีนั้น  จะเห็นว่า trt ที่เรียงนั้น มันถูกเรียงตาม rep
> head(dat)
Source: local data frame [6 x 15]

    trt   rep    sm  sm y   moi  hill panicle  sunk mc_sunk float_sunk mc_float
  (chr) (int) (int) (dbl) (dbl) (int)   (int) (dbl)   (dbl)      (dbl)    (dbl)    
1    PR     1     1 2.320  14.0   108     214 261.8    13.1       64.1     14.0   
2    PR     1     2 2.570  15.6   108     230 283.8    13.7       62.1     14.5   
3    PR     1     3 2.485  13.8   108     202 255.6    13.4       56.9     13.1  
4    DT     1     1 2.295  14.0   108     240 268.3    13.2       73.7     13.3   
5    DT     1     2 0.205  13.7   108     235 252.7    14.3       68.9     15.2  
6    DT     1     3 2.110  13.6   108     246 272.0    14.1       91.8     14.5   

# แต่ผมจะเรียงตาม trt อย่างนี้

> target <- c("GM", "RP", "MJ", "DT", "PR") # ระบุว่าจะเรียงแบบไหน
> # อย่าลืมเปลี่ยนต้่องแปลงให้่เป็น factor และเรียง
> dat$trt <- factor(dat$trt, levels = target)
> # ใช้คำสั่ง order เพื่อ จัด row ว่าแต่ละ trt ที่เราระบุนั้นอยู่ row ไหนบ้าง แล้วก็เรียงตามนั้น
> newdat <- dat[order(dat$trt),] 
>head(newdat)
Source: local data frame [6 x 15]

     trt   rep    sm  sm y   moi  hill panicle  sunk mc_sunk float_sunk mc_float
  (fctr) (int) (int) (dbl) (dbl) (int)   (int) (dbl)   (dbl)      (dbl)    (dbl)  
1     GM     1     1 2.805  14.7   108     239 347.8    14.6       64.3     14.5   
2     GM     1     2 2.850  16.2   108     221 337.2    14.8       66.0     14.6   
3     GM     1     3 3.295  16.7   108     321 345.4    14.6       72.9     15.2  
4     GM     2     1 0.870  13.2   108     207 282.8    12.9       53.8     13.0   
5     GM     2     2 1.620  15.0   108     190 287.4    13.0       40.8     11.6   
6     GM     2     3 1.700  12.2   108     201 232.8    11.1       51.4     11.4  
{% endhighlight %}


หวังว่าจะเป็น ทิปที่มีประโยชน์ ไม่ม่ากก็น้อยนะครับ
Hope you enjoyed this useful tip.
<div style = "text-align:center"><img src ="/images/blog/sithsig.png" width = "100"></div>
{% highlight r %}
{% endhighlight %}
