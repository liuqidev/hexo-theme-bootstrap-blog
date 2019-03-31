# hexo-theme-bootstrap-blog

简单的基于bootstrap v3的hexo博客主题。

源自 [官方主题](http://getbootstrap.com/examples/blog/).

[演示](http://i.blankspace.cn) | [更多信息](http://i.blankspace.cn/categories/Projects/hexo-theme-bootstrap-blog/) | [中文文档](https://github.com/liuqidev/hexo-theme-bootstrap-blog/blob/master/README-zhs.md)

## 安装

0) 学习hexo，搭建自己的hexo站点,[文档](https://hexo.io/zh-cn/docs/)


1) 安装主题:

```bash
$ git clone https://github.com/liuqidev/hexo-theme-bootstrap-blog.git themes/bootstrap-blog
```

1.1) 安装相关依赖**（重要）**

进到自己的博客根目录，执行命令
```
npm install
```
注意给出的提示，例如某些库的版本过时，按照提示进行操作。


2) (可选) Install [hexo-tag-bootstrap](https://github.com/wzpan/hexo-tag-bootstrap) for more Bootstrap tags (textcolors, buttons, labels, badges, etc.):

```bash
$ npm install hexo-tag-bootstrap --save
```

3) (可选) Install [hexo-tag-fontawesome](https://github.com/akarzim/hexo-tag-fontawesome) for placing Font Awesome icons in your Markdown:

```bash
$ npm install hexo-tag-fontawesome --save
```

4. (可选) 使用LaTeX：

Go to your hexo blog root, cd to `node_modules\kramed\lib\rules\inline.js `, edit line11:

```bash
//  escape: /^\\([\\`*{}\[\]()#$+\-.!_>])/,
  escape: /^\\([`*\[\]()#$+\-.!_>])/
```
编辑第 20/21行:

```bash
//  em: /^\b_((?:__|[\s\S])+?)_\b|^\*((?:\*\*|[\s\S])+?)\*(?!\*)/,
  em: /^\*((?:\*\*|[\s\S])+?)\*(?!\*)/
```


```
# MathJax Support
mathjax:
  enable: true
```



### 生效

Modify the `theme` setting in `_config.yml` to `bootstrap-blog`.

### 更新

```bash
cd themes/bootstrap-blog
git pull
```

## 可选配置

```yml
# File: themes/bootstrap-blog/_config.yml
# Header
navbar_brand: false
menu:
  Home: index.html
  Archives: archives/
  Categories: categories/
  # Projects: projects/
  About: about/
  # Blogroll: blogroll/
 
rss: /atom.xml

# Content
excerpt_link: Read more...
fancybox: true
wordcount: true
viewcount: true
timecost: false
language: zh-CN

# Sidebar
widgets:
- translate
- recent_posts
- about         # See also: `about_content`
- category
- archive
- search
#- tag
#- tagcloud
about_widget_content: >
  <p>Etiam porta <em>sem malesuada magna</em> mollis euismod.
  Cras mattis consectetur purus sit amet fermentum. Aenean
  lacinia bibendum nulla sed consectetur.</p>
# widget behavior
archive_type: 'monthly'

# Miscellaneous
google_analytics: UA-122713769-1
favicon: images/icon.png
twitter_id:
google_plus: your google plus ID
fb_admins:
fb_app_id:
# baidu analytics
baidu_tongji: true

# https://github.com/hustcc/canvas-nest.js
canvas_nest: false

# https://github.com/imsun/gitment
# https://coding.net/  can be deployed to coding
# gitment: false
gitment:
  owner: liuqidev
  repo: liuqidev.github.io
  client_id: 
  client_secret: 
 
# Valine Comment system. https://valine.js.org
valine: false
# valine:
  # enable: true # Use valine，set true
  # appId:  # your leancloud appId
  # appKey:  # your leancloud appKey
  # notify: false # Mail notify
  # verify: false # Verify code
  # avatar: mm # Gravatar style : mm/identicon/monsterid/wavatar/retro/hide
  # placeholder: Say something~ # Comment Box placeholder
  # guest_info: nick,mail # Comment header info
  # pageSize: 20 # comment list page size

# livere https://livere.com/
livere: false
# livere:
  # dataUID: #your dataID
 
# http://www.daovoice.io
dao_voice: false
# dao_voice:
  # appId: a2c8df52
  
eyes_protected: false

# dynamic_title
# title_change: false
title_change:
  normal: o(∩_∩)o Welcome!
  leave: Opps...●﹏●

```

- **navbar_brand** - The HTML content for an optional ["navbar-brand"](http://getbootstrap.com/components/#navbar-brand-image). Can be text or an image. `false` to hide.
- **menu** - Navigation menu (map of Titles to URLs)
- **rss** - RSS link (ie. "/atom.xml")
- **excerpt_link** - "Read More" link at the bottom of excerpted articles. `false` to hide the link.
- **fancybox** - Enable [Fancybox] for images
- **widgets** - Enable sidebar widgets ([more info below](#sidebar))
- **about_widget_content** - The HTML content for the "About" sidebar widget ([more info below](#sidebar))
- **google_analytics** - Google Analytics ID
- **favicon** - Favicon path (ie. '/favicon.ico')
- **twitter_id** - Twitter ID of the author (ie. `@c_g_martin`)
- **google_plus** - Google+ profile link

Instead of editing the layout's configuration file directly, you can override the theme settings from your project's root `_config.yml`, ie.:
```yml
theme_config:
  # Header
  navbar_brand: <img src="/navbrand.png">
  menu:
    Home: index.html
    Archives: archives/
    'Another Page': page/index.html
  widgets:
   - about
   - category
   - archive
   - recent_posts
   - tag
  about_widget_content: >
    <p>This is <strong>custom content</strong> for the
    "about" sidebar widget.</p>
```

## 新特性

- toc: table of contents, show the toc of an article besides.
- top: enable an article stick 
- wordcount

- viewcount
- timecost
- baidu_tongji
- canvas_nest
- comment systems:
  - gitment: https://github.com/imsun/gitment
  - valine: https://valine.js.org
  - livere: https://livere.com/
  - dao_voice: http://www.daovoice.io
- dynamic_title


## 原来特性

### Front-Matter Extras

Optional settings in the front-matter can be added for various effects:
```yml
---
author: Author Name   # displays the post's author
photos:               # displays a Bootstrap thumbnail gallery
- images/HNCK0537.jpg
- images/HNCK6173.jpg
---
```

### Fancybox

This theme uses [Fancybox] to showcase your photos. You can use the image Markdown syntax or fancybox tag plugin to add your photos.

Usage:
```
![img caption](img url)


```

### Callouts

A custom tag for the [Bootstrap "callout" style](http://cpratt.co/twitter-bootstrap-callout-css-styles/) is available for use.



### Sidebar

This theme provides 6 built-in widgets that can be displayed in the sidebar:

- [about](./layout/_widget/about.ejs) \*
- [category](./layout/_widget/category.ejs)
- [tag](./layout/_widget/tag.ejs)
- [tagcloud](./layout/_widget/tagcloud.ejs)
- [archives](./layout/_widget/archives.ejs)
- [recent_posts](./layout/_widget/recent_posts.ejs)

All widgets are enabled and displayed by default. You can toggle them on/off with the `widgets` setting in the theme's [_config.yml](./config.yml).

\* **NOTE**: The "about" widget contains static Lorem Ipsum text by default. You'll want to edit the `about_widget_content` setting for your site or disable the widget in the [theme config](./config.yml). You can also modify the widget file itself to include contents from a Markdown page:
```html
<!-- file: ./layout/_widget/about.ejs -->
<div class="sidebar-module sidebar-module-inset">
  <h4>About</h4>
  <%- site.pages['data'].find(function(p) { return p.path === 'about/index.html'; }).content %>
</div>
```
...then run `hexo new page about` to create the Markdown page.

### Bootstrap Paginator Helper

A custom `bs_paginator()` helper is used to produce [Bootstrap-compatible pagination markup](http://getbootstrap.com/components/#pagination). It is a drop-in replacement for Hexo's built-in `paginator()`.

```
<%- bs_paginator({
      prev_text: '<i class="fa fa-chevron-left"></i> Prev',
      next_text: 'Next <i class="fa fa-chevron-right"></i>'
    }) %>
```

## Development

The [default Landscape Hexo theme](https://github.com/hexojs/hexo-theme-landscape) was used as the starting point and heavily edited for this theme.

The Landscape Stylus styles have been replaced with standard CSS files which override `bootstrap.min.css`. Stylus is used only for [bundling the CSS files](./source/css/styles.styl). Feel free to convert the CSS to your pre-processor of choice (Stylus, LESS, Sass, etc.).

## 证书

[MIT License](http://cgm.mit-license.org/)

Copyright © 2016 [@liuqidev](https://github.com/liuqidev)

[Hexo]: http://zespia.tw/hexo/
[Fancybox]: http://fancyapps.com/fancybox/
[Font Awesome]: http://fontawesome.io/
[Bootstrap]: http://getbootstrap.com/

