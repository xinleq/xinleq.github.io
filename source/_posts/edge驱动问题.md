---
title: edge驱动问题
date: 2019-05-12 11:24:22
tags:
---

这是硬盘坏的第几天来着？资料恢复行动已经告一段落，能回收的资料已经回收，电脑上之前的软件在陆续安装。

因为硬盘的关系，系统也恢复了一下，结果升级后，在用selenium3写脚本时出现了新的问题，关于驱动

之前发现的问题，虽然系统是64位的，但使用IE11的64位驱动，selenium3的键盘输入简直慢到令人发指。换32位驱动正常。至于驱动选择，与selenium版本号一致即可

edge浏览器之前是17版本的，17134，官网可以下到对应驱动

https://developer.microsoft.com/en-us/microsoft-edge/tools/webdriver/，selenium3会出现resoucing Error，但是脚本可以正常执行。然而此次系统恢复到原来的老版本，又更新直接更到最新版本，edge版本也更到18版本Microsoft EdgeHTML 18.17763，

于是按照官网给的命令输入然后悲剧，浏览器打开网页变的很慢。

chrome打开某些网站也会很慢，目前的水平来说，使用Firefox似乎是最好选择。

以上.....

待解决......