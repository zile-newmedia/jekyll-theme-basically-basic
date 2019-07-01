---
layout: post
title: 如何通过CSS运用媒体查询实现基础的网页平面设计？
author: imaginist
date: 2019-6-27
categories:
     - Plane design
---

## #Plane design
## #CSS：@media


如今的界面开发需要适应更多的平台，比如PC端，移动端。而各种平台页面的尺寸是不一样的，这样就加大了我们制作页面的难度。而运用CSS的媒体查询就可以解决这一问题，下面就给大家分享一下CSS如何通过运用媒体查询实现基础的网页平面设计。

- 首先准备html的文档，并且在文档中准备一个div空标签，如下图所示。
![avatar](http://m.qpic.cn/psb?/V13n1hdE00quqe/IPziSu55YKnKWa*ZqL1qr6rW8iZeXCsdiLHcZAS7tvU!/b/dL4AAAAAAAAA&bo=4AEWAeABFgERFyA!&rf=viewer_4&t=5)

- 其次给div中的样式类添加样式，如下图所示，样式主要设置了宽，高以及背景。
![avatar](http://m.qpic.cn/psb?/V13n1hdE00quqe/VeWrkp.sjVWuVkxi1z2WQUMkxxl7USsUAIREuPEBVJ4!/b/dDMBAAAAAAAA&bo=4AHAAeABwAERFyA!&rf=viewer_4&t=5)

- 然后运用@media规则进行媒体查询的设计，如下图所示，设置当页面宽度最小达到768的时候执行其下面的样式。
<br>
![avatar](http://m.qpic.cn/psb?/V13n1hdE00quqe/5A*jFXji.PNay5dw7N7KDeQmB1ytRwZ24Pd2xPTvurQ!/b/dL8AAAAAAAAA&bo=4AFWAeABVgERFyA!&rf=viewer_4&t=5)

- 最后媒体查询的尺寸也可以写多个，如下图所示，运用and将多个尺寸连接起来即可。
![avatar](http://m.qpic.cn/psb?/V13n1hdE00quqe/6jopNX2iYlQU0A0eNF5QG*9DYtU4GblqHw5SxY9Hpv0!/b/dL8AAAAAAAAA&bo=sQHkALEB5AARFyA!&rf=viewer_4&t=5)

  综上所述，媒体查询的使用主要运用尺寸来界定各种平台。