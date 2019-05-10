---
title: unittest跳过某个测试方法及命令行执行(追回)
date: 2019-05-10 21:54:55
tags:
---

<p>在批量执行测试用例时，某些测试用例想要忽略，可以在测试方法前加下列语句跳过此方法。</p>
<ol>
<li>@unittest.skip(“说明语句”)：无条件跳过</li>
<li>@unittest.skipIf(条件表达式，”说明语句”)：条件为真，忽略该方法</li>
<li>@unittest.skipUnless(条件表达式，”说明语句”)：条件为假，跳过该方法 </li>
</ol>
<hr>
<h6 id="命令行模式执行测试用例"><a href="#命令行模式执行测试用例" class="headerlink" title="命令行模式执行测试用例"></a>命令行模式执行测试用例</h6><p>命令行模式，切换到当前测试模块所在目录下，执行下面命令：</p>
<ol>
<li><p>通过命令直接运行整个测试模块</p>
<figure class="highlight plain"><table><tr><td class="gutter"><pre><span class="line">1</span><br><span class="line">2</span><br></pre></td><td class="code"><pre><span class="line">python -m unittest test_module1 test_module2.....</span><br><span class="line">例：python -m unittest -v MyTest #-v参数表示输出测试用例执行的详细信息</span><br></pre></td></tr></table></figure>
</li>
<li><p>执行测试模块中某个测试类</p>
<figure class="highlight plain"><table><tr><td class="gutter"><pre><span class="line">1</span><br><span class="line">2</span><br></pre></td><td class="code"><pre><span class="line">python -m unittest test_module1.TestClass</span><br><span class="line">例：python -m unittest -v MyTest.MyTestClass</span><br></pre></td></tr></table></figure>
</li>
<li><p>执行测试模块中某个测试类下的某个测试方法</p>
<figure class="highlight plain"><table><tr><td class="gutter"><pre><span class="line">1</span><br><span class="line">2</span><br></pre></td><td class="code"><pre><span class="line">python -m unittest test_module1.TestClass.test_method</span><br><span class="line">例：python -m unittest -v MyTest.MyTestClass.test_fun</span><br></pre></td></tr></table></figure>
</li>
</ol>
<h6 id="命令行模式，批量执行某个目录下的测试脚本"><a href="#命令行模式，批量执行某个目录下的测试脚本" class="headerlink" title="命令行模式，批量执行某个目录下的测试脚本"></a>命令行模式，批量执行某个目录下的测试脚本</h6><p>命令行模式，cd 切换到要测目录，执行命令</p>
<figure class="highlight plain"><table><tr><td class="gutter"><pre><span class="line">1</span><br></pre></td><td class="code"><pre><span class="line">python -m unittest discover</span><br></pre></td></tr></table></figure>
<p>discover命令的参数（可选）</p>
<p>-v：输出详细测试信息</p>
<figure class="highlight plain"><table><tr><td class="gutter"><pre><span class="line">1</span><br></pre></td><td class="code"><pre><span class="line">例 python -m unittest discover -v</span><br></pre></td></tr></table></figure>
<p>-s：执行发现测试脚本的目录，默认为当前目录</p>
<p>-p：模式匹配文件</p>
<figure class="highlight plain"><table><tr><td class="gutter"><pre><span class="line">1</span><br></pre></td><td class="code"><pre><span class="line">例 python -m unittest discover -p &quot;test*.py&quot;</span><br></pre></td></tr></table></figure>
<p>-t：工程的根目录下搜索可执行的测试脚本，默认是当前目录</p>