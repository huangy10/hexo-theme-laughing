# Laughing theme for hexo
[![Build Status](https://img.shields.io/badge/build-passing-brightgreen.svg)](https://github.com/BoizZ/hexo-theme-laughing)
[![Hexo](https://img.shields.io/badge/hexo-3.2.0+-blue.svg)](https://github.com/hexojs/hexo)
[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/BoizZ/hexo-theme-laughing/master/LICENSE)

简单轻量的[hexo](https://hexo.io)主题。

Demo: [lalala.lol](http://lalala.lol)

## 外观

响应式布局，宽松设计，还原最佳阅读体验。

![电脑界面](http://callfiles.ueibo.com/hexo-theme-laughing/pc_1200.jpg)

![手机界面](http://callfiles.ueibo.com/hexo-theme-laughing/phone_1200.jpg)

## 功能

 - 10分钟快速配置
 - 支持多说评论，自由开启评论，主题定制样式
 - 简易二次开发

## 安装

 1. 安装[hexo-render-pug](https://github.com/maxknee/hexo-render-pug)
 
 Laughing主题使用`pug`模板引擎开发，所以首先需要在主程序中安装依赖组件。

 ``` shell
 npm install hexo-renderer-pug --save
 ```

 2. 拷贝主题到`themes`目录

 ```
 cd themes
 git clone git@github.com:BoizZ/hexo-theme-laughing.git
 ```

 3. 修改主程序的`_config.yml`文件

  ``` yaml
  theme: hexo-theme-laughing
  ```

## 主题配置文档

主题的配置都放在了 `_config.yml` 文件里面。

### 网站图标

``` yaml
favicon: /favicon.ico
```

### SEO

站点标题、副标题、描述沿用站点的配置。

``` yaml
## 关键字
keywords: Hexo, Gruntjs, Nodejs, Reactjs, Vuejs
```

### 页头

菜单按钮风格目前支持两种：`dark`，`light`。

``` yaml
## 页面背景
page_background: /default_images/page_background.jpg

## 页面菜单按钮风格
page_menu_button: dark

## 文章背景
post_background: /default_images/post_background.jpg

## 文章菜单按钮风格
post_menu_button: light

## 标题占位字：无标题类型文章的标题占位字
title_plancehold: '随笔'

## 自定义菜单
navication:
  - name: Lalala.lol
    link: http://lalala.lol
```

### 作者信息

作者的名字沿用站点的配置。

``` yaml
## head：作者头像
## signature：作者签名
author:
  head: /default_images/author_head.gif
  signature: Only when you plant the flowers can you really smell their fragrance.
```

### 内容宽度

可自定义内容的最大显示宽度。

``` yaml
content_width: 600
```

### 社交信息

主题内置的社交图标目前有：`facebook`, `twitter`, `weibo`, `wechat`, `github`, `stackoverflow`, `linkin`, `email`, `segmentfault`, `flickr`, `zhihu`, `disqus`, `douban`, `bilibili`

如需新增请在Issues里面提出

``` yaml
## name：名称
## icon：图标（请使用配置文件里面给出的图标）
## link：指向当前社交账号的链接
social:
  - name: GitHub
    icon: github
    link: http://github.com/BoizZ
```

### 评论

这个主题之前默认支持的是多说平台，但是这个平台现在已经关闭了。 
现在增加了对一些其他的平台的支持。如果有需要今后会进一步扩展评论使用的范围。

#### Valine

Valine 诞生于2017年8月7日，是一款基于Leancloud的快速、简洁且高效的无后端评论系统。
你需要先去[LeanCloud](https://leancloud.cn/)上注册一个账户并创建应用。
在配置文件中需要填上[从leanCloud获取的appId和appKey](https://valine.js.org/quickstart.html)。在主题中使用Valine的方式如下：

``` yaml
comments:
  provider: valine
  apiId: '<your-app-id>'
  appKey: '<your-app-key>'
```

#### 来必力

来必力是其来自韩国的产品。其官网是[http://www.laibili.com.cn/](http://www.laibili.com.cn/)。相比于Valine，来必力的评论形式更加丰富一些，支持图片和动图。
配置模板为：

``` yaml
comments:
  provider: laibili
  uid: '<your-data-uid>'
```

其中，`uid`来自于来必力管理界面中代码管理部分提供的安装代码。例如一个一般网站的安装代码为：

```html
<!-- 来必力City版安装代码 -->
<div id="lv-container" data-id="city" data-uid="Mi8xLzM=">
<script type="text/javascript">
   (function(d, s) {
       var j, e = d.getElementsByTagName(s)[0];

       if (typeof LivereTower === 'function') { return; }

       j = d.createElement(s);
       j.src = 'https://cdn-city.livere.com/js/embed.dist.js';
       j.async = true;

       e.parentNode.insertBefore(j, e);
   })(document, 'script');
</script>
<noscript>为正常使用来必力评论功能请激活JavaScript</noscript>
</div>
<!-- City版安装代码已完成 -->
```

其中最上层`div`标签中的`data-uid`即为需要填写到配置文件中的`uid`.

### 版权

``` yaml
## record: 备案名称（若无则填写 false）
## hexo: 是否显示“POWER BY HEXO”
## laughing：是否显示“THEME BY LAUGHING”
copyright:
  record: false
  hexo: true
  laughing: true
```

## 二次开发 [![Build Status](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/BoizZ/hexo-theme-laughing/pulls)

Laughing主题遵循简易开发模式，以文件层级及命名细分模块，二次开发比较简单。

### 模板引擎

Laughing主题使用`pug`作为模板引擎，在开发前请确保已经安装了[hexo-render-pug](https://github.com/maxknee/hexo-render-pug)插件，如未安装，请在`Hexo`程序根目录运行以下命令进行安装：

```
npm install hexo-renderer-pug --save
```

### 安装Grunt

Laughing主题使用`sass`作为预编译样式语言，使用`grunt`监听文件变化并编译成css。当然，`sass`是基于`ruby`的，需要在电脑上安装`ruby`；

进入主题目录，运行以下命令安装`grunt`以及其他依赖：

```
npm install
```

### 参考

 - [GRUNT](http://gruntjs.com/)
 - [PUG](https://pugjs.org/api/getting-started.html)
 - [SASS](http://sass-lang.com/guide)
 - [RUBY](https://www.ruby-lang.org)
