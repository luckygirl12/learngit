# Git 入门

![Git](assets/logo@2x.png)

## git简介

### 为什么学习git

- 企业需求
  - 开源免费
  - **版本管理**
  - **多人协作**

### git的诞生

​	git作者：林纳斯·本纳第克特·托瓦兹

![](assets\5882b2b7d0a20cf4f664615276094b36adaf9943.jpg)

> - 1991年Linus创建了linux
> - 2002年以前, linus手动合并志愿者代码
> - 为什么不把代码放到已有的版本控制系统里：
> - - 免费的：控制权在别人手里
>   - 收费的：与开源精神不符
> - 2002年，BitMover公司的BitKeeper出于人道主义精神，授权Linux社区免费使用这个版本控制系统
> - 2005年，开发Samba的Andrew试图破解BitKeeper的协议被发现了，收回Linux社区的免费使用权
> - Linus花了两周时间自己用C写了一个分布式版本控制系统，这就是Git！
> - 2008年，GitHub网站上线了，它为开源项目免费提供Git存储

### git是什么

> Git是目前世界上最先进的分布式版本控制系统（没有之一）。

#### 什么是版本控制系统

如果你用Microsoft Word写过长篇大论，那你一定有这样的经历：

想删除一个段落，又怕将来想恢复找不回来怎么办？有办法，先把当前文件“另存为……”一个新的Word文件，再接着改，改到一定程度，再“另存为……”一个新文件，这样一直改下去，最后你的Word文档变成了这样：

![lots-of-docs](assets/0.jpeg)

过了一周，你想找回被删除的文字，但是已经记不清删除前保存在哪个文件里了，只好一个一个文件去找，真麻烦。

看着一堆乱七八糟的文件，想保留最新的一个，然后把其他的删掉，又怕哪天会用上，还不敢删，真郁闷。

更要命的是，有些部分需要你的财务同事帮助填写，于是你把文件Copy到U盘里给她（也可能通过Email发送一份给她），然后，你继续修改Word文件。一天后，同事再把Word文件传给你，此时，你必须想想，发给她之后到你收到她的文件期间，你作了哪些改动，得把你的改动和她的部分合并，真困难。

于是你想，如果有一个软件，不但能自动帮我记录每次文件的改动，还可以让同事协作编辑，这样就不用自己管理一堆类似的文件了，也不需要把文件传来传去。如果想查看某次改动，只需要在软件里瞄一眼就可以，岂不是很方便？

这个软件用起来就应该像这个样子，能记录每次文件的改动：

| 版本 | 文件名      | 用户 | 说明                   | 日期       |
| :--- | :---------- | :--- | :--------------------- | :--------- |
| 1    | service.doc | 张三 | 删除了软件服务条款5    | 7/12 10:38 |
| 2    | service.doc | 张三 | 增加了License人数限制  | 7/12 18:09 |
| 3    | service.doc | 李四 | 财务部门调整了合同金额 | 7/13 9:51  |
| 4    | service.doc | 张三 | 延长了免费升级周期     | 7/14 15:17 |

#### 集中式vs分布式

> Linus一直痛恨的CVS及SVN都是集中式的版本控制系统，而Git是分布式版本控制系统，集中式和分布式版本控制系统有什么区别呢？

##### 集中式

先说集中式版本控制系统，版本库是集中存放在中央服务器的，而干活的时候，用的都是自己的电脑，所以要先从中央服务器取得最新的版本，然后开始干活，干完活了，再把自己的活推送给中央服务器。

![central-repo](assets/0-20190526233947050.jpeg)

![éä¸­åççæ¬æ§å¶å¾è§£](assets/centralized.png)

集中式版本管理的代表：

- SVN

##### 分布式

分布式版本控制系统根本没有“中央服务器”，每个人的电脑上都是一个完整的版本库，这样，你工作的时候，就不需要联网了，因为版本库就在你自己的电脑上。既然每个人电脑上都有一个完整的版本库，那多个人如何协作呢？比方说你在自己电脑上改了文件A，你的同事也在他的电脑上改了文件A，这时，你们俩之间只需把各自的修改推送给对方，就可以互相看到对方的修改了。

在实际使用分布式版本控制系统的时候，其实很少在两人之间的电脑上推送版本库的修改，分布式版本控制系统通常也有一台充当“中央服务器”的电脑，但这个服务器的作用仅仅是用来方便“交换”大家的修改，没有它大家也一样干活，只是交换修改不方便而已。

![distributed-repo](assets/0-20190526234018814.jpeg)

![åå¸å¼çæ¬æ§å¶å¾è§£](assets/distributed.png)

分布式版本管理的代表：

- git

### 资源连接

