# gitbook的环境配置

> ### 1.安装nodejs {#1安装nodejs}

访问nodejs的官方网站的downdolad，网址：[https://nodejs.org/en/download/](https://nodejs.org/en/download/)，可以看到最新的nodejs下载，包括不同的版本，截图如下所示。  
![](http://img.blog.csdn.net/20170329190539370?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvcXFfMjE3OTQ2MDM=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast "这里写图片描述")  
   根据[Linux](http://lib.csdn.net/base/linux)的不同版本选择32位或64位，因为我的[linux](http://lib.csdn.net/base/linux)的虚拟机是64位的，所以我选择的是64位二进制安装文件（Linux Binariesx64\),可以右键选择在新窗口中打开链接，记下这个地址。[https://nodejs.org/dist/v6.10.1/node-v6.10.1-linux-x64.tar.xz](https://nodejs.org/dist/v6.10.1/node-v6.10.1-linux-x64.tar.xz)；  
   回到linux虚拟机，在控制台输入  
`# wget https://nodejs.org/dist/v6.10.1/node-v6.10.1-linux-x64.tar.xz`  
   系统将会下载这个文件，可以选择下载到默认路径。成功下载，在命令行输入命令可以查看到文件。如下图所示。  
![](http://img.blog.csdn.net/20170329194814703?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvcXFfMjE3OTQ2MDM=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast "这里写图片描述")

根据下载的文件可以看出它的压缩方式是.xz的方式，所以不能直接使用linux命令tar直接下载。需要下载能够解压这种格式的工具。我们可以使用yum源来安装，控制台命令：

```
# yum search xz

# yum install xz.i386

# xz -d node-v6.10.1-linux-x64.tar.xz

# tar -xf node-v6.10.1-linux-x64.tar

# mv node-v6.10.1-linux-x64 node-v6.10.1
```

在控制台输入`yum search xz`,在搜索到的列表中选择安装软件，如`yum install xz.i386`，解压完成后文件变为以.tar后缀，使用`tar -xf node-v6.10.1-linux-x64.tar`解压文件。  
   可以更改文件名方便操作，在命令台输入`mv node-v6.10.1-linux-x64 node-v6.10.1`，更改文件名为node-v6.10.1。  
   为了验证是否能够使用node，我们可以输入cd node-v6.10.1/bin，输入./node -v查看node版本，安装成功则能够成功显示node版本。如下图所示。（截图中的node -v应该为./node -v，因为是后面截图的）。  
![](http://img.blog.csdn.net/20170329193059346?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvcXFfMjE3OTQ2MDM=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast "这里写图片描述")

> ### 2.配置nodejs {#2配置nodejs}

要想node能够在全局能够使用，需要添加连接，在控制台输入下面命令能够实现。其中“/root/node-v6.10.1/bin/node”为二进制nodejs文件的目录，根据上面的步骤，我这里是直接解压到了root目录下，所以路径为/root/node-v6.10.1/bin/node。

ln -s /root/node-v6.10.1/bin/node /usr/local/bin/node

ln -s /root/node-v6.10.1/bin/npm /usr/local/bin/npm

配置完成后即可在任何目录下使用node。  
![](http://img.blog.csdn.net/20170329194133691?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvcXFfMjE3OTQ2MDM=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast "这里写图片描述")

> ### 3.安装gitbook

GitBook 是一个基于 Node.js 的命令行工具，可使用 Github/Git 和 Markdown 来制作精美的电子书。通过Node.js命令安装GitBook

1、NMP安装Gitbook

> npm install gitbook -g

2、安装gitbook CLI

> 想在系统上的任何地方的gitbook命令，需要安装“gitbook CLI”，执行以下命令
>
> //安装命令  
> npm install -g gitbook-cli  
> //卸载命令  
> npm uninstall -g gitbook

3、检验下是否安装成功

> gitbook -V //显示0.4.2

# 

# 基本使用

gitbook 的基本用法非常简单，基本上就只有两步：

1. 使用 
   `gitbook init`
    初始化书籍目录
2. 使用 
   `gitbook serve`
    编译书籍

下面将结合一个非常简单的实例，来介绍 gitbook 的基本用法。

## gitbook init {#gitbook-init}

首先，创建如下目录结构：

```
$ tree book/
book/
├── README.md
└── SUMMARY.md


0
 directories, 
2
 files
```

README.md 和 SUMMARY.md 是两个必须文件，README.md 是对书籍的简单介绍：

```
$ cat book/README.md 

# README


This is a book powered by [GitBook](https://github.com/GitbookIO/gitbook).
```

SUMMARY.md 是书籍的目录结构。内容如下：

```
$ cat book/SUMMARY.md 

# SUMMARY


* [Chapter1](chapter1/README.md)
  * [Section1.
1
](chapter1/section1.
1
.md)
  * [Section1.
2
](chapter1/section1.
2
.md)
* [Chapter2](chapter2/README.md)
```

创建了这两个文件后，使用 `gitbook init`，它会为我们创建 SUMMARY.md 中的目录结构。

```
$ 
cd
 book
$ gitbook init
$ tree
.
├── README.md
├── SUMMARY.md
├── chapter1
│   ├── README.md
│   ├── section1.
1
.md
│   └── section1.
2
.md
└── chapter2
    └── README.md


2
 directories, 
6
 files
```

注意：在我的实验中，`gitbook init` 只支持**两级**目录！

## gitbook serve {#gitbook-serve}

书籍目录结构创建完成以后，就可以使用 `gitbook serve` 来编译和预览书籍了：

```
$ gitbook serve
Press CTRL+C to quit ...

Live reload server started on port: 
35729

Starting build ...
Successfully built!

Starting server ...
Serving book on http://localhost:
4000
```

`gitbook serve` 命令实际上会首先调用 `gitbook build` 编译书籍，完成以后会打开一个 web 服务器，监听在本地的 4000 端口。

现在，可以用浏览器打开 [http://127.0.0.1:4000](http://127.0.0.1:4000) 查看书籍的效果，如下图：

![](http://www.chengweiyang.cn/gitbook/assets/basic-usage/gitbook-sample.png "gitbook")

现在，gitbook 为我们创建了书籍目录结构后，就可以向其中添加真正的内容了，文件的编写使用 markdown 语法，在文件修改过程中，每一次保存文件，`gitbook serve` 都会自动重新编译，所以可以持续通过浏览器来查看最新的书籍效果！

`gitbook`build   生成图书

       `gitbook serve ` 启动服务编译书籍



> ### 4.安装git {#2配置nodejs}

```
$ yum install git
```

我们来简单的配置一下git吧:

```
#配置用户名
$ git config --global user.name Jack

#配置用户邮箱
$ git config --global user.email jack@xx.com

#配置编辑器
$ git config --global core.editor vim

#配置比较工具
$ git config --global merge.tool vimdiff

#查看配置
$ git config --list
```

1.克隆远程仓库代码到仓库

```
git clone https://github.com/yanghaize/newstore.git
```

2.更新远程最新的代码到服务器，我们可以使用如下命令从origin远程仓库获取最新版本的代码

git fetch origin master:temp

上面代码的意思是：从远程的origin仓库的master分支下载到本地master并新建一个temp分支

1. 查看temp分支与本地原有分支的不同  

git diff temp

4.将temp分支和本地的master分支合并 （注：一定要记得合并）

git merge temp

现在，B的本地代码已经和远程仓库处于同一个版本了，于是B可以开心coding了。

最后再提一下，上面的步骤中我们创建了temp分支，如果想要删除temp分支，也是可以的，

命令如下：  git branch -d temp

