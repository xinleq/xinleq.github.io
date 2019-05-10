---
title: selenium配置安装概要(回溯)
date: 2019-05-10 22:19:03
tags:
---

<p>selenium前世今生？</p>
<p>        前世今生？有点夸张。selenium是一款支持多语言的免费开源的自动化测试软件工具，现在已经更新到selenium3。</p>
<p>        selenium1包含selenium rc(用于运行自动化测试脚本)，selenium IDE（Firefox插件，提供图形界面录制和回放脚本）以及selenium grid(实现脚本并发执行)</p>
<p>        selenium2 是selenium1+webdriver</p>
<p>        selenium3去掉了seleniumRC，并在selenium2上进行了功能增强，例如提高自动化测试稳定性，支持更新更多的浏览器等。</p>
<h5 id="关于测试工具安装配置"><a href="#关于测试工具安装配置" class="headerlink" title="关于测试工具安装配置"></a>关于测试工具安装配置</h5><p>        网上度娘可以找到很多大神详尽的图文并茂的叙述，故不再啰嗦。</p>
<p>下面只提几个关键词，给自己加深记忆。</p>
<p>       selenium IDE插件直接搜索下载安装即可。</p>
<p>       <strong>着重点：selenium2</strong></p>
<p>       因为使用python进行自动化脚本的编写，所以是基于python环境的安装。</p>
<p>       1.<strong>python解释器</strong>：官网下载，安装</p>
<p>       2.<strong>pycharm</strong>：python编辑器，依旧是下载安装</p>
<p>       3.<strong>pip工具安装</strong>：搜索-下载，下载后解压，cmd下，找到setup.py文件所在的目录，输入”<em>python setup.py install</em>“命令进行安装</p>
<p>输入“<em>pip –version</em>“可查看是否安装成功，一般python会默认自带一个低版本的pip工具，但如后续安装中出现版本兼容问题，可使用此安装方式。</p>
<p>       4.<strong>selenium安装</strong>：<em>pip install selenium==2.48.0</em></p>
<p>      5.<strong>浏览器驱动</strong>：各浏览器都需要下载各自对应的驱动，并添加到path环境变量中。（在脚本中使用executable_path参数指明驱动文件所在路径也可。例如：<em>driver=webdriver.Firefox(executable_path=”c:\geckodriver”）</em>),selenium3.x支持Firefox48以后版本，需要下载驱动，而Firefox48之前版本则由selenium2.x支持，无需下载驱动（有内置驱动）。</p>
{% asset_img smile.png 依旧我美丽的大国宝 %}

