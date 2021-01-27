# GitBook的使用说明

### 1.GitBook的介绍

在我认识`GitBook` 之前，我已经在使用`Git`了，毋容置疑，`Git` 是目前世界上最先进的分布式版本控制系统。

我认为 `Git`不仅是程序员管理代码的工具，它的分布式协作方式同样适用于很多场合，其中一个就是写作（这会是一个引起社会变革的伟大的工具！）。所以在我发现 `GitBook` 之前，实际上我已经无数次想象过它的使用场景了。

咋一看 `GitBook`的名字，你可能会认为它是关于 `Git` 的一本书。而当你有所了解之后，你也许会认为它是一个使用 `Git` 构建电子书的工具。其实不然，```GitBook`` 与`Git`的关系，就像雷锋塔和雷锋那样，没有一点关系！

实际上，`GitBook` 是一个基于 `Node.js`的命令行工具，支持 `Markdown` 和 `AsciiDoc` 两种语法格式，可以输出 `HTML、PDF、eBook` 等格式的电子书。所以我更喜欢把 `GitBook` 定义为文档格式转换工具。 所以，GitBook 不是 Markdown 编辑工具，也不是 `Git` 版本管理工具。市面上我们可以找到很多 `Markdown` 编辑器，比如 `Typora、MacDown、Bear、MarkdownPad、MarkdownX、JetBrains’s IDE`（需要安装插件）、`Atom`、`简书`、`CSDN` 以及 `GitBook` 自家的 `GitBook Editor` 等等。

**但 GitBook 又与 Markdown 和 Git 息息相关**，因为只有将它们结合起来使用，才能将它们的威力发挥到极致！因此，通常我们会选择合适的 Markdown 编辑工具以获得飞一般的写作体验；使用 `GitBook` 管理文档，预览、制作电子书；同时通过 `Git` 管理书籍内容的变更，并将其托管到云端（比如 `GitHub、GitLab`、码云，或者是自己搭建的 `Git` 服务器），实现多人协作。

实际上，GitBook Editor 对于新手来说是个不错的选择，它集成了 `GitBook、Git、Markdown` 等功能，还支持将书籍同步到 `gitbook.com` 网站，使我们可以很方便地编辑和管理书籍。但是不幸的是，GitBook Editor\` 的注册和登录需要翻墙，即便注册成功了也可能登录不上，似乎是因为网站最近在升级

因此，我推荐，也是我目前使用的搭配是 `GitBook + Typora + Git`。

### 2.为什么推荐`GitBook + Typora + Git`

通常，我们最开始学习和使用的办公软件就是 `Word、Excel` 和 `PowerPoint`。这里不是说它们已经过时了，不是说 `GitBook` 能够替代它们。

相反，`Microsoft` 的办公软件很优秀并且经受了时间的考验，但是正因为它功能丰富，导致稍显臃肿（**二八定律：80%的时间里我们只会只用20%的功能**），同时因为它存在以二进制格式保存、软件不兼容、格式不兼容、难以进行版本控制、难以实时分享预览、难以多人协作等短板。而这恰恰是 `GitBook + Markdown + Git` 的长处。

简单来说，`GitBook + Markdown + Git` 带来的好处有：

> * 语法简单
> * 兼容性强
> * 导出方便
> * 专注内容
> * 团队协作

当然，`GitBook` 不是万能的，当我们需要复杂排版时，依然需要依托于 `Word` 等工具。但不用担心，因为我们可以把 `Markdown` 格式的文档导出为 `Word` 格式，再进一步加工。

### 3.怎么安装 `GitBook`

## GitBook安装

下面介绍在本地如何安装 `GitBook`，如果不需要本地调试 `&` 不需要获得生成的 `html` 文件，可以直接使用 [官网](https://www.gitbook.com/) 提供的服务。

#### 3.1 环境要求

* `NodeJS`\(v4.0.0及以上\)

#### 3.2通过NPM安装

运行下面的命令进行安装

```bash
npm install gitbook-cli -g
```

其中`gitbook-cli`是gitbook的一个命令行工具, 通过它可以在电脑上安装和管理gitbook的多个版本.

#### 3.3 编辑书籍

gitbook 官方已经提供了一个本地的[编辑器](https://www.gitbook.com/editor/osx), 使用它可以方便的编写书籍\(不需要手动的写SUMMARY.md\), 并且支持windows、mac、linux 三种平台, 所以强烈建议使用编辑器编写书籍.

#### 3.4预览书籍

使用下列命令会运行一个服务器, 通过`http://localhost:4000/`可以预览书籍

