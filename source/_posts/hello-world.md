---
title: 大锤的第一篇博客
date: 2020-04-01
tags:
- 开始
- Icarus用户指南
# categories:
# - 用户 
cover: /covers/vector_landscape_1.svg
thumbnail: /covers/vector_landscape_1.svg
---
这是我的第一篇博客，基于Hexo搭建的，使用github托管部署，此前我对于markdown语法还不太熟悉，接下来我会发布一些对于我个人而言有帮助的解决问题的经验分享。
<!-- more -->
{% tabs align:left style:boxed %}
<!-- tab id:install-source 'icon:fas fa-file-code' 'title:通过源码安装' -->
从GitHub下载源代码，并复制到Hexo站点的theme目录
或者，使用Git将Icarus仓库克隆到`themes`目录：

{% codeblock "Git Bash/Shell" %}
git clone https://github.com/ppoffice/hexo-theme-icarus.git themes/icarus -b <version number> --depth 1
{% endcodeblock %}

可以省略`-b <version number>`直接获取Icarus主题的最新版本。
去掉`--depth 1`可以下载Icarus主题完整的历史提交记录。
此外，可以使用以下命令将Icarus安装为Git子模块：

{% codeblock "Git Bash/Shell" %}
git submodule add https://github.com/ppoffice/hexo-theme-icarus.git themes/icarus
{% endcodeblock %}
<!-- endtab -->

<!-- tab active id:install-npm 'icon:fas fa-cubes' 'title:使用NPM安装' -->
通过NPM安装，在项目根目录运行：

{% codeblock "Shell" %}
npm install -S hexo-theme-icarus hexo-renderer-inferno
{% endcodeblock %}
<!-- endtab -->
{% endtabs %}

<hr>

修改项目根目录的`_config.yml`文件设置主题：

{% codeblock _config.yml lang:yaml %}
theme: icarus
{% endcodeblock %}

或者使用`hexo`命令设置主题：

{% codeblock "Shell" %}
hexo config theme icarus
{% endcodeblock %}

最后，运行预览！

{% codeblock "Shell" %}
hexo server
{% endcodeblock %}

要了解有关主题、小部件和插件的更多信息，请查看 [Icarus 用户指南](/hexo-theme-icarus/tags/Icarus-User-Guide/)。
您也可以参考此站点的源代码以获取更多示例。它在GitHub中Icarus仓库的[`site` 分支](https://github.com/ppoffice/hexo-theme-icarus/tree/site)。
另外, 您可以在这里找到其他Icarus用户的帮助 [GitHub Discussions](https://github.com/ppoffice/hexo-theme-icarus/discussions)。

**其他资源**
下面一些资源，可能会使你发现这些资源对进一步自定义站点很有用.
您也可以通过以下方式提交Icarus教程 [链接地址](https://github.com/ppoffice/hexo-theme-icarus/edit/site/source/_posts/en/Getting-Started.md).

<div class="menu-list is-size-6">
<a href="https://hexo.io/docs/index.html"><i class="fas fa-bookmark mr-2"></i> Hexo 文档地址</a>
</div>
<br>
<article class="message message-immersive is-warning">
<div class="message-body">
<i class="fas fa-question-circle mr-2"></i>关于ICARUS的更多使用文档 
点击这里 <a href="https://github.com/ppoffice/hexo-theme-icarus/blob/site/source/_posts/zh-CN/Getting-Started.md"></a> 
</div>
</article>