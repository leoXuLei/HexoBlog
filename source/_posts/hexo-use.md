---
title: Hexo 安装使用配置
---
## 什么是 Hexo？
Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 Markdown（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。
## 快速开始
### 安装前提
  hexo基于node.js，本地需要安装node 和npm
- 安装[Git](http://git-scm.com/)
- 安装[Node.js](http://nodejs.org/)

### 全局安装Hexo
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

## 常用命令
```bash
$ hexo server // 启动
$ hexo new "My New Post"
$ hexo generate | hexo g // 生成静态文件
$ hexo deploy // 部署到远程站点 
```
## 目录
新建完成后，指定文件夹的目录如下：
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
### _config.yml
网站的配置信息，您可以在此配置大部分的参数。
### package.json
应用程序的信息。EJS, Stylus 和 Markdown renderer 已默认安装，您可以自由移除。
```json
// package.json
{
  "name": "hexo-site",
  "version": "0.0.0",
  "private": true,
  "hexo": {
    "version": ""
  },
  "dependencies": {
    "hexo": "^3.8.0",
    "hexo-generator-archive": "^0.1.5",
    "hexo-generator-category": "^0.1.3",
    "hexo-generator-index": "^0.2.1",
    "hexo-generator-tag": "^0.2.0",
    "hexo-renderer-ejs": "^0.3.1",
    "hexo-renderer-stylus": "^0.3.3",
    "hexo-renderer-marked": "^0.3.2",
    "hexo-server": "^0.3.3"
  }
}
```
### scaffolds
模版 文件夹。当您新建文章时，Hexo 会根据 scaffold 来建立文件。

Hexo的模板是指在新建的文章文件中默认填充的内容。例如，如果您修改scaffold/post.md中的Front-matter内容，那么每次新建一篇文章时都会包含这个修改。

### source
资源文件夹是存放用户资源的地方。除 _posts 文件夹之外，开头命名为 _ (下划线)的文件 / 文件夹和隐藏的文件将会被忽略。Markdown 和 HTML 文件会被解析并放到 public 文件夹，而其他文件会被拷贝过去。

### themes
主题文件夹。Hexo 会根据主题来生成静态页面。
## 主题
创建 Hexo 主题非常容易，您只要在 `themes` 文件夹内，新增一个任意名称的文件夹，并修改 _config.yml 内的 theme 设定，即可切换主题。一个主题可能会有以下的结构：
```JSON
.
├── _config.yml
├── languages
├── layout
├── scripts
└── source
```


### 目录
#### _config.yml
主题的配置文件。和 Hexo 配置文件不同，主题配置文件修改时会自动更新，无需重启 Hexo Server。
#### languages
语言文件夹。
#### layout
布局文件夹。用于存放主题的模板文件，决定了网站内容的呈现方式，Hexo 内建 Swig 模板引擎，您可以另外安装插件来获得 EJS、Haml、Jade 或 Pug 支持，Hexo 根据模板文件的扩展名来决定所使用的模板引擎，例如：
```bash
layout.ejs   - 使用 EJS
layout.swig  - 使用 Swig
```
#### scripts
脚本文件夹。在启动时，Hexo 会载入此文件夹内的 JavaScript 文件。
#### source
资源文件夹，除了模板以外的 Asset，例如 CSS、JavaScript 文件等，都应该放在这个文件夹中。文件或文件夹开头名称为 _（下划线线）或隐藏的文件会被忽略。

如果文件可以被渲染的话，会经过解析然后储存到 public 文件夹，否则会直接拷贝到 public 文件夹。
#### themes
主题文件夹。
### 参考资料
- [hexo主题](https://hexo.io/themes/)
- [Next官方文档](https://theme-next.iissnan.com/)

## 参考资料
- [Hexo官网文档](https://hexo.io/zh-cn/docs/)
- [Hexo-Next 主题博客个性化配置超详细，超全面(两万字)](https://blog.csdn.net/as480133937/article/details/100138838/)