```bash
gitbook serve
```

运行该命令后会在书籍的文件夹中生成一个 `_book` 文件夹, 里面的内容即为生成的 html 文件. 我们可以使用下面命令来生成网页而不开启服务器

```bash
gitbook build
```

### 4 常用的命令

#### 4.1 命令

这里主要介绍一下 `GitBook` 的命令行工具 `gitbook-cli` 的一些命令, 首先说明两点:

* `gitbook-cli` 和 `gitbook` 是两个软件
* `gitbook-cli` 会将下载的 `gitbook` 的不同版本放到 `~/.gitbook`中, 可以通过设置`GITBOOK_DIR`环境变量来指定另外的文件夹

**列出gitbook所有的命令**

```bash
gitbook help
```

**输出`gitbook-cli`的帮助信息**

```bash
gitbook --help
```

**生成静态网页**

```bash
gitbook build
```

**生成静态网页并运行服务器**

```bash
gitbook serve
```

**生成时指定gitbook的版本, 本地没有会先下载**

```bash
gitbook build --gitbook=2.0.1
```

**列出本地所有的gitbook版本**

```bash
gitbook ls
```

**列出远程可用的gitbook版本**

```bash
gitbook ls-remote
```

**安装对应的gitbook版本**

```bash
gitbook fetch 标签/版本号
```

**更新到gitbook的最新版本**

```bash
gitbook update
```

**卸载对应的gitbook版本**

```bash
gitbook uninstall 2.0.1
```

**指定log的级别**

```bash
gitbook build --log=debug
```

**输出错误信息**

```bash
gitbook builid --debug
```

### 5.目录结构

#### 5.1 目录结构

`GitBook` 基本的目录结构如下所示

```text
.
├── book.json
├── README.md
├── SUMMARY.md
├── chapter-1/
|   ├── README.md
|   └── something.md
└── chapter-2/
    ├── README.md
    └── something.md
```

这里主要讲下 GitBook 预定义的几个文件的作用

#### 5.1 `book.json`

存放配置信息，在下一章中所讲的配置信息都是在这个文件里定义的，关于该文件的配置可以看 [配置](settings.md) 这个章节。

#### 5.3 Summary

概要文件主要存放 `GitBook` 的文件目录信息，左侧的目录就是根据这个文件来生成的，默认对应的文件是 `SUMMARY.md`，可以在 `book.json` 重新定义该文件的对应值。它通过 Markdown 中的列表语法来表示文件的父子关系，下面是一个简单的示例：

```text
# Summary
* [Introduction](README.md)
* [Part I](part1/README.md)
    * [Writing is nice](part1/writing.md)
    * [GitBook is nice](part1/gitbook.md)
* [Part II](part2/README.md)
    * [We love feedback](part2/feedback_please.md)
    * [Better tools for authors](part2/better_tools.md)
```

我们通过使用 标题 或者 水平分割线 标志将 `GitBook` 分为几个不同的部分

```text
​```swift
# Summary

### Part I

* [Introduction](README.md)
* [Writing is nice](part1/writing.md)
* [GitBook is nice](part1/gitbook.md)

### Part II

* [We love feedback](part2/feedback_please.md)
* [Better tools for authors](part2/better_tools.md)

----

* [Last part without title](part3/title.md)
​
```

```text
##### 5.4 `Glossary`

词汇表文件，默认对应的文件是 `GLOSSARY.md`。该文件主要存储词汇信息，如果在其他页面中出现了该文件中的词汇，鼠标放到词汇上会给出词汇示意，可以将鼠标移到下面两个词汇上看下效果。

Git &nbsp;&nbsp; Markdown

Glossary 文件的格式如下所示：
```markdown
## Git
分散式版本控制软件

## Markdown
Aaron Swartz 跟John Gruber共同设计的排版语言
```

