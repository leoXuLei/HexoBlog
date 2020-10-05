---
title: Hexo 安装配置使用
---

## 什么是 Hexo？

Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 Markdown（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。

## 快速开始

### 安装前提

hexo 基于 node.js，本地需要安装 node 和 npm

- 安装[Git](http://git-scm.com/)
- 安装[Node.js](http://nodejs.org/)

### 全局安装 hexo-cli

```bash
$ npm install -g hexo-cli
```

### 新建项目

安装 Hexo 完成后，请执行下列命令，Hexo 将会在指定文件夹中新建所需要的文件。

```bash
$ hexo init <folder> // 初始化项目
$ cd <folder>
$ npm install // 安装依赖
```

### 目录

新建完成后，指定文件夹的 [目录](https://hexo.io/zh-cn/docs/setup) 如下：

```JSON
.
├── _config.yml
├── package.json
├── scaffolds
├── source
|   ├── _drafts
|   └── _posts
└── themes
```

目录组成

<!-- | 文件/夹 | 描述 |
| :-- | :-- |
| `_config.yml` | 网站的配置信息，您可以在此配置大部分的参数。 |
| `package.json` | 应用程序的信息。EJS, Stylus 和 Markdown renderer 已默认安装，您可以自由移除。 |
| `scaffolds：` | 模版文件夹。当您新建文章时，Hexo 会根据 scaffold 来建立文件。Hexo的模板是指在新建的文章文件中默认填充的内容。例如，如果您修改scaffold/post.md中的Front-matter内容，那么每次新建一篇文章时都会包含这个修改。 |
| `source` | 资源文件夹是存放用户资源的地方。除 _posts 文件夹之外，开头命名为 _ (下划线)的文件 / 文件夹和隐藏的文件将会被忽略。Markdown 和 HTML 文件会被解析并放到 public 文件夹，而其他文件会被拷贝过去。 |
| `themes` | 主题文件夹。Hexo 会根据主题来生成静态页面。 | -->

- `_config.yml`

  网站的配置信息，您可以在此配置大部分的参数。

- `package.json`

  应用程序的信息。EJS, Stylus 和 Markdown renderer 已默认安装，您可以自由移除。

- `scaffolds：`

  模版文件夹。当您新建文章时，Hexo 会根据 scaffold 来建立文件。Hexo 的模板是指在新建的文章文件中默认填充的内容。例如，如果您修改 scaffold/post.md 中的 Front-matter 内容，那么每次新建一篇文章时都会包含这个修改。

- `source`

  资源文件夹是存放用户资源的地方。除 _posts 文件夹之外，开头命名为 _ (下划线)的文件 / 文件夹和隐藏的文件将会被忽略。Markdown 和 HTML 文件会被解析并放到 public 文件夹，而其他文件会被拷贝过去。

- `themes`

  主题文件夹。Hexo 会根据主题来生成静态页面。

## 常用命令

```bash
$ hexo server // 启动
$ hexo new "My New Post"
$ hexo generate | hexo g // 生成静态文件
$ hexo deploy // 部署到远程站点
```

## 配置文件

在 Hexo 中有两份主要的配置文件，其名称都是 \_config.yml。 其中，

- 一份位于站点根目录下，主要包含 [Hexo 本身的配置](https://hexo.io/zh-cn/docs/configuration)；
- 另一份位于主题目录下，这份配置由主题作者提供，主要用于配置主题相关的选项。

为了描述方便，在以下说明中，将前者称为 `站点配置文件`， 后者称为 `主题配置文件`。

```js
站点配置文件: /hexo/_cfgino.yml

主题配置文件: /hexo/eehmst / next / _config.yml
```

## 主题

创建 [Hexo 主题](https://hexo.io/zh-cn/docs/themes) 非常容易，您只要在 `themes` 文件夹内，新增一个任意名称的文件夹，并修改 \_config.yml 内的 theme 设定，即可切换主题。一个主题可能会有以下的结构：

```JSON
.
├── _config.yml
├── languages
├── layout
├── scripts
└── source
```

### 目录

- `_config.yml`

  主题的配置文件。和 Hexo 配置文件不同，主题配置文件修改时会自动更新，无需重启 Hexo Server。

- `languages`

  语言文件夹。

- `layout`

  布局文件夹。用于存放主题的模板文件，决定了网站内容的呈现方式，Hexo 内建 Swig 模板引擎，您可以另外安装插件来获得 EJS、Haml、Jade 或 Pug 支持，Hexo 根据模板文件的扩展名来决定所使用的模板引擎，例如：

  ```bash
  layout.ejs   - 使用 EJS
  layout.swig  - 使用 Swig
  ```

- `scripts`

  脚本文件夹。在启动时，Hexo 会载入此文件夹内的 JavaScript 文件。

- `source`

  资源文件夹，除了模板以外的 Asset，例如 CSS、JavaScript 文件等，都应该放在这个文件夹中。文件或文件夹开头名称为 \_（下划线线）或隐藏的文件会被忽略。

  如果文件可以被渲染的话，会经过解析然后储存到 public 文件夹，否则会直接拷贝到 public 文件夹。

### 下载主题

```js
$ git clone https://github.com/theme-next/hexo-theme-next themes/next
```

### 启用主题

与所有 Hexo 主题启用的模式一样。 当 克隆/下载 完成后，打开 站点配置文件， 找到 theme 字段，并将其值更改为 next

```bash
theme: next
```

### 新建标签及分类界面

打开 `主题配置文件`，搜索 menu，把 tags 和 categories 前面的 `#` 删除，如下：

```bash
menu:
  home: / || fa fa-home
  tags: /tags/ || fa fa-tags
  categories: /categories/ || fa fa-th
  archives: /archives/ || fa fa-archive
  about: /about/ || fa fa-user
  #schedule: /schedule/ || fa fa-calendar
  #sitemap: /sitemap.xml || fa fa-sitemap
  #commonweal: /404/ || fa fa-heartbeat
```

### 切换主题样式

next 主题自带四种样式。在 `主题配置文件` 中查找：scheme，如下：

```bash
# Schemes
#scheme: Muse
#scheme: Mist
#scheme: Pisces
scheme: Gemini
# 选择你喜欢的一种样式，去掉前面的 #，其他主题前加上 # 即可。
```

### 浏览页面显示当前浏览进度

打开 `主题配置文件`，搜索 scrollpercent 字段，把 false 改为 true。

### Local Search 本地搜索

安装插件 `hexo-generator-searchdb`

```bash
npm install hexo-generator-searchdb --save
```

编辑 `站点配置文件`，新增以下内容到任意位置：

```bash
search:
  path: search.xml
  field: post
  format: html
  limit: 10000
```

编辑 `主题配置文件`，启用本地搜索功能：

```bash
local_search:
  enable: true
```

### 文章分享功能

编辑 `主题配置文件`，搜索关键字 needmoreshare2 修改为下面设置：

```
...
```

### 字数统计及阅读时长

安装插件 `hexo-wordcount`

```bash
npm install hexo-symbols-count-time --save
```

编辑 `主题配置文件`，编辑如下：

```bash
symbols_count_time:
  separated_meta: true  # false会显示一行
  item_text_post: true  # 显示属性名称,设为false后只显示图标和统计数字,不显示属性的文字
  item_text_total: true # 底部footer是否显示字数统计属性文字
  awl: 4                # 计算字数的一个设置,没设置过
  wpm: 275              # 一分钟阅读的字数
```

编辑 `站点配置文件`，编辑如下：

```bash
symbols_count_time:
 #文章内是否显示
  symbols: true
  time: true
 # 网页底部是否显示
  total_symbols: true
  total_time: true
```

## 参考

- [Hexo 官网文档](https://hexo.io/zh-cn/docs/)
- [hexo 主题](https://hexo.io/themes/)
- [Next 官方文档](https://theme-next.iissnan.com/)
- [Hexo-Next 主题博客个性化配置超详细，超全面(两万字)](https://blog.csdn.net/as480133937/article/details/100138838/)
- [Hexo Next 主题配置](https://www.jianshu.com/p/4b54b1b350c6)
