---
layout: post
title: Find and Replace in R
excerpt: "Find and Replace function in R"
tags: [R]
modified: 2015-11-16
comments: true
---

คือ เมื่อวาน มีน้องในเลป เข้ามาถามเกี่ยวกับ การใช้ อาร์ เพื่อ จะเอาไปใช้กับงานวิจัยของเขา แล้ว มันมี Function นึงใน  excel ที่ ค่อนข้างจะมีประโยชน์ และก็สามารถทำในอาร์ได้ แต่ น้องคนนี้ก็ยืนยันจะทำใน excel อยู่ดี คือ ผมเองก็ไม่เคยจะได้ศึกษาเท่าไหร่ ในเรื่อง ที่ว่า จะ หา function อะไร ใน อาร์ ที่ทำงานคล้ายๆ กับ Find and Replace   ผมเอง ก็ลอง หา หา ไป เรื่อย แล้ว ก็แก้ กัน ไป ผมเลย พบ function `recode` จาก `car` package

{% highlight r %}
library(car)
{% endhighlight %}

ผมเอาตัวอย่างที่เป็น data frame มานะครับ เพระาว่า ปกติ เวลาเราทำงาน ข้อมูลเรามักจะเป็น data frame

### ถ้าเราต้องการเปลี่ยนแค่ column เดียว
{% highlight r %}
x <- data.frame(col1 = c(1, 1, 2, 2), col2 = c("x", "x", "y", "y"))
x
col1 col2
1    1    x
2    1    x
3    2    y
4    2    y
x$col1 <- recode(x$col1, "1 = 5 ; 2 = 10 ")
x$col2 <- recode(x$col2, "'x' = 1; 'y' = 2")
 col1 col2
1    5    1
2    5    1
3   10    2
4   10    2
{% endhighlight %}


บางครั้ง ข้อมมูลที่ บันทึกไว้ เรา code เป็น ตัวอักษร ทั้งหมด ทุก column ของ data frame



{% highlight r %}
library(car)
y <- data.frame(col1 = c("M", "M", "F", "F"), col2 = c("F", "F", "M", "M"))

y

col1 col2
1    M    F
2    M    F
3    F    M
4    F    M

for (i in 1:ncol(y)) {

  y[, i] <- recode(y[, i], "'M' = 1 ; 'F' = 2")

}

y
 col1 col2
1    1    2
2    1    2
3    2    1
4    2    1

{% endhighlight %}

เรามาลองดูอีก package ชื่อ `DataCombine` ไม่ได้อยู่บน CRAN แต่สามารถโหลดจาก Github  ซึ่งผมเองคิดว่าน่าสนใจ เรามาลองกันดูนะครับ

{% highlight r %}
> devtools::install_github('christophergandrud/DataCombine')

> ABData <- data.frame(a = c("London, UK", "Oxford, UK", "Berlin, DE",
                           "Hamburg, DE", "Oslo, NO"),
                     b = c("London, UK", "Oxford, UK", "Berlin, DE",
                           "Hamburg, DE", "Oslo, NO")
                     )

> Replaces <- data.frame(from = c("UK", "DE"), to = c("England", "Germany"))

> Vars <- names(ABData)

>for(i in 1:length(Vars)){

  temp <- FindReplace(data = ABData, Var = paste(Vars[i]), replaceData = Replaces,
                         from = "from", to = "to", exact = FALSE)

  ABData <- temp
  }
{% endhighlight %}

ผ่านไว้ครับ

<div style = "text-align:center"><img src ="/images/blog/sithsig.png" width = "100"></div>
{% highlight r %}
{% endhighlight %}
