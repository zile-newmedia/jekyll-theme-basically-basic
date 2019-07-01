---
layout: post
title: 如何通过SVG中的ViewBox实现基础的网页平面设计？
author: imaginist
date: 2019-6-27
categories:
     - Plane design
---

## #Plane design
## #SVG：ViewBox

- **SVG 的根元素**
SVG的根元素有width、height和viewbox属性。<svg width="198px" height="188px" viewBox="0 0 198 188"这三个属性在SVG展示的时候都起到了十分重要的作用。希望现在大家能很好地理解“视口”这个概念。在众多地方它都用于描述在设备上能够观看内容的面积。
<br>
举个例子，一部手机的视口可能只有320像素宽480像素高，而桌面电脑则一般有1920像素宽1080像素高。宽度和高度属性对于创造一个视口十分有用。透过这个定义的视口，我们可以看到内部定义的SVG形状。和普通的Web页面一样，SVG的内容可能会比视口大，但是这不意味着多余的部分就不存在，只是我们看不到而已。
<br>
- **视框（viewbox）**
而另一方面，视框（viewbox）则定义了SVG中所有形状都需要遵循的坐标系。
你可以把视框值0 0 198 198视为对矩形左上角和右下角的描述。前两个值被称为min-x
和min-y，用于描述左上角的位置。而接下来的两个值被称作宽度和高度，可以描述右下角的位
置。
<br>
因此viewbox属性可以让你缩放图片。例如，你可以这么设置viewbox属性：
<svg width="198px" height="188px" viewBox="0 0 99 94"
那么其中的形状为了填满SVG的宽度和高度，就会被放大。
举个例子，我用svg画了个半径200px的圆。
![avatar](http://m.qpic.cn/psb?/V13n1hdE00quqe/KdFSq6afsvp1OZ10dtWbTCbvN3uuzJm4h80SwxsXx1c!/b/dFEBAAAAAAAA&bo=1wRFANcERQADFzI!&rf=viewer_4&t=5)
如果是在一个400*400的画布上，圆正好撑满整个画布，挺好的。
好了，然后我要把这个圆嵌入到自己的页面里的svg标签里去，页面的svg标签尺寸是由实际业务需要来定的，不一定正好是，可能大可能小，还可能不是正方形。
![avatar](http://m.qpic.cn/psb?/V13n1hdE00quqe/TYvK6evWel4T3pG2tHXr52jgquVh3rk4xi3seUVFMkg!/b/dFQBAAAAAAAA&bo=1ASCANQEggADFzI!&rf=viewer_4&t=5)
正常情况下面浏览器中显示是这个样子的
![avatar](http://m.qpic.cn/psb?/V13n1hdE00quqe/hrY.zRcuAKqM17gBbxAJnNTzw8iqPe0xHwkmtDBHjPE!/b/dL4AAAAAAAAA&bo=7wDQAe8A0AEDFzI!&rf=viewer_4&t=5)
产品见了肯定不乐意啊，“我要整个圆啊，谁要这种残次品啊”。
咋整的，要么把这个圆的代码改了吧。
可如果不是简简单单一个圆呢，而是一大堆复杂代码，改个鬼啊。
呵呵~此刻，便是viewBox用武之地！
![avatar](http://m.qpic.cn/psb?/V13n1hdE00quqe/862jdTUIJplljdvll6u0N1t8lrkBHn*7sPCRwrfGhrw!/b/dFQBAAAAAAAA&bo=XAR2AFwEdgADFzI!&rf=viewer_4&t=5)
摇身一变就成这样了
![avatar](http://m.qpic.cn/psb?/V13n1hdE00quqe/t3kTTik7PeF7k91LoOaNmqnjeyabaQYz7hk3DVqM4FE!/b/dL8AAAAAAAAA&bo=WwRrAVsEawEDFzI!&rf=viewer_4&t=5)
viewBox的四个参数分别代表：最小X轴数值；最小y轴数值；宽度；高度。
前两个暂时用不到，个人理解除非要对内部svg做整体位移，否则一般都是0 0，暂时先不做解释，重点关注后两个参数。
想象一下viewBox是个400*400的正方形，但是单位不是px，也不是任何一个css单位，就当是一个假的单位吧。在viewBox放了一个圆，这个圆的半径是200，单位也不是px，而是变成了和viewBox的单位一模一样的那个假的单位。为啥说是假的呢？因为这个单位代表的长度是会变的，接着看。
svg有个特点，在默认情况下，会调整这个viewBox的大小，让这个viewBox正好能被放进svg里去。拿上面例子来说，viewBox是个正方形，而svg的宽度比高度小，所以就把viewBox的大小缩小到和svg宽度一样，就能正好将viewBox放进svg里来了。所以现在viewBox的实际大小是个150px*150px的正方形。
所以现在可以确定的是，viewBox的一个单位代表的长度 = 150px/400 = 0.375px。
而viewBox内部的所有数值*0.375px才是真正的长度。那个circle的圆心实际上是在坐标75px, 75px的位置上，半径为75px。