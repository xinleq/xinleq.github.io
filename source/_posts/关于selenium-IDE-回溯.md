---
title: 关于selenium IDE(回溯)
date: 2019-05-10 22:42:14
tags:
---

<h4 id="selenium-IDE"><a href="#selenium-IDE" class="headerlink" title="selenium IDE"></a>selenium IDE</h4><h5 id="定义"><a href="#定义" class="headerlink" title="定义"></a>定义</h5><p>Selenium IDE是Firefox和Chrome浏览器插件，可实现网页操作步骤的录制和回放，可执行简单测试逻辑的自动化测试，可将它的脚本导出为java,python等多种语言格式的程序代码，可将认为操作网页的各种动作直接转化为自动化测试的程序代码，便于编写更加复杂的测试代码。</p>
<h5 id="特点"><a href="#特点" class="headerlink" title="特点"></a>特点</h5><p>优点：小巧简单，易于上手</p>
<p>缺点：录制脚本转换为其他语言脚本时有可能出现一些错误，需要人为修改</p>
<p>总之，Selenium IDE工具仅适合用于执行简单逻辑的自动化测试脚本，或通过录制方式导出相关的自动化测试脚本，不适于执行大中型项目的自动化测试程序</p>
<h5 id="selenium-IDE脚本的组成"><a href="#selenium-IDE脚本的组成" class="headerlink" title="selenium IDE脚本的组成"></a>selenium IDE脚本的组成</h5><p>command（命令)、target(目标定位)、value(值)</p>
<h6 id="Selenium-IDE的command命令类型："><a href="#Selenium-IDE的command命令类型：" class="headerlink" title="Selenium IDE的command命令类型："></a>Selenium IDE的command命令类型：</h6><ul>
<li>Assertions(断言)类型：</li>
</ul>
<p>waitForText：在测试执行时用来判断某些文本是否显示在界面中。若显示，测试程序继续执行；若<em>等待一段时间后</em>，不显示指定文本，测试用例被设定为<em>执行失败</em>状态，测试脚本<em>继续执行</em>。（option里可设定等待时间，默认30秒）</p>
<p>assertText：测试执行时用来判断界面上某些文本是否与预期一致。若一致，测试程序继续执行；若不一致，测试用例被设定为<em>执行失败</em>，<em>后续</em>测试脚本<em>不再执行</em>。</p>
<p>verifyText：测试执行时用来判断界面上某些文本是否与预期一致。若一致，测试脚本继续执行；不一致，测试用例被设定为<em>执行失败</em>，测试脚本<em>继续执行</em>。</p>
<ul>
<li>Accessors(存储器)类型：</li>
</ul>
<p>    storeTitle：主要用于将网页的title内容存储到变量中</p>
<p>    echo：主要用于常量字符串和变量字符创的打印输出，特别用于调试脚本时输出脚本的状态</p>
<p>例：命令</p>
{% asset_img 存储器类型命令.png 存储title内容到变量a，在log显示区域打印变量a的值 %}
<p>结果</p>
{% asset_img  存储器类型命令结果.png 存储title内容到变量a，在log显示区域打印变量a的值 %}
<ul>
<li><p>Actions(动作)类型：</p>
<p>open：打开浏览器窗口</p>
<p>openWindow：打开新的Firefox浏览器窗口</p>
<p>selectWindow：选择一个处于打开状态的窗口</p>
<p>pause：暂停（单位ms)</p>
<p>type：输入字符</p>
<p>click：点击一个按钮，链接，单选或复选框</p>
<p>refresh：刷新当前页</p>
<p>close：关闭浏览器窗口</p>
</li>
</ul>
<hr>
<p>以上内容非原创，参考《自动化框架实战指南》，命令非全部，仅为常用几种基本命令<br>
<iframe title="国宝治愈系列" src="//player.bilibili.com/player.html?aid=31723902&cid=55479363&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true" height="300px"> </iframe>
</p>

