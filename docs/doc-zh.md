# apollo主题配置

## Meta Description

如果你想设置页面的 meta description 信息，请在每篇 markdown 文件的头部添加 `desc` 字段信息——更实用的方式是在 scaffolds 文件夹中，将 `desc` 配置到常用模板中去，示例如下：

```md
title: Lorem ipsum dolor
date: 2015-12-31 14:49:13
desc: Lorem ipsum dolor sit amet, consectetur.
---

Lorem ipsum dolor sit amet, consectetur adipisicing elit. Totam, non numquam saepe ex ut. Deleniti culpa inventore consectetur nam saepe!
```

生成结果:

```html
<meta name="description" content="Lorem ipsum dolor sit amet, consectetur.">
```

如果没有配置该信息，hexo-theme-apollo 会使用 `page.title` 和 `page.author` 来配置该标签。

## 标题

实际上，hexo-theme-apollo 只支持两种标题：`h1~h3` 大标题，`h4~h6` 小标题，也就是说，`#` 和 `###` 的样式是一样的。之所以这么处理，是因为就个人感觉而言，我们不应该为文章设置过多的层级消耗读者的阅读精力。这相当于强制使用 apollo 的用户在写文章时注意文章结构，最多只能使用两层结构。

另一个潜在的原因是因为我还没有发现好的样式来处理不同层级的标题，单纯以大小和颜色很容易让页面变得混乱和冗杂。如果你有好的建议，请告诉我:)!

## 文章摘要

如果你想创建文章摘要用于向读者展示文章的核心内容，那么需要在文章摘要之后其他内容之前添加 HTML 注释标签 `<!--more-->`，使用方法如下图所示：

![more](https://cloud.githubusercontent.com/assets/9530963/14064341/0fa3c754-f432-11e5-8ad7-5d063d4a0886.png)

## 评论插件

Hexo-theme-apollo 支持Disqus和Gitalk评论插件. 请在 `_config.apollo.yml` 文件中做如下配置:

```yaml
disqus: disqus_shortname

gitalk:
  on: true
  owner: 你的github账户名
  repo: 你要作为评论系统的repo
  admin: ['github用户名']
  clientID: 你的clientId
  clientSecret: 你的clientSecret
```

## 分类页面

需用hexo命令生成

```bash
hexo new page categories
```

修改title和type

```md
---
title: 分类
date: 2020-04-08 00:16:38
type: category
---
```

## 友链页面

hexo命令生成友链页面

```bash
hexo new page link
```

修改type

```md
---
title: link
date: 2020-04-10 21:13:44
type: link
---
```

在Hexo博客目录中的source/_data，创建一个文件link.yml

``` yml
class:
  class_name: 友情链接
  link_list:
    1:
      name: xxx
      link: https://blog.xxx.com
      avatar: https://cdn.xxxxx.top/avatar.png
      descr: xxxxxxx
    2:
      name: xxxxxx
      link: https://www.xxxxxxcn/
      avatar: https://xxxxx/avatar.png
      descr: xxxxxxx  
```

## 警告块

使用警告块需要`markdown-it-container`插件或直接写入 html 标签，支持四种等级: success, info, warning, danger

```html
<div class="warning">
    这是警告消息
</div>

# markdown-it-container 插件形式

::: danger
这是错误信息
:::
```

![message](https://pic.rmb.bdstatic.com/bjh/8bf54919b67518d88eaa07130b5fcfd7.png)

## Last but not Least

专注文章内容的创作胜过博客样式的美观，祝各位玩的开心:) !
