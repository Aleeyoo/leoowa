## 🔗 **工具简介**

* [NoteGen](https://notegen.top/) 支持将笔记同步到GitHub仓库的笔记软件。
* [TinyMind](https://github.com/mazzzystar/tinymind) 通过GitHub登录，自动创建仓库并提供在线编辑功能的博客网页。

## 📝 **配置步骤**

Gmeek-html<img src="https://raw.githubusercontent.com/Aleeyoo/note-gen-image-sync/main/a8333a4c-cc06-4550-af00-474c9aae4b8c.png">

1. 参考教程创建仓库后，按NoteGen教程设置同步仓库为"tinymind-blog"
2. 同步配置关键项：
   * 选择GitHub平台并创建Access Token（需勾选repo权限）
   * 自定义同步仓库名填写"tinymind-blog"
   * 确认仓库状态显示为"可用"

### ✍️ **写博客**

* 在content文件blog文件下新建文件，使用markdown语法，右下角同步即可上传。

### 📃 **其他页面**

* 对content文件下about.md、thoughts.json两个文件进行修改。

### 🖼️ **图片处理**

* 按官方教程设置图库后，在NoteGen中粘贴图片可自动上传至GitHub仓库。

### ⏰ **时间轴修复**

* 在文章开头添加时间戳格式：

```
----------------------------
title: NoteGen与TinyMind搭配使用指南
date: 2025-10-23T06:08:06.191Z
------------------------------
```