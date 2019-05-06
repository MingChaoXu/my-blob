---
title: pytorch--并行bug
date: 2019-05-06 10:21:13
categories: 
- Technology
tags: 
- pytorch
mathjax: true
---

官方版本的pytorch 并行方式一般使用下面这种方式：

{% codeblock lang:python %}
> id = '0,1'
> model = nn.DataParallel(model, device_ids=id) 
{% endcodeblock %}

这种并行方式主程序只会运行一次，并在跑模型前向的时候自动把batch平分到各卡，这就带来一个问题，当模型有两个输入时，例如一个batch为32，1个batch为2，假如用4卡并行，会出现第一个输入均分到各卡上是batch为8的tensor，但是第二个输入会有卡分配不到tensor，这时候程序会报错。我理解的错误是由这个原因导致的，解决办法也许是换一种并行方式，利用broudcast整个各卡信息。
