# 第一天

![Git](assets/logo@2x.png)

### 01-为什么学习git

1. 版本管理
2. 多人协作

### 02-git的诞生

1. 2005年诞生

### 03-git是什么

- 分布式管理系统

### 04-什么是版本控制系统

1. 记录版本信息
2. 可以多人协作

### 05-集中式vs分布式

1. 集中式：有中央服务器，一旦断网，不能工作，版本信息都存在中央服务器。
2. 分布式：没有真正意义上的服务器，他的中央服务器只是用来多人交换代码的，离线依然可以工作。

### 06-安装 Git

1. 支持三平台

### 07-Git 的使用方式

1. 命令行模式(建议)
2. 图形界面

### 08-git-bash中常用文件操作命令

```js
cd // 切换目录
pwd // 查看当前目录的具体路径
ls // 查看当前目录下所有文件及文件夹  -a // 查看隐藏目录
mkdir // 创建目录
touch // 创建一个文件
rm // 删除目录或文件 -rf // 删除当前目录下所有文件包括后代文件夹并且不提示
cat // 查看文件内容，适用内容较少文件
less // 查看文件内容，适用内容较多的文件
vi // 编辑文件 
俩种模式
输入i进入插入模式
esc退出插入模式，回到命令模式
:wq // 保存并退出
:q! // 强制退出不保存
```



### 09-git全局配置

```js
git config --global user.name "你的名字"
git config --global user.email "你的邮箱"

// 查看当前git用户名字
git config user.name
```



### 10-创建版本库

```js
git init // 初始化git仓库
git add 文件名 
git commit -m 提示信息 
```



### 11-状态查看

```js
git status // 查看当前文件状态
git diff 文件名 // 查看具体的修改内容
```

### 12-版本回退

```js
git reset --hard HEAD^ //回退上一个版本
git reset --hard commitID // 回退到指定版本

git log // 查看历史版本信息
git reflog  // 控制台关闭过，查看之前的提交信息
```

### 13-工作区和暂存区

- 工作区：就是本机电脑的目录
- 暂存区：存在于版本库，git add  . 会将修改添加到暂存区
- git commit 将暂存区的修改添加到master

### 14-管理修改

- git 管理的是文件修改，而非文件本身

### 15-撤销修改

1. 修改文件以后，还有git add :

   ```js
   git checkout -- 文件名
   ```

2. ​	修改文件后，已经提交到暂存区：

   ```js
   git reset HEAD 文件名
   ```

3. 已经git commit :
   
   1. 没有提交到远程仓库：版本回退

### 16-删除文件

1. 删除文件 rm 文件名

2. git rm 文件名

   注意：如果删除的文件从来没有添加版本库，是无法回复的

### 17-远程仓库

1. gitHub
2. 备份代码
3. 多人协作

### 18-本地Git仓库和GitHub仓库之间的传输协议

1. ssh 

   1. ```js
      $ ssh-keygen -t rsa -C "youremail@example.com" // 创建公钥密钥
      ```

   2. 详细步骤见讲义

### 19-添加远程库

1. 创建远程仓库

2. 将远程仓库和本地仓库进行关联

   ```js
   git remote add origin https://github.com/magicstf/learngit.git
   其中magicstf是你自己github账号的名称
   ```

3. 将本地仓库的内容推送远程仓库

   ```js
   git push -u origin master
   ```

### 20-从远程库克隆

1. 先创建远程仓库

2. ```js
   git clone 远程仓库的地址
   ```

3. 在本地当前文件夹中会出现一个和远程仓库同名的文件夹，

### 21-分支管理

1. 创建分支

   ```jd
   git checkout -b 想要创建的分支名
   git checkout 分支名 // 切换分支
   git branch // 查看分支
   ```

### 22-创建与合并分支

1. 创建分支

   ```js
   git checkout -b "分支名称"
   ```

2. 切换到master分支

   ``` js
   git checkout master
   ```

3. 合并分支

   ```js
   git merge "分支名称"
   ```

### 23-解决冲突

1. 使用vscode解决

2. 删除分支：

   ```js
   git branch -d "分支名称"
   ```

# 第二天

### 01-分支管理策略



### 02-Bug分支

1. 存储当前开发现场：

   ```js
   git stash
   ```

2. bug修复完成，回复现场：

   ```js
   git stash pop // 不仅恢复现场，还能将之前的记录删除
   ```

3. 查看stash 记录：

   ```hs
   git stash list
   ```

   

### 03-Feature分支

1. feature 一般是用来开发新功能使用的

2. 分支未合并就想删除：

   ```js
   git branch -D feature-007
   ```

### 04-推送分支

1. 要查看远程库的信息，用`git remote`：

   ```js
   git remote
   输出 origin
   ```

2. 查看详细信息：

   ```js
   git remote -v
   ```

3. 推送分支:

   ```js
   git push origin master
   ```

### 05-抓取分支

1. 抓取分支：

   ```js
   git pull //抓取分支
   ```

2. 要在`dev`分支上开发，就必须创建远程`origin`的`dev`分支到本地：

   ```js
   git checkout -b dev origin/dev
   ```

### 07-创建标签

1. 创建标签：

   ```js
   git tag 标签名
   ```

2. 创建具体提交的标签：

   ```js
   git tag 标签名 commitID
   ```

3. 查看标签列表：

   ```js
   git tag 
   ```

4. 查看标签具体信息：

   ```js
   git show 标签名
   ```

5. 给标签添加说明：

   ```js
   git tag -a v0.1 -m "version 0.1 released" commitID
   ```

### 08-操作标签

1. 删除标签：

   ```js
   git tag -d 标签名
   ```

2. 远程删除标签：

   ```js
   git push origin :refs/tags/标签名
   ```

3. 推送标签：

   ```js
   git push origin 标签名
   ```

4. 一次性推送多个标签：

   ``` js
   git push origin --tags
   ```

### 09-忽略特殊文件

1. 在项目根目录创建.gitignore 文件
2. 在文件中添加我们想忽略的文件名称或者文件夹的名称
3. 这样使用git status 就查看不到该文件的变动了

### 10-sourceTree基本使用

下载地址：

<https://www.sourcetreeapp.com/>

从远程仓库克隆项目

第一步：

![1561779072872](D:\itcast\Git\forenoon\note\assets\1561779072872.png)



![1561779285709](D:\itcast\Git\forenoon\note\assets\1561779285709.png)

### 00-分支合并

1. git merge 要合并的分支

### 00-创建远程仓库

### 00-将本地仓库推送到远程仓库

1. 初始化： git init 
2. git add .
3. git commit -m "说明"
4. git remote add origin "远程仓库的地址"
5. git push -u origin master