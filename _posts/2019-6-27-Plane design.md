---
layout: post
title: 怎样把图片以最合适的比列呈现站网页里面？
author: imaginist
date: 2019-6-27
categories:
     - Plane design
---

## #Plane design
## #Picture presentation

有人说“一图胜千言”，确实如此。我们网页中关于松饼的文字介绍再多，也没有图片有吸
引力。下面我们就在页面上方添加一张松饼的图片，效果类似引诱用户往下看的大题图。

![avatar](http://m.qpic.cn/psb?/V13n1hdE00quqe/FXACxEed2DlvI2.w1Ryr1LvgtkYoo7lSJpORSlBAJUQ!/b/dFQBAAAAAAAA&bo=9QBtAfUAbQERFyA!&rf=viewer_4&t=5)

哇，真是好大一张图（2000像素宽），可是它让整个网页看起来都失衡了。
不行，我们必须解决这个问题。是不是可以用CSS给图片指定固定宽度？但问题是我们想让它能在不同大小的屏幕中自动缩放。
比如，我们例子中的iPhone5S屏幕宽度为320像素，如果我们把图片设置成320像素宽，那么
iPhone5S屏幕旋转后又怎么办呢？这时候320像素岂不是变成了480像素了？其实，解决方案很简单，只要一行CSS代码就可以让图片随容器宽度自动缩放啦！
在这里我们创建一个CSS文件：“css/styles.css”，将它链接到HTML页面的头部。
以下是我们在这个CSS文件中写的代码。一般来说，应该先设置一些默认值。现在我们就加入这点代码：
img {
 max-width: 100%;
} 

![avatar](http://m.qpic.cn/psb?/V13n1hdE00quqe/CWHXPzXbZgiDXyOJkx5Kr8JfUNXdd6R8ZCVR2Mzo6oc!/b/dL8AAAAAAAAA&bo=7QBkAe0AZAERFyA!&rf=viewer_4&t=5)
就这样，页面视口就就可以随着页面大小变化而变化了！回到手机上，刷新页面，结果比较符合预期了。