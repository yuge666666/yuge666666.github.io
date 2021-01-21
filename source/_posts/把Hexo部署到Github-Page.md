---
layout: 把hexo部署到github page
title: 把Hexo部署到Github Page
date: 2021-01-21 17:18:44
tags:
---

# 使用Hexo搭建博客系统部署到Github

### 1.Hexo

官网地址：https://hexo.io/zh-cn/

快速、简洁且高效的博客框架

### 2.安装Git，Node.js

### 3.安装Hexo

```
npm install -g hexo-cli
hexo init <folder>
cd <folder>
npm install
```

### 4.修改配置 `_config.yml`

官网有详细说明，这里我就不列举了

### 5.本地启动服务

`hexo g`  生成静态文件

`hexo s ` 启动服务，默认端口： 4000

### 6.选取主题

官网主题地址：https://hexo.io/themes/

进到主题内有详细的git仓库地址，有安装说明，基本就是把git仓库下载到本地 `themes/` 目录下。

修改_config.yml里的theme为新建主题目录的名字

```
hexo clean
hexo g
hexo s
```

之后刷新页面看下效果

### 7.添加文章

hexo new "your-post-name"

如果想在本地存放图片等信息需要在_config.yml修改

post_asset_folder: true

开启这个配置当新建文件时会在本地创建两个文件，一个是存Markdown文档的，一个储存图片和音频的

### 8.部署到Github

首先到Github创建一个公开的项目，名字为你的`账号名.github.io` 

此处一定要设置为账号名为前缀的域名，不然后续会有一些坑，导致你的页面显示不了JS

### 9.在设置中配置 Github Pages 选择分支

### 10.在本地配置链接Github

安装  `npm install hexo-deployer-git --save`

配置_config.yml

```bash
deploy:
  type: git
  repo: 你的git地址
  branch: 分支
```

hexo g

hexo d

出现INFO Deploy done: git则大功告成，可以去GitHub上访问看看在线网站

参考文章地址：https://www.jianshu.com/p/282717c8da6c