---
layout: post
title: "为博客添加统计和SEO功能"
date: 2016-02-28 10:09:06 +0800
comments: true
categories: Octopress
tags: [octopress, 博客统计, SEO]
keywords: seo, octopress, analytics, 站内搜索
description: 为博客添加统计和SEO功能
---
>引言 你想自己的博客被更多的人看到吗？你想你的博客网站有更好的人气和流量吗？
大多时候，我们的博客都没有像新浪、CSDN或者ITEYE等一样，有很高的访问量，原因在于我么的博客文章没有被搜索引擎抓取到。你需要做到以下几点：

![上图](http://cepos.img47.wal8.com/img47/537802_20160227224327/145662966874.jpg
)
##### 将自己的博客提交到各大搜素引擎


  [http://urlc.cn/tool/addurl.html](http://urlc.cn/tool/addurl.html)

   [http://tool.lusongsong.com/addurl.html](http://tool.lusongsong.com/addurl.html)

提交到搜素引擎了，大大地增加了你博客被搜索到的几率。

##### Optopress 文章的规范格式
你还需要做的是为你的网站、文章添加描述信息、关键字，来帮助用户准确的搜索到你的文章。关键字和描述是指网页head部分的元标签meta，是给搜索引擎看的，以此希望用户可以比较容易找到。

为你的每篇文章添加描述和关键字，本文的文件头如下：
```
---
layout: post
title: "为博客添加统计和SEO功能"
date: 2016-02-28 10:09:06 +0800
comments: true
categories: Octopress
tags: [octopress, 博客统计, SEO]
keywords: seo, octopress, analytics, 站内搜索
description: 为博客添加统计和SEO功能
---

```
你的博客首页也需要添加描述和关键字，首页文件index.html是：

```
source/index.html
```
Optopress模版实现了文章的描述，source/\_includes/head.html中：
```
 {% capture description %}{% if page.description %}{{ page.description }}{% else %}{{ content | raw_content }}{% endif %}{% endcapture %}
  <meta name="description" content="{{ description | strip_html | condense_spaces | truncate:150 }}">
 {% if page.keywords %}<meta name="keywords" content="{{ page.keywords }}">{% endif %}
```
此外，也可以在_config.yml里添加默认的description和keywords。

##### 统计工具

Optopress 默认带了Google Analytics工具，这个国内无法使用，不再赘述。
国内，［CNZZ］(http://zhanzhang.cnzz.com/)流量统计使用较广，注册后，添加并验证你的网站就可以添加统计代码了，选好自己喜欢的样式，获得代码，可添加到source/\_includes/custom/footer.html中。即可查看每天你的博客的流量，进行相应的优化了。
最后还要提的就是百度站长工具和百度统计了，方法和CNZZ方法类似，统计代码也可以添加到source/\_includes/custom/footer.html中。但是我发现似乎百度统计并不太准确，并且百度很难搜的到我的博客。
统计代码大致如下，包括百度统计和CNZZ：
```
<p>
  Copyright &copy; {{ site.time | date: "%Y" }} - {{ site.author }} -
  <span class="credit">
          Powered by
          <a href="http://octopress.org">Octopress</a>
  </span>
  <script type="text/javascript">
        var _bdhmProtocol = (("https:" == document.location.protocol) ? " https://" : " http://");
        document.write(unescape("%3Cscript src='" + _bdhmProtocol + "hm.baidu.com/h.js%3F25fb42e16458b238f8da9ba05d6b9d4d' type='text/javascript'%3E%3C/script%3E"));
  </script>
  <script type="text/javascript">var cnzz_protocol = (("https:" == document.location.protocol) ? " https://" : " http://");document.write(unescape("%3Cspan id='cnzz_stat_icon_1000106316'%3E%3C/span%3E%3Cscript src='" + cnzz_protocol + "s22.cnzz.com/z_stat.php%3Fid%3D1000106316%26show%3Dpic' type='text/javascript'%3E%3C/script%3E"));</script>
</p>
```
##### 摘要和语法高亮
如果想让文章在首页只显示一部分，只需要在文章中相应的位置添加<!-- more -->即可，在_config.yml中修改excerpt_link: "继续阅读 &rarr;"来修改继续阅读按钮的显示内容。
octopress自带了语法高亮功能，使用的是pygements.rb，使用方法见[Backtick Code Blocks](http://octopress.org/docs/plugins/backtick-codeblock/)，支持的语言见[Supported languages](http://pygments.org/docs/lexers/)。
其他方法见[embed code from a file](http://octopress.org/docs/plugins/include-code/)、embed GitHubgists(http://octopress.org/docs/plugins/gist-tag/) 或[Octopress代码高亮](http://xiongbupt.github.io/blog/2012/06/08/octopressdai-ma-gao-liang/)。

##### 站内搜素
(留个记号)