- [Git 官网](https://git-scm.com/)
- [官方文档](<https://git-scm.com/docs>)
- [GitHub Cheat Sheet](https://github.github.com/training-kit/downloads/github-git-cheat-sheet.pdf)
- [Visual Git Cheat Sheet](http://ndpsoftware.com/git-cheatsheet.html)
- [一个国人写的Git 教程](https://www.liaoxuefeng.com/wiki/896043488029600)
- **[Pro Git](https://git-scm.com/book/zh/v2)**
- [猴子都能懂得 GIT 入门](<https://backlog.com/git-tutorial/cn/>)
- [git 简明指南](<https://rogerdudler.github.io/git-guide/index.zh.html>)

## git使用

### 安装 Git

- 下载地址：https://git-scm.com/downloads
- 支持的平台
  - Linux
  - macOS
  - Windows

在命令行中输入以下命令查看 Git 是否安装成功。

```bash
$ git --version

git version 2.21.0.windows.1
```

> 注：`$` 表示命令提示符，不需要输入它

### Git 的使用方式

- 命令行(建议)
  - cmd
  - powershell
  - terminal
  - iterm2
  - bash
  - 。。。
- 图形软件
  - windows上的TortoiseGit
  - Mac上的SourceTree

### 使用 Git Bash

> 在 Windows 上推荐使用安装 Git 自带的 Git Bash，因为 Git Bash 中可以运行一些 Linux 命令，比 Windows 的操作命令更为强大和易用。尤其是当你涉及到一些 Linux 服务器操作时，掌握这些 Linux 命令是有很大的益处的。



打开方式：

- 在开始目录中找到 `Git Bash`
- 在目录（或者目录空白）位置右键，选择 `Git Bash Here`



### git-bash中常用文件操作命令

```bash
# change directory
# cd 目录路径
$ cd

# print working directory
$ pwd

# list
# ls -a 包括隐藏文件|目录
$ ls

# make directory
# mkdir 目录路径
$ mkdir

# 新建文件
$ touch 文件路径

# remove
# rm 文件路径
# “- f ”忽略不存在的文件，强制删除，不给出提示。 
# “- r” 指示rm将参数中列出的全部目录和子目录均递归地删除。 
# rm -rf 目录路径
# 使用这种方式可以删除一些顽固文件|目录
$ rm

# 查看文件，适用于内容比较少的情况
$ cat 文件路径

# 查看文件，适用于文件内容比较多的情况
# 退出使用 q
$ less

# 清屏
$ clear

# vi编辑
# i 进入插入模式
# 无论你处于任何模式，esc 都回到命令模式
# :w 保存
# :q 退出
# :wq 保存并退出
# :q! 强制退出不保存
$ vi 文件名
```

> 扩展学习：
>
> - [Linux命令大全----常用文件操作命令](<https://blog.csdn.net/Evankaka/article/details/49227669>)
> - [Linux vi/vim](<https://www.runoob.com/linux/linux-vim.html>)

### git全局配置

> 安装完成后，还需要最后一步设置，在命令行输入：
>
> ```js
> $ git config --global user.name "Your Name"
> $ git config --global user.email "email@example.com"
> ```

因为Git是分布式版本控制系统，所以，每个机器都必须自报家门：你的名字和Email地址。

> 注意`git config`命令的`--global`参数，用了这个参数，表示你这台机器上所有的Git仓库都会使用这个配置，当然也可以对某个仓库指定不同的用户名和Email地址。

### 创建版本库

> 什么是版本库呢？版本库又名仓库，英文名**repository**，你可以简单理解成一个目录，这个目录里面的所有文件都可以被Git管理起来，每个文件的修改、删除，Git都能跟踪，以便任何时刻都可以追踪历史，或者在将来某个时刻可以“还原”。
>
> 所以，创建一个版本库非常简单，首先，选择一个合适的地方，创建一个空目录：

```js
$ mkdir learngit
$ cd learngit
$ pwd
/c/Users/73664/learngit
```

> `pwd`命令用于显示当前目录

**注意：为了避免遇到各种莫名其妙的问题，请确保目录名（包括父目录）不包含中文**

> 第二步，通过`git init`命令把这个目录变成Git可以管理的仓库：

```js
$ git init
Initialized empty Git repository in C:/Users/73664/learngit/.git/
```

细心的同学可以发现当前目录下多了一个`.git`的目录，这个目录是Git来跟踪管理版本库的。

如果你没有看到`.git`目录，那是因为这个目录默认是隐藏的，用`ls -a`命令就可以看见。

言归正传，现在我们编写一个`readme.txt`文件，内容如下：

```js
git is a version control system.
git is free software.
```

一定要放到`learngit`目录下（子目录也行），因为这是一个Git仓库，放到其他地方Git再厉害也找不到这个文件。

和把大象放到冰箱需要3步相比，把一个文件放到Git仓库只需要两步。

第一步，用命令`git add`告诉Git，把文件添加到仓库：

```js
$ git add readme.txt
```

执行上面的命令，没有任何显示，这就对了，Unix的哲学是“没有消息就是好消息”，说明添加成功。

第二步，用命令`git commit`告诉Git，把文件提交到仓库：

```js
$ git commit -m "wrote a readme file"
[master (root-commit) 2752175] wrote a readme file
 1 file changed, 3 insertions(+)
 create mode 100644 readme.txt
```

`-m`后面输入的是本次提交的说明，可以输入任意内容，当然最好是有意义的，这样你就能从历史记录里方便地找到改动记录。

`git commit`命令执行成功后会告诉你，`1 file changed`：1个文件被改动（我们新添加的readme.txt文件）；`3 insertions`：插入了两行内容（readme.txt有两行内容）。

注意：你可以add多次添加多个文件，或者使用`git add .`将目录内所有修改都添加到暂存区，然后用commit统一提交。

```js
$ git add file1.txt file2.txt
// 或者
$ git add .
// 然后
$ git commit -m "add 3 files."
```

### 状态查看

我们已经成功地添加并提交了一个readme.txt文件，现在，是时候继续工作了，于是，我们继续修改readme.txt文件，改成如下内容：

```js
git is a distributed version control system.
git is free software.
```

现在，运行`git status`命令看看结果：

```js
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   readme.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

`git status`命令可以让我们时刻掌握仓库当前的状态，上面的命令输出告诉我们，`readme.txt`被修改过了，但还没有准备提交的修改。

虽然Git告诉我们`readme.txt`被修改了，但如果能看看具体修改了什么内容，自然是很好的。比如你休假两天后，第一天上班时，已经记不清上次怎么修改的`readme.txt`，所以，需要用`git diff`这个命令看看：

```js
$ git diff readme.txt
warning: LF will be replaced by CRLF in readme.txt.
The file will have its original line endings in your working directory
diff --git a/readme.txt b/readme.txt
index 87218be..87a222c 100644
--- a/readme.txt
+++ b/readme.txt
@@ -1,3 +1,3 @@
-git is a version control system.
+git is a distributed version control system.
 git is free software
```

注意：warning: LF will be replaced by CRLF in 

windows中的换行符为 CRLF， 而在linux下的换行符为LF，所以在执行add . 时出现提示，解决办法：

```js
git config --global core.autocrlf false
```

`git diff`顾名思义就是查看difference，显示的格式正是Unix通用的diff格式，可以从上面的命令输出看到，我们在第一行添加了一个`distributed`单词。

知道了对`readme.txt`作了什么修改后，再把它提交到仓库就放心多了，提交修改和提交新文件是一样的两步，第一步是`git add`：

```js
$ git add readme.txt
```

同样没有任何输出。在执行第二步`git commit`之前，我们再运行`git status`看看当前仓库的状态：

```js
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        modified:   readme.txt
```

`git status`告诉我们，将要被提交的修改包括`readme.txt`，下一步，就可以放心地提交了：

```js
$ git commit -m "add distributed"
[master 9e390c2] add distributed
 1 file changed, 1 insertion(+), 1 deletion(-)
```

提交后，我们再用`git status`命令看看仓库的当前状态：

```js
$ git status
On branch master
nothing to commit, working tree clean
```

Git告诉我们当前没有需要提交的修改，而且，工作目录是干净（working tree clean）的。

### 版本回退

现在，再练习一次，修改readme.txt文件如下：

```js
git is a distributed version control system.
git is free software distributed under the GPL.
```

然后尝试提交：

```js
$ git add readme.txt
$ git commit -m "append GPL"
[master 8206148] append GPL
 1 file changed, 1 insertion(+), 1 deletion(-)
```

像这样，你不断对文件进行修改，然后不断提交修改到版本库里, 每当你觉得文件修改到一定程度的时候，就可以“保存一个快照”，这个快照在Git中被称为`commit`。一旦你把文件改乱了，或者误删了文件，还可以从最近的一个`commit`恢复，然后继续工作，而不是把几个月的工作成果全部丢失。

现在，我们回顾一下`readme.txt`文件一共有几个版本被提交到Git仓库里了：

版本1：wrote a readme file

```js
git is a version control system.
git is free software.
```

版本2：add distributed

```js
git is a distributed version control system.
git is free software.
```

版本3：append GPL

```js
git is a distributed version control system.
git is free software distributed under the GPL.
```

在Git中，我们用`git log`命令查看：

```js
$ git log
commit 8206148135ed0cb1ad0e795544c3ec4fa751df9e (HEAD -> master)
Author: magicstf <736643403@qq.com>
Date:   Mon Jun 24 09:47:10 2019 +0800

    append GPL

commit 9e390c2acbaefc11239b89f4759281a5d9f0cf11
Author: magicstf <736643403@qq.com>
Date:   Mon Jun 24 09:42:54 2019 +0800

    add distributed

commit 275217593432e1b3b6fef0b464f487a67efbfcf1
Author: magicstf <736643403@qq.com>
Date:   Mon Jun 24 09:19:54 2019 +0800

    wrote a readme file
```

`git log`命令显示从最近到最远的提交日志，我们可以看到3次提交，最近的一次是`append GPL`，上一次是`add distributed`，最早的一次是`wrote a readme file`。

如果嫌输出信息太多，看得眼花缭乱的，可以试试加上`--pretty=oneline`参数：

```js
$ git log --pretty=oneline
8206148135ed0cb1ad0e795544c3ec4fa751df9e (HEAD -> master) append GPL
9e390c2acbaefc11239b89f4759281a5d9f0cf11 add distributed
275217593432e1b3b6fef0b464f487a67efbfcf1 wrote a readme file
```

你看到的一大串类似`8206148...`的是`commit id`（版本号），和SVN不一样，Git的`commit id`不是1，2，3……递增的数字，而是一个SHA1计算出来的一个非常大的数字，用十六进制表示，而且你看到的`commit id`和我的肯定不一样，以你自己的为准。

**每提交一个新版本，实际上Git就会把它们自动串成一条时间线。**

现在我们启动时光穿梭机，准备把`readme.txt`回退到上一个版本，也就是`add distributed`的那个版本，怎么做呢？

首先，Git必须知道当前版本是哪个版本，在Git中，用`HEAD`表示当前版本，也就是最新的提交`8206148...`（注意我的提交ID和你的肯定不一样），上一个版本就是`HEAD^`，上上一个版本就是`HEAD^^`，往上100个版本，写成`HEAD~100`。

现在，我们要把当前版本`append GPL`回退到上一个版本`add distributed`，就可以使用`git reset`命令：

```js
$ git reset --hard HEAD^
HEAD is now at 9e390c2 add distributed
```

> --hard：暂存区和工作区的内容都会被新指向的commit提交内容所替换；

看看`readme.txt`的内容是不是版本`add distributed`：

```js
$ cat readme.txt
git is a distributed version control system.
git is free software
```

还可以继续回退到上一个版本`wrote a readme file`，不过且慢，然我们用`git log`再看看现在版本库的状态：

```js
$ git log
commit 9e390c2acbaefc11239b89f4759281a5d9f0cf11 (HEAD -> master)
Author: magicstf <736643403@qq.com>
Date:   Mon Jun 24 09:42:54 2019 +0800

    add distributed

commit 275217593432e1b3b6fef0b464f487a67efbfcf1
Author: magicstf <736643403@qq.com>
Date:   Mon Jun 24 09:19:54 2019 +0800

    wrote a readme file
```

最新的那个版本`append GPL`已经看不到了！好比你从21世纪坐时光穿梭机来到了19世纪，想再回去已经回不去了，肿么办？

办法其实还是有的，只要上面的命令行窗口还没有被关掉，你就可以顺着往上找啊找啊，找到那个`append GPL`的`commit id`是`1094adb...`，于是就可以指定回到未来的某个版本：

```js
$ git reset --hard 820614
HEAD is now at 8206148 append GPL
```

看看`readme.txt`的内容：

```js
$ cat readme.txt
git is a distributed version control system.
git is free software distributed under the GPL.
```

Git的版本回退速度非常快，因为Git在内部有个指向当前版本的`HEAD`指针，当你回退版本的时候，Git仅仅是把HEAD从指向`append GPL`：

```ascii
┌────┐
│HEAD│
└────┘
   │
   └──> ○ append GPL
        │
        ○ add distributed
        │
        ○ wrote a readme file
```

改为指向`add distributed`：

```ascii
┌────┐
│HEAD│
└────┘
   │
   │    ○ append GPL
   │    │
   └──> ○ add distributed
        │
        ○ wrote a readme file
```

然后顺便把工作区的文件更新了。所以你让`HEAD`指向哪个版本号，你就把当前版本定位在哪。

现在，你回退到了某个版本，关掉了电脑，第二天早上就后悔了，想恢复到新版本怎么办？找不到新版本的`commit id`怎么办？

在Git中，总是有后悔药可以吃的。当你用`$ git reset --hard HEAD^`回退到`add distributed`版本时，再想恢复到`append GPL`，就必须找到`append GPL`的commit id。Git提供了一个命令`git reflog`用来记录你的每一次命令：

```js
$ git reflog
8206148 (HEAD -> master) HEAD@{0}: reset: moving to 820614
9e390c2 HEAD@{1}: reset: moving to HEAD^
8206148 (HEAD -> master) HEAD@{2}: commit: append GPL
9e390c2 HEAD@{3}: commit: add distributed
2752175 HEAD@{4}: commit (initial): wrote a readme file
```

终于舒了口气，从输出可知，`append GPL`的commit id是`8206148`，现在，你又可以乘坐时光机回到未来了。

### 工作区和暂存区

> Git和其他版本控制系统如SVN的一个不同之处就是有暂存区的概念。

#### 工作区（Working Directory）

就是你在电脑里能看到的目录，比如我的`learngit`文件夹就是一个工作区：

![1561342588852](assets\1561342588852.png)

#### 版本库（Repository）

工作区有一个隐藏目录`.git`，这个不算工作区，而是Git的版本库。

Git的版本库里存了很多东西，其中最重要的就是称为stage（或者叫index）的暂存区，还有Git为我们自动创建的第一个分支`master`，以及指向`master`的一个指针叫`HEAD`。

![](assets\0.jpg)

分支和`HEAD`的概念我们以后再讲。

前面讲了我们把文件往Git版本库里添加的时候，是分两步执行的：

第一步是用`git add`把文件添加进去，实际上就是把文件修改添加到暂存区；

第二步是用`git commit`提交更改，实际上就是把暂存区的所有内容提交到当前分支。

因为我们创建Git版本库时，Git自动为我们创建了唯一一个`master`分支，所以，现在，`git commit`就是往`master`分支上提交更改。

你可以简单理解为，需要提交的文件修改通通放到暂存区，然后，一次性提交暂存区的所有修改。

俗话说，实践出真知。现在，我们再练习一遍，先对`readme.txt`做个修改，比如加上一行内容：

```js
git is a distributed version control system.
git is free software distributed under the GPL.
git has a mutable index called stage.
```

然后，在工作区新增一个`LICENSE`文本文件（内容随便写）。

```js
$ touch LICENSE.md
$ vi LICENSE.md
$ cat LICENSE.md
```

先用`git status`查看一下状态：

```js
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   readme.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        LICENSE.md

no changes added to commit (use "git add" and/or "git commit -a")
```

Git非常清楚地告诉我们，`readme.txt`被修改了，而`LICENSE`还从来没有被添加过，所以它的状态是`Untracked`。

现在，使用两次命令`git add`，把`readme.txt`和`LICENSE`都添加后，用`git status`再查看一下：

```js
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   LICENSE.md
        modified:   readme.txt
```

现在，暂存区的状态就变成这样了：

![](assets\1.jpg)

所以，`git add`命令实际上就是把要提交的所有修改放到暂存区（Stage），然后，执行`git commit`就可以一次性把暂存区的所有修改提交到分支。

```js
$ git commit -m "understand how stage works"
[master 14a390e] understand how stage works
 2 files changed, 2 insertions(+), 1 deletion(-)
 create mode 100644 LICENSE.md
```

一旦提交后，如果你又没有对工作区做任何修改，那么工作区就是“干净”的：

```js
$ git status
On branch master
nothing to commit, working tree clean
```

现在版本库变成了这样，暂存区就没有任何内容了：

![](assets\2.jpg)

### 管理修改

> 为什么Git比其他版本控制系统设计得优秀，因为Git跟踪并管理的是修改，而非文件。

为什么说Git管理的是修改，而不是文件呢？我们还是做实验。第一步，对readme.txt做一个修改，比如加一行内容：

```js
$ cat readme.txt
git is a distributed version control system.
git is free software distributed under the GPL.
git has a mutable index called stage.
git tracks changes.
```

然后，添加：

```js
$ git add readme.txt
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        modified:   readme.txt
```

然后，再修改readme.txt：

```js
$ cat readme.txt
git is a distributed version control system.
git is free software distributed under the GPL.
git has a mutable index called stage.
git tracks changes of files.
```

提交：

```js
$ git commit -m "git tracks changes"
[master 8798b94] git tracks changes
 1 file changed, 1 insertion(+)
```

提交后，再看看状态：

```js
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   readme.txt

no changes added to commit (use "git add" and/or "git commit -a")

```

咦，怎么第二次的修改没有被提交？

别激动，我们回顾一下操作过程：

第一次修改 -> `git add` -> 第二次修改 -> `git commit`

你看，我们前面讲了，Git管理的是修改，当你用`git add`命令后，在工作区的第一次修改被放入暂存区，准备提交，但是，在工作区的第二次修改并没有放入暂存区，所以，`git commit`只负责把暂存区的修改提交了，也就是第一次的修改被提交了，第二次的修改不会被提交。

提交后，用`git diff HEAD -- readme.txt`命令可以查看工作区和版本库里面最新版本的区别：

```js
$ git diff HEAD -- readme.txt
diff --git a/readme.txt b/readme.txt
index 6c29947..b7b0032 100644
--- a/readme.txt
+++ b/readme.txt
@@ -1,4 +1,4 @@
 git is a distributed version control system.
 git is free software distributed under the GPL.
 git has a mutable index called stage.
-git tracks changes.
+git tracks changes of files.

```

>  注意：--与readme.txt中间有一个空格

那怎么提交第二次修改呢 ?

1. 第一次修改 -> `git add` ->`git commit`-> 第二次修改 -> `git add` -> `git commit`

2. 第一次修改 -> `git add` -> 第二次修改 -> `git add` -> `git commit`

### 撤销修改

自然，你是不会犯错的。不过现在是凌晨两点，你正在赶一份工作报告，你在`readme.txt`中添加了一行：

```js
$ cat readme.txt
git is a distributed version control system.
git is free software distributed under the GPL.
git has a mutable index called stage.
git tracks changes of files.
my stupid boss still prefers SVN.
```

在你准备提交前，一杯咖啡起了作用，你猛然发现了`stupid boss`可能会让你丢掉这个月的奖金！

既然错误发现得很及时，就可以很容易地纠正它。你可以删掉最后一行，手动把文件恢复到上一个版本的状态。如果用`git status`查看一下：

```js
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   readme.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

你可以发现，Git会告诉你，`git checkout -- file`可以丢弃工作区的修改：

```js
$ git checkout -- readme.txt
```

命令`git checkout -- readme.txt`意思就是，把`readme.txt`文件在工作区的修改全部撤销，这里有两种情况：

一种是`readme.txt`自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；

一种是`readme.txt`已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。

总之，就是让这个文件回到最近一次`git commit`或`git add`时的状态。

现在，看看`readme.txt`的文件内容：

```js
$ cat readme.txt
git is a distributed version control system.
git is free software distributed under the GPL.
git has a mutable index called stage.
git tracks changes.
```

文件内容果然复原了。

`git checkout -- file`命令中的`--`很重要，没有`--`，就变成了“切换到另一个分支”的命令，我们在后面的分支管理中会再次遇到`git checkout`命令。

现在假定是凌晨3点，你不但写了一些胡话，还`git add`到暂存区了：

```js
$ cat readme.txt
git is a distributed version control system.
git is free software distributed under the GPL.
git has a mutable index called stage.
git tracks changes.
my stupid boss still prefers SVN.

$ git add readme.txt
```

庆幸的是，在`commit`之前，你发现了这个问题。用`git status`查看一下，修改只是添加到了暂存区，还没有提交：

```js
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        modified:   readme.txt
```

Git同样告诉我们，用命令`git reset HEAD <file>`可以把暂存区的修改撤销掉（unstage），重新放回工作区：

```js
$ git reset HEAD readme.txt
Unstaged changes after reset:
M       readme.txt
```

`git reset`命令既可以回退版本，也可以把暂存区的修改回退到工作区。当我们用`HEAD`时，表示最新的版本。

再用`git status`查看一下，现在暂存区是干净的，工作区有修改：

```js
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   readme.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

还记得如何丢弃工作区的修改吗？

```js
$ git checkout -- readme.txt
$ git status
On branch master
nothing to commit, working tree clean
```

终于可以睡觉了！

### 删除文件

> 在Git中，删除也是一个修改操作，我们实战一下，先添加一个新文件`test.txt`到Git并且提交：

```js
$ git add test.txt
$ git commit -m "add test.txt"
[master 51c785f] add test.txt
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test.txt
```

一般情况下，你通常直接在文件管理器中把没用的文件删了，或者用`rm`命令删了：

```js
$ rm test.txt
```

这个时候，Git知道你删除了文件，因此，工作区和版本库就不一致了，`git status`命令会立刻告诉你哪些文件被删除了：

```js
$ git status
On branch master
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        deleted:    test.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

现在你有两个选择，一是确实要从版本库中删除该文件，那就用命令`git rm`删掉，并且`git commit`：

```js
$ git rm test.txt
rm 'test.txt'

$ git commit -m "remove test.txt"
[master 09dc11f] remove test.txt
 1 file changed, 0 insertions(+), 0 deletions(-)
 delete mode 100644 test.txt

```

现在，文件就从版本库中被删除了。

> 先手动删除文件，然后使用git rm <file>和git add<file>效果是一样的。

另一种情况是删错了，因为版本库里还有呢，所以可以很轻松地把误删的文件恢复到最新版本：

```js
$ git checkout -- test.txt
```

`git checkout`其实是用版本库里的版本替换工作区的版本，无论工作区是修改还是删除，都可以“一键还原”。

**注意：从来没有被添加到版本库就被删除的文件，是无法恢复的！**

### 远程仓库

- 备份代码

- 多人协作

  Git是分布式版本控制系统，同一个Git仓库，可以分布到不同的机器上。怎么分布呢？最早，肯定只有一台机器有一个原始版本库，此后，别的机器可以“克隆”这个原始版本库，而且每台机器的版本库其实都是一样的，并没有主次之分。

  你肯定会想，至少需要两台机器才能玩远程库不是？但是我只有一台电脑，怎么玩？

  其实一台电脑上也是可以克隆多个版本库的，只要不在同一个目录下。不过，现实生活中是不会有人这么傻的在一台电脑上搞几个远程库玩，因为一台电脑上搞几个远程库完全没有意义，而且硬盘挂了会导致所有库都挂掉，所以我也不告诉你在一台电脑上怎么克隆多个仓库。

  实际情况往往是这样，找一台电脑充当服务器的角色，每天24小时开机，其他每个人都从这个“服务器”仓库克隆一份到自己的电脑上，并且各自把各自的提交推送到服务器仓库里，也从服务器仓库中拉取别人的提交。

  完全可以自己搭建一台运行Git的服务器，不过现阶段，为了学Git先搭个服务器绝对是小题大作。好在这个世界上有个叫[GitHub](https://github.com/)的神奇的网站，从名字就可以看出，这个网站就是提供Git仓库托管服务的，所以，只要注册一个GitHub账号，就可以免费获得Git远程仓库。

#### 本地Git仓库和GitHub仓库之间的传输协议

- ##### SSH

第1步：创建SSH Key。在用户主目录下，看看有没有.ssh目录，如果有，再看看这个目录下有没有`id_rsa`和`id_rsa.pub`这两个文件，如果已经有了，可直接跳到下一步。如果没有，打开Shell（Windows下打开Git Bash），创建SSH Key：

```js
$ ssh-keygen -t rsa -C "youremail@example.com"
```

你需要把邮件地址换成你自己的邮件地址，然后一路回车，使用默认值即可，由于这个Key也不是用于军事目的，所以也无需设置密码。

如果一切顺利的话，可以在用户主目录里找到`.ssh`目录，里面有`id_rsa`和`id_rsa.pub`两个文件，这两个就是SSH Key的秘钥对，`id_rsa`是私钥，不能泄露出去，`id_rsa.pub`是公钥，可以放心地告诉任何人。

第2步：登陆GitHub，打开“Account settings”，“SSH Keys”页面：

然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴`id_rsa.pub`文件的内容：

点“Add Key”，你就应该看到已经添加的Key

为什么GitHub需要SSH Key呢？因为GitHub需要识别出你推送的提交确实是你推送的，而不是别人冒充的，而Git支持SSH协议，所以，GitHub只要知道了你的公钥，就可以确认只有你自己才能推送。

当然，GitHub允许你添加多个Key。假定你有若干电脑，你一会儿在公司提交，一会儿在家里提交，只要把每台电脑的Key都添加到GitHub，就可以在每台电脑上往GitHub推送了。

最后友情提示，在GitHub上免费托管的Git仓库，任何人都可以看到喔（但只有你自己才能改）。所以，不要把敏感信息放进去。

- ##### HTTPS

  无需设置，直接克隆

> 有了远程仓库，妈妈再也不用担心我的硬盘了。

#### 添加远程库

现在的情景是，你已经在本地创建了一个Git仓库后，又想在GitHub创建一个Git仓库，并且让这两个仓库进行远程同步，这样，GitHub上的仓库既可以作为备份，又可以让其他人通过该仓库来协作，真是一举多得。

首先，登陆GitHub，然后，在右上角找到“+”按钮，点击 "New repository" 创建一个新的仓库：

![](D:\BaiduNetdiskDownload\mygit\note\assets\1561347685293.png)

在Repository name填入`learngit`，其他保持默认设置，点击“Create repository”按钮，就成功地创建了一个新的Git仓库：

![1561347869051](assets\1561347869051.png)

![1561347924469](assets\1561347924469.png)

目前，在GitHub上的这个`learngit`仓库还是空的，GitHub告诉我们，可以从这个仓库克隆出新的仓库，也可以把一个已有的本地仓库与之关联，然后，把本地仓库的内容推送到GitHub仓库。

现在，我们根据GitHub的提示，在本地的`learngit`仓库下运行命令：

```js
git remote add origin https://github.com/magicstf/learngit.git
```

请千万注意，把上面的`magicstf`替换成你自己的GitHub账户名，否则，你在本地关联的就是我的远程库，关联没有问题，但是你以后推送是推不上去的，因为你的SSH Key公钥不在我的账户列表中。

添加后，远程库的名字就是`origin`，这是Git默认的叫法，也可以改成别的，但是`origin`这个名字一看就知道是远程库。

下一步，就可以把本地库的所有内容推送到远程库上：

```js
$ git push -u origin master
Enumerating objects: 20, done.
Counting objects: 100% (20/20), done.
Delta compression using up to 12 threads
Compressing objects: 100% (15/15), done.
Writing objects: 100% (20/20), 1.58 KiB | 323.00 KiB/s, done.
Total 20 (delta 5), reused 0 (delta 0)
remote: Resolving deltas: 100% (5/5), done.
To https://github.com/magicstf/learngit.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.

```

把本地库的内容推送到远程，用`git push`命令，实际上是把当前分支`master`推送到远程。

由于远程库是空的，我们第一次推送`master`分支时，加上了`-u`参数，Git不但会把本地的`master`分支内容推送的远程新的`master`分支，还会把本地的`master`分支和远程的`master`分支关联起来，在以后的推送或者拉取时就可以简化命令。

推送成功后，可以立刻在GitHub页面中看到远程库的内容已经和本地一模一样：

![1561348191810](assets\1561348191810.png)

从现在起，只要本地作了提交，就可以通过命令：

```js
$ git push origin master
```

把本地`master`分支的最新修改推送至GitHub，现在，你就拥有了真正的分布式版本库！

注意：SSH警告

> 当你第一次使用Git的`clone`或者`push`命令连接GitHub时，会得到一个警告：

```js
The authenticity of host 'github.com (xx.xx.xx.xx)' can't be established.
RSA key fingerprint is xx.xx.xx.xx.xx.
Are you sure you want to continue connecting (yes/no)?
```

这是因为Git使用SSH连接，而SSH连接在第一次验证GitHub服务器的Key时，需要你确认GitHub的Key的指纹信息是否真的来自GitHub的服务器，输入`yes`回车即可。

Git会输出一个警告，告诉你已经把GitHub的Key添加到本机的一个信任列表里了：

```js
Warning: Permanently added 'github.com' (RSA) to the list of known hosts.
```

这个警告只会出现一次，后面的操作就不会有任何警告了。

分布式版本系统的最大好处之一是在本地工作完全不需要考虑远程库的存在，也就是有没有联网都可以正常工作，而SVN在没有联网的时候是拒绝干活的！当有网络的时候，再把本地提交推送一下就完成了同步，真是太方便了！

#### 从远程库克隆

我们从零开发，那么最好的方式是先创建远程库，然后，从远程库克隆。

首先，登陆GitHub，创建一个新的仓库，名字叫`gitskills`：

![1561348600923](assets\1561348600923.png)

我们勾选`Initialize this repository with a README`，这样GitHub会自动为我们创建一个`README.md`文件。创建完毕后，可以看到`README.md`文件：

![1561348655294](assets\1561348655294.png)

现在，远程库已经准备好了，下一步是用命令`git clone`克隆一个本地库：

```js
$ git clone git@github.com:magicstf/gitskills.git
Cloning into 'gitskills'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.
```

注意把Git库的地址换成你自己的，然后进入`gitskills`目录看看，已经有`README.md`文件了：

```
$ cd gitskills
$ ls
README.md
```

如果有多个人协作开发，那么每个人各自从远程克隆一份就可以了。

### 分支管理

分支就是科幻电影里面的平行宇宙，当你正在电脑前努力学习Git的时候，另一个你正在另一个平行宇宙里努力学习SVN。

如果两个平行宇宙互不干扰，那对现在的你也没啥影响。不过，在某个时间点，两个平行宇宙合并了，结果，你既学会了Git又学会了SVN！

![](assets\fenzhi.png)

分支在实际中有什么用呢？假设你准备开发一个新功能，但是需要两周才能完成，第一周你写了50%的代码，如果立刻提交，由于代码还没写完，不完整的代码库会导致别人不能干活了。如果等代码全部写完再一次提交，又存在丢失每天进度的巨大风险。

现在有了分支，就不用怕了。你创建了一个属于你自己的分支，别人看不到，还继续在原来的分支上正常工作，而你在自己的分支上干活，想提交就提交，直到开发完毕后，再一次性合并到原来的分支上，这样，既安全，又不影响别人工作。

其他版本控制系统如SVN等都有分支管理，但是用过之后你会发现，这些版本控制系统创建和切换分支比蜗牛还慢，简直让人无法忍受，结果分支功能成了摆设，大家都不去用。

但Git的分支是与众不同的，无论创建、切换和删除分支，Git在1秒钟之内就能完成！无论你的版本库是1个文件还是1万个文件。

#### 创建与合并分支

在[版本回退](https://www.liaoxuefeng.com/wiki/896043488029600/897013573512192)里，你已经知道，每次提交，Git都把它们串成一条时间线，这条时间线就是一个分支。截止到目前，只有一条时间线，在Git里，这个分支叫主分支，即`master`分支。`HEAD`严格来说不是指向提交，而是指向`master`，`master`才是指向提交的，所以，`HEAD`指向的就是当前分支。

一开始的时候，`master`分支是一条线，Git用`master`指向最新的提交，再用`HEAD`指向`master`，就能确定当前分支，以及当前分支的提交点：

![1561358821047](assets\1561358821047.png)

每次提交，`master`分支都会向前移动一步，这样，随着你不断提交，`master`分支的线也越来越长。

当我们创建新的分支，例如`dev`时，Git新建了一个指针叫`dev`，指向`master`相同的提交，再把`HEAD`指向`dev`，就表示当前分支在`dev`上：

![1561359115802](assets\1561359115802.png)

你看，Git创建一个分支很快，因为除了增加一个`dev`指针，改改`HEAD`的指向，工作区的文件都没有任何变化！

不过，从现在开始，对工作区的修改和提交就是针对`dev`分支了，比如新提交一次后，`dev`指针往前移动一步，而`master`指针不变：

![1561359306142](assets\1561359306142.png)

假如我们在`dev`上的工作完成了，就可以把`dev`合并到`master`上。Git怎么合并呢？最简单的方法，就是直接把`master`指向`dev`的当前提交，就完成了合并：

![1561359452025](assets\1561359452025.png)

所以Git合并分支也很快！就改改指针，工作区内容也不变！

合并完分支后，甚至可以删除`dev`分支。删除`dev`分支就是把`dev`指针给删掉，删掉后，我们就剩下了一条`master`分支：

![1561359599879](assets\1561359599879.png)

下面开始实战。

首先，我们创建`dev`分支，然后切换到`dev`分支：

```js
$ git checkout -b dev
Switched to a new branch 'dev'
```

`git checkout`命令加上`-b`参数表示创建并切换，相当于以下两条命令：

```js
$ git branch dev
$ git checkout dev
Switched to branch 'dev'
```

然后，用`git branch`命令查看当前分支：

```js
$ git branch
* dev
  master
```

`git branch`命令会列出所有分支，当前分支前面会标一个`*`号。

然后，我们就可以在`dev`分支上正常提交，比如对`readme.txt`做个修改，加上一行：

```js
creating a new branch is quick.
```

然后提交：

```js
$ git add readme.txt
$ git commit -m "branch test"
[dev ff78c00] branch test
 1 file changed, 1 insertion(+)
```

现在，`dev`分支的工作完成，我们就可以切换回`master`分支：

```js
$ git checkout master
Switched to branch 'master'
Your branch is up to date with 'origin/master'.
```

切换回`master`分支后，再查看一个`readme.txt`文件，刚才添加的内容不见了！因为那个提交是在`dev`分支上，而`master`分支此刻的提交点并没有变：

![1561360293283](assets\1561360293283.png)

现在，我们把`dev`分支的工作成果合并到`master`分支上：

```js
$ git merge dev
Updating 09dc11f..ff78c00
Fast-forward
 readme.txt | 1 +
 1 file changed, 1 insertion(+)
```

`git merge`命令用于合并指定分支到当前分支。合并后，再查看`readme.txt`的内容，就可以看到，和`dev`分支的最新提交是完全一样的。

注意到上面的`Fast-forward`信息，Git告诉我们，这次合并是“快进模式”，也就是直接把`master`指向`dev`的当前提交，所以合并速度非常快。

当然，也不是每次合并都能`Fast-forward`，我们后面会讲其他方式的合并。

合并完成后，就可以放心地删除`dev`分支了：

```js
$ git branch -d dev
Deleted branch dev (was ff78c00).
```

删除后，查看`branch`，就只剩下`master`分支了：

```js
$ git branch
* master
```

因为创建、合并和删除分支非常快，所以Git鼓励你使用分支完成某个任务，合并后再删掉分支，这和直接在`master`分支上工作效果是一样的，但过程更安全。

#### 解决冲突

即使是最美好的婚姻，一生中也会有200次离婚的念头，50次掐死对方的冲动。

同样，合并分支往往也不是一帆风顺的。

准备新的`feature1`分支，继续我们的新分支开发：

```js
$ git checkout -b feature1
Switched to a new branch 'feature1'
```

修改`readme.txt`最后一行，改为：

```js
creating a new branch is quick and simple.
```

在`feature1`分支上提交：

```js
$ git add readme.txt
$ git commit -m " and simple"
[feature1 c26dbed]  and simple
 1 file changed, 1 insertion(+), 1 deletion(-)
```

切换到`master`分支：

```js
$ git checkout master
Switched to branch 'master'
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)
```

Git还会自动提示我们当前`master`分支比远程的`master`分支要超前1个提交。

在`master`分支上把`readme.txt`文件的最后一行改为：

```js
creating a new branch is quick & simple.
```

提交：

```js
$ git add readme.txt 
$ git commit -m "& simple"
[master 5357755] & simple
 1 file changed, 1 insertion(+), 1 deletion(-)
```

现在，`master`分支和`feature1`分支各自都分别有新的提交，变成了这样：

![1561361326313](assets\1561361326313.png)

这种情况下，Git无法执行“快速合并”，只能试图把各自的修改合并起来，但这种合并就可能会有冲突，我们试试看：

```js
$ git merge feature1
Auto-merging readme.txt
CONFLICT (content): Merge conflict in readme.txt
Automatic merge failed; fix conflicts and then commit the result.
```

果然冲突了！Git告诉我们，`readme.txt`文件存在冲突，必须手动解决冲突后再提交。`git status`也可以告诉我们冲突的文件：

```js
$ git status
On branch master
Your branch is ahead of 'origin/master' by 2 commits.
  (use "git push" to publish your local commits)

You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)

        both modified:   readme.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

我们可以直接查看readme.txt的内容：

```js
$ cat readme.txt
git is a distributed version control system.
git is free software distributed under the GPL.
git has a mutable index called stage.
git tracks changes.
<<<<<<< HEAD
creating a new branch is quick & simple.
=======
creating a new branch is quick and simple.
>>>>>>> feature1
```

Git用`<<<<<<<`，`=======`，`>>>>>>>`标记出不同分支的内容，我们修改如下后保存：

```js
creating a new branch is quick and simple.
```

再提交：

```js
$ git add readme.txt
$ git commit -m "conflict fixed"
[master c8a6cd4] conflict fixed
```

现在，`master`分支和`feature1`分支变成了下图所示：

![1561361814715](assets\1561361814715.png)

用带参数的`git log`也可以看到分支的合并情况：

```js
// 查看分支的合并情况，包括分支合并图、一行显示、提交校验码缩略显示。
$ git log --graph --pretty=oneline --abbrev-commit
*   c8a6cd4 (HEAD -> master) conflict fixed
|\
| * c26dbed (feature1)  and simple
* | 5357755 & simple
|/
* ff78c00 branch test
* 09dc11f (origin/master) remove test.txt
* 51c785f add test.txt
* 8798b94 git tracks changes
* 14a390e understand how stage works
* 8206148 append GPL
* 9e390c2 add distributed
* 2752175 wrote a readme file
```

>  `--graph` 查看分支合并图

>  --abbrev-commit  提交校验码缩略显示

最后，删除`feature1`分支：

```js
$ git branch -d feature1
Deleted branch feature1 (was c26dbed).
```

工作完成。

#### 分支管理策略

通常，合并分支时，如果可能，Git会用`Fast forward`模式，但这种模式下，删除分支后，会丢掉分支信息。

如果要强制禁用`Fast forward`模式，Git就会在merge时生成一个新的commit，这样，从分支历史上就可以看出分支信息。

下面我们实战一下`--no-ff`方式的`git merge`：

首先，仍然创建并切换`dev`分支：

```js
$ git checkout -b dev
Switched to a new branch 'dev'
```

修改readme.txt文件，并提交一个新的commit：

```js
$ git add readme.txt
$ git commit -m "add merge"
[dev d695fb3] add merge
 1 file changed, 1 insertion(+)
```

现在，我们切换回`master`：

```js
$ git checkout master
Switched to branch 'master'
```

准备合并`dev`分支，请注意`--no-ff`参数，表示禁用`Fast forward`：

```js
$ git merge --no-ff -m "merge with no-ff" dev
Merge made by the 'recursive' strategy.
 readme.txt | 1 +
 1 file changed, 1 insertion(+)
```

因为本次合并要创建一个新的commit，所以加上`-m`参数，把commit描述写进去。

合并后，我们用`git log`看看分支历史：

```js
$ git log --graph --pretty=oneline --abbrev-commit
*   ba2c977 (HEAD -> master) merge with no-ff
|\
| * d695fb3 (dev) add merge
|/
...
```

可以看到，不使用`Fast forward`模式，merge后就像这样：

![1561363084702](assets\1561363084702.png)

##### 分支策略

在实际开发中，我们应该按照几个基本原则进行分支管理：

首先，`master`分支应该是非常稳定的，也就是仅用来发布新版本，平时不能在上面干活；

那在哪干活呢？干活都在`dev`分支上，也就是说，`dev`分支是不稳定的，到某个时候，比如1.0版本发布时，再把`dev`分支合并到`master`上，在`master`分支发布1.0版本；

你和你的小伙伴们每个人都在`dev`分支上干活，每个人都有自己的分支，时不时地往`dev`分支上合并就可以了。

所以，团队合作的分支看起来就像这样：

![1561366229027](assets\1561366229027.png)

#### Bug分支

软件开发中，bug就像家常便饭一样。有了bug就需要修复，在Git中，由于分支是如此的强大，所以，每个bug都可以通过一个新的临时分支来修复，修复后，合并分支，然后将临时分支删除。

当你接到一个修复一个代号101的bug的任务时，很自然地，你想创建一个分支`issue-101`来修复它，但是，等等，当前正在`dev`上进行的工作还没有提交：

```js
$ git status
On branch dev
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   hello.js
```

并不是你不想提交，而是工作只进行到一半，还没法提交，预计完成还需1天时间。但是，必须在两个小时内修复该bug，怎么办？

幸好，Git还提供了一个`stash`功能，可以把当前工作现场“储藏”起来，等以后恢复现场后继续工作：

```js
$ git stash
Saved working directory and index state WIP on dev: d695fb3 add merge
```

现在，用`git status`查看工作区，就是干净的（除非有没有被Git管理的文件），因此可以放心地创建分支来修复bug。

首先确定要在哪个分支上修复bug，假定需要在`master`分支上修复，就从`master`创建临时分支：

```js
$ git checkout master
Switched to branch 'master'
Your branch is ahead of 'origin/master' by 6 commits.
  (use "git push" to publish your local commits)

$ git checkout -b issue-101
Switched to a new branch 'issue-101'
```

现在修复bug，需要把“git is free software ...”改为“git is a free software ...”，然后提交：

```js
$ git add readme.txt

$ git commit -m "fix bug 101"
[issue-101 e4224c0] fix bug 101
 1 file changed, 1 insertion(+), 1 deletion(-)
```

修复完成后，切换到`master`分支，并完成合并，最后删除`issue-101`分支：

```js
$ git checkout master
Switched to branch 'master'
Your branch is ahead of 'origin/master' by 6 commits.
  (use "git push" to publish your local commits)

$ git merge --no-ff -m "merged bug fix 101" issue-101
Merge made by the 'recursive' strategy.
 readme.txt | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)

$ git branch -d issue-101
Deleted branch issue-101 (was e4224c0).
```

太棒了，原计划两个小时的bug修复只花了5分钟！现在，是时候接着回到`dev`分支干活了！

```js
$ git checkout dev
Switched to branch 'dev'

$ git status
On branch dev
nothing to commit, working tree clean

```

工作区是干净的，刚才的工作现场存到哪去了？用`git stash list`命令看看：

```js
$ git stash list
stash@{0}: WIP on dev: d695fb3 add merge
```

工作现场还在，Git把stash内容存在某个地方了，但是需要恢复一下，有两个办法：

一是用`git stash apply`恢复，但是恢复后，stash内容并不删除，你需要用`git stash drop`来删除；

另一种方式是用`git stash pop`，恢复的同时把stash内容也删了：

```js
$ git stash pop
On branch dev
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   hello.js

Dropped refs/stash@{0} (9980ae39952affdb59b93632ebcba653932a8b3c)
```

再用`git stash list`查看，就看不到任何stash内容了：

```js
$ git stash list
```

你可以多次stash，恢复的时候，先用`git stash list`查看，然后恢复指定的stash，用命令：

```js
$ git stash apply stash@{0}
```

#### Feature分支

软件开发中，总有无穷无尽的新的功能要不断添加进来。

添加一个新功能时，你肯定不希望因为一些实验性质的代码，把主分支搞乱了，所以，每添加一个新功能，最好新建一个feature分支，在上面开发，完成后，合并，最后，删除该feature分支。

现在，你终于接到了一个新任务：开发代号为007的新功能。

于是准备开发：

```js
$ git checkout -b feature-007
Switched to a new branch 'feature-007'
```

5分钟后，开发完毕：

```js
$ git add world.js

$ git status
On branch feature-007
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   world.js

$ git commit -m "add feature 007"
[feature-007 cc408f9] add feature 007
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 world.js

```

切回`dev`，准备合并：

```js
$ git checkout dev
```

一切顺利的话，feature分支和bug分支是类似的，合并，然后删除。

但是！

就在此时，接到上级命令，因经费不足，新功能必须取消！

虽然白干了，但是这个包含机密资料的分支还是必须就地销毁：

```js
$ git branch -d feature-007
error: The branch 'feature-007' is not fully merged.
If you are sure you want to delete it, run 'git branch -D feature-007'.
```

销毁失败。Git友情提醒，`feature-vulcan`分支还没有被合并，如果删除，将丢失掉修改，如果要强行删除，需要使用大写的`-D`参数。。

现在我们强行删除：

```js
$ git branch -D feature-007
Deleted branch feature-007 (was cc408f9).
```

删除成功！

#### 多人协作

当你从远程仓库克隆时，实际上Git自动把本地的`master`分支和远程的`master`分支对应起来了，并且，远程仓库的默认名称是`origin`。

要查看远程库的信息，用`git remote`：

```js
$ git remote
origin
```

或者，用`git remote -v`显示更详细的信息：

```js
$ git remote -v
origin  https://github.com/magicstf/learngit.git (fetch)
origin  https://github.com/magicstf/learngit.git (push)
```

上面显示了可以抓取和推送的`origin`的地址。如果没有推送权限，就看不到push的地址。

##### 推送分支

推送分支，就是把该分支上的所有本地提交推送到远程库。推送时，要指定本地分支，这样，Git就会把该分支推送到远程库对应的远程分支上：

```js
$ git push origin master
```

如果要推送其他分支，比如`dev`，就改成：

```
$ git push origin dev
```

但是，并不是一定要把本地分支往远程推送，那么，哪些分支需要推送，哪些不需要呢？

- `master`分支是主分支，因此要时刻与远程同步；
- `dev`分支是开发分支，团队所有成员都需要在上面工作，所以也需要与远程同步；
- bug分支只用于在本地修复bug，就没必要推到远程了，除非老板要看看你每周到底修复了几个bug；
- feature分支是否推到远程，取决于你是否和你的小伙伴合作在上面开发。

总之，就是在Git中，分支完全可以在本地自己藏着玩，是否推送，视你的心情而定！

##### 抓取分支

多人协作时，大家都会往`master`和`dev`分支上推送各自的修改。

现在，模拟一个你的小伙伴，可以在另一台电脑（注意要把SSH Key添加到GitHub）或者同一台电脑的另一个目录下克隆：

```js
$ git clone git@github.com:magicstf/learngit.git
Cloning into 'learngit'...
remote: Enumerating objects: 38, done.
remote: Counting objects: 100% (38/38), done.
remote: Compressing objects: 100% (19/19), done.
remote: Total 38 (delta 14), reused 38 (delta 14), pack-reused 0
Receiving objects: 100% (38/38), done.
Resolving deltas: 100% (14/14), done.
```

当你的小伙伴从远程库clone时，默认情况下，你的小伙伴只能看到本地的`master`分支。不信可以用`git branch`命令看看：

```js
$ git branch
* master
```

现在，你的小伙伴要在`dev`分支上开发，就必须创建远程`origin`的`dev`分支到本地，于是他用这个命令创建本地`dev`分支：

> 这里可能有的同学会报错，报错信息如下：
>
> fatal: 'origin/dev' is not a commit and a branch 'dev' cannot be created from it
>
> 这是因为远程仓库上没有dev分支，我们要将自己的dev分支推送到远程，这样，你的小伙伴才可以创建本地分支并与远程的dev进行关联,执行如下命令：
>
> ```js
> $ git push origin div
> ```
>
> 你推送上去以后，你的小伙伴还需要重新拉去一下远程仓库：
>
> ```js
> $ git pull
> ```
>
> 这样操作后，再执行如下命令：

```js
$ git checkout -b dev origin/dev
```

现在，他就可以在`dev`上继续修改，然后，时不时地把`dev`分支`push`到远程：

```js
$ git add env.txt

$ git commit -m "add env"
[dev 5cb158a] add env
 1 file changed, 1 insertion(+)
 create mode 100644 env.txt

$ git push origin dev
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 12 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 339 bytes | 169.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To github.com:magicstf/learngit.git
   c5b7a0f..5cb158a  dev -> dev                             
```

你的小伙伴已经向`origin/dev`分支推送了他的提交，而碰巧你也对同样的文件作了修改，并试图推送：

```js
$ cat env.txt
env

$ git add env.txt

$ git commit -m "add new env"
[dev f1ebc2c] add new env
 1 file changed, 1 insertion(+)
 create mode 100644 env.txt
                                             
$ git push origin dev
To https://github.com/magicstf/learngit.git
 ! [rejected]        dev -> dev (fetch first)
error: failed to push some refs to 'https://github.com/magicstf/learngit.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.  
```

推送失败，因为你的小伙伴的最新提交和你试图推送的提交有冲突，解决办法也很简单，Git已经提示我们，先用`git pull`把最新的提交从`origin/dev`抓下来，然后，在本地合并，解决冲突，再推送：

```js
$ git pull
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 3 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), done.
From https://github.com/magicstf/learngit
   c5b7a0f..5cb158a  dev        -> origin/dev
There is no tracking information for the current branch.
Please specify which branch you want to merge with.
See git-pull(1) for details.

    git pull <remote> <branch>

If you wish to set tracking information for this branch you can do so with:

    git branch --set-upstream-to=origin/<branch> dev
```

`git pull`也失败了，原因是没有指定本地`dev`分支与远程`origin/dev`分支的链接，根据提示，设置`dev`和`origin/dev`的链接：

```js
$ git branch --set-upstream-to=origin/dev dev
Branch 'dev' set up to track remote branch 'dev' from 'origin'.
```

再pull：

```js
$ git pull
CONFLICT (add/add): Merge conflict in env.txt
Auto-merging env.txt
Automatic merge failed; fix conflicts and then commit the result.
```

这回`git pull`成功，但是合并有冲突，需要手动解决，解决的方法和分支管理中的[解决冲突](http://www.liaoxuefeng.com/wiki/896043488029600/900004111093344)完全一样。解决后，提交，再push：

```js
$ git add env.txt

$ git commit -m "fix env conflict"
[dev 399c89f] fix env conflict

$ git push origin dev
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 12 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (4/4), 431 bytes | 431.00 KiB/s, done.
Total 4 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/magicstf/learngit.git
   5cb158a..399c89f  dev -> dev
```

因此，多人协作的工作模式通常是这样：

1. 首先，可以试图用`git push origin <branch-name>`推送自己的修改；
2. 如果推送失败，则因为远程分支比你的本地更新，需要先用`git pull`试图合并；
3. 如果合并有冲突，则解决冲突，并在本地提交；
4. 没有冲突或者解决掉冲突后，再用`git push origin <branch-name>`推送就能成功！

如果`git pull`提示`no tracking information`，则说明本地分支和远程分支的链接关系没有创建，用命令`git branch --set-upstream-to <branch-name> origin/<branch-name>`。

这就是多人协作的工作模式，一旦熟悉了，就非常简单。

### 标签管理

发布一个版本时，我们通常先在版本库中打一个标签（tag），这样，就唯一确定了打标签时刻的版本。将来无论什么时候，取某个标签的版本，就是把那个打标签的时刻的历史版本取出来。所以，标签也是版本库的一个快照。

Git的标签虽然是版本库的快照，但其实它就是指向某个commit的指针（跟分支很像对不对？但是分支可以移动，标签不能移动），创建和删除标签都是瞬间完成的。

Git有commit，为什么还要引入tag？

“请把上周一的那个版本打包发布，commit号是6a5819e...”

“一串乱七八糟的数字不好找！”

如果换一个办法：

“请把上周一的那个版本打包发布，版本号是v1.2”

“好的，按照tag v1.2查找commit就行！”

所以，tag就是一个让人容易记住的有意义的名字，它跟某个commit绑在一起。

#### 创建标签

在Git中打标签非常简单，首先，切换到需要打标签的分支上：

```js
$ git branch
* dev
  master

$ git checkout master
Switched to branch 'master'
Your branch is up to date with 'origin/master'.
```

然后，敲命令`git tag <name>`就可以打一个新标签：

```js
$ git tag v1.0
```

可以用命令`git tag`查看所有标签：

```js
v$ git tag
v1.0
```

默认标签是打在最新提交的commit上的。有时候，如果忘了打标签，比如，现在已经是周五了，但应该在周一打的标签没有打，怎么办？

方法是找到历史提交的commit id，然后打上就可以了：

```js
$ git log --pretty=oneline --abbrev-commit
69c2536 (HEAD -> master, tag: v1.0, origin/master) merged bug fix 101
e4224c0 fix bug 101
ba2c977 merge with no-ff
d695fb3 add merge
c8a6cd4 conflict fixed
5357755 & simple
c26dbed  and simple
ff78c00 branch test
09dc11f remove test.txt
51c785f add test.txt
8798b94 git tracks changes
14a390e understand how stage works
8206148 append GPL
9e390c2 add distributed
2752175 wrote a readme file
```

比方说要对`add merge`这次提交打标签，它对应的commit id是`d695fb3`，敲入命令：

```js
$ git tag v0.9 d695fb3
```

再用命令`git tag`查看标签：

```js
$ git tag
v0.9
v1.0
```

注意，标签不是按时间顺序列出，而是按字母排序的。可以用`git show <tagname>`查看标签信息：

```js
$ git show v0.9
commit d695fb39afbefcc195e6740c18a0b8937b368316 (tag: v0.9)
Author: magicstf <736643403@qq.com>
Date:   Mon Jun 24 15:49:06 2019 +0800

    add merge

diff --git a/readme.txt b/readme.txt
index a7d1cda..d61fde4 100644
--- a/readme.txt
+++ b/readme.txt
@@ -3,3 +3,4 @@ git is free software distributed under the GPL.
 git has a mutable index called stage.
 git tracks changes.
 creating a new branch is quick and simple.
+current is dev
```

可以看到，`v0.9`确实打在`add merge`这次提交上。

还可以创建带有说明的标签，用`-a`指定标签名，`-m`指定说明文字：

```js
$ git tag -a v0.1 -m "version 0.1 released" 2752175
```

用命令`git show <tagname>`可以看到说明文字：

```js
$ git show v0.1
tag v0.1
Tagger: magicstf <736643403@qq.com>
Date:   Mon Jun 24 23:59:31 2019 +0800

version 0.1 released

commit 275217593432e1b3b6fef0b464f487a67efbfcf1 (tag: v0.1)
Author: magicstf <736643403@qq.com>
Date:   Mon Jun 24 09:19:54 2019 +0800

    wrote a readme file

diff --git a/readme.txt b/readme.txt
new file mode 100644
index 0000000..87218be
--- /dev/null
+++ b/readme.txt
@@ -0,0 +1,3 @@
+git is a version control system.
+git is free software
+
```

#### 操作标签

如果标签打错了，也可以删除：

```js
$ git tag -d v0.1
Deleted tag 'v0.1' (was 4a40270)
```

因为创建的标签都只存储在本地，不会自动推送到远程。所以，打错的标签可以在本地安全删除。

如果要推送某个标签到远程，使用命令`git push origin <tagname>`：

```js
$ git push origin v1.0
Total 0 (delta 0), reused 0 (delta 0)
To https://github.com/magicstf/learngit.git
 * [new tag]         v1.0 -> v1.0
```

或者，一次性推送全部尚未推送到远程的本地标签：

```js
$ git push origin --tags
Total 0 (delta 0), reused 0 (delta 0)
To https://github.com/magicstf/learngit.git
 * [new tag]         v0.9 -> v0.9
```

如果标签已经推送到远程，要删除远程标签就麻烦一点，先从本地删除：

```js
$ git tag -d v0.9
Deleted tag 'v0.9' (was d695fb3)
```

然后，从远程删除。删除命令也是push，但是格式如下：

```js
$ git push origin :refs/tags/v0.9
To https://github.com/magicstf/learngit.git
 - [deleted]         v0.9
```

要看看是否真的从远程库删除了标签，可以登陆GitHub查看。

### 忽略特殊文件

如果我们项目中某个文件不想提交到远程仓库，该怎么办？

当然，git已经为大家想好办法了，在Git工作区的根目录下创建一个特殊的`.gitignore`文件，然后把要忽略的文件名填进去，Git就会自动忽略这些文件。

忽略文件的原则是：

1. 忽略操作系统自动生成的文件；
2. 忽略编译生成的中间文件、可执行文件等，也就是如果一个文件是通过另一个文件自动生成的，那自动生成的文件就没必要放进版本库，比如 /node_modules、/dist目录；
3. 忽略你自己的带有敏感信息的配置文件，比如存放口令的配置文件。

做个试验，假设我们现在有个config.js，里面存放的是一些配置敏感信息，不能提交到远程仓库，如何实现？

首先我们新增`.gitignore`文件和config.js,然后我们查看状态如下：

```js
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        .gitignore
        config.js

nothing added to commit but untracked files present (use "git add" to track)
```

提示有俩个未追踪的文件，然后我们在`.gitignore`文件中新增如下代码:

```js
config.js
```

然后在查看状态，状态如下：

```js
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        .gitignore

nothing added to commit but untracked files present (use "git add" to track)
```

看到没？ config.js 没有了，这就是`.gitignore`文件的作用。