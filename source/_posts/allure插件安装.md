---
title: allure插件安装
date: 2020-03-18 17:56:15
tags:	
---

​       前两天pytest升级成最新版，allure原版本（具体哪版不记得了）因为冲突被退休，我把它卸载了。可是还是少不了它的，于是，今天装allure插件。之前跟老师学到的知识，插件是这样安装的：

1.在线安装：命令行输入*pip install pytest-allure-adaptor*（度娘给出的频率最高的答案）

结果：现在用这个命令安装的插件版本为1.7.0，2018年的，明显跟最新的pytest版本不配套，失败

2.本地安装：*pip install 本地安装包*

结果：失败。原因嘛，没有本地安装包.......

3.在线安装：*pip install pytest-allure*

结果：去年是成功的，插件版本本人没有了，配套命令行工具allure-2.7。但现在插件在我的pytest升级至5.4以后就用不了。而且现在输入这行命令只能得到如下结果

{% asset_img no.png 结果 %}

4.目前：*pip install allure-pytest*

结果：目前用起来挺好。命令行是在pypi网站上找的。下图是安装 成功的图片，可以通过安装图片看下具体版本匹配情况。allure命令行工具用的allure-2.13.2版的

{% asset_img success.png 结果 %}

