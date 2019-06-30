---
layout: post
title: 关于文件传输
author: imaginist
date: 2019-6-27
categories:
     - Learning notes
---


## #Learning notes
## #File Transfer Protocol


## 文件传输（FTP）


![avatar]
(http://m.qpic.cn/psb?/V13n1hdE00quqe/BzuTfzsm4Mth6lP8wyXeVmTslNjIVee8hYLfCpK5Bks!/b/dAQBAAAAAAAA&bo=eAQpAXgEKQEDJwI!&rf=viewer_4&t=5)


## FTP工作机制


![avatar]
(http://m.qpic.cn/psb?/V13n1hdE00quqe/wX53EtsNo*gFXK7R607AepFnWCBeI2LvAbMRjzGdzY0!/b/dL4AAAAAAAAA&bo=7QKdAe0CnQEDFzI!&rf=viewer_4&t=5)

- 使用两条TCP连接：一条用来控制，另一条用于数据（文件）的传输。
- 用于**控制的TCP连接**主要在FTP的控制部分使用。例如登录用户名和密码的验证、发送文件的名称、发送方式的设置。
- 用于控制的TCP连接在进行文件GET、PUT、以及文件一览（LIST）等操作时，每次都会建立一个用于**数据传输的TCP连接**。数据的传输和文件一览表的传输正是在这个新建的连接上进行。当数据传送完毕之后，传输数据的这条连接也会被断开



##TCP/IP分层模型与通信示例


![avatar](http://m.qpic.cn/psb?/V13n1hdE00quqe/HlPPQXq0z1ktejzFLnaEA2tk*G0JKbykWvKPB1i24gY!/b/dL8AAAAAAAAA&bo=hgLjAYYC4wEDFzI!&rf=viewer_4&t=5)

- 数据包首部的层次化
- 每个分层中，都会对所发送的数据附加一个首部，在这个首部中包含了该层必要的信息，如发送的目标地址以及协议相关信息。通常，为协议提供的信息为包首部，所要发送的内容为数据。




##TCP/IP分层模型与通信示例

###数据包首部的层次化

- packets包
- frames帧
- data packets数据包
- segment段
- messages消息

![avatar](http://m.qpic.cn/psb?/V13n1hdE00quqe/0xwtX1Iu2MFKM0*I*AwuHdhL*oRdxlbjTQt8ZvmqS*Q!/b/dL8AAAAAAAAA&bo=fgLfAX4C3wEDFzI!&rf=viewer_4&t=5)


以上五个述语都用来表述数据的单位。
**包**可以说是全能性述语。**帧**用于表示数据链路层中包的单位。而**数据包**是IP和UDP等网络层以上的分层中包的单位。**段**则表示TCP数据流中的信息。**消息**是指应用协议中数据的单位。
