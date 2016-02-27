---
layout: post
title: "Octopress中多说终于搞定了"
date: 2016-02-28 00:24:14 +0800
comments: true
categories: 建站
author: 无痕
---
>搞了很多遍，终于搞定了给Optopress添加多说功能，很赞。




![特此祝贺](http://cepos.img47.wal8.com/img47/537802_20160227224327/145659192877.jpg
)

[在此，要感谢这篇文章，][1] 希望链接不要失效。
按照这篇文章做，基本上能实现增加多说功能，但也需要补充，在这里一并说明：

 - **保持默认主题** ：这篇文章是按照Optopress安装时默认主题下进行多少功能的添加的，目录结构能对得上。如果安装了其他主题，不能保证目录结构有序，可能造成多说无法运行，那就很悲催了。
 - **补充代码** ： 需要补充如下代码：
 在_config.yml中添加开关：

  ```
    # comment and share
    comment_share: true
  ```
  然后，在source/\_includes/post/sharing.html中添加如下代码：

  ```
    {% if site.comment_share %}
    {% include post/duoshuo.html %}
    {% endif %}
  ```





[1]: http://havee.me/internet/2013-02/add-duoshuo-commemt-system-into-octopress.html
