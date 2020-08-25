---
title: Git 工作区&暂存区&本地仓库&远程仓库
subtitle: ''
author: Airren
catalog: true
header-img: ''
tags:
  - null
p: git/git_stage_repo
date: 2020-08-26 01:12:13
---



![image-20200826011224617](git_stage_repo/image-20200826011224617.png)

## Git 数据存储的基本概念

WorkSpace: 工作区，编辑修改文件的区域

Index/Stage: 暂存区， 未提交修改

Repository： 本地仓库

Remote： 远程仓库

我们使用编辑器写代码的区域就是WorkSpace, 执行`git add fileName`之后，就将修改的文件提交到了暂存区，执行`git commmit -m "update fineName"` 之后就将修改提交到了本地版本库。最后使用 `git push` 将修改提交到远程仓库。



## Git 常用操作

### 配置用户名以及邮箱

设置

```sh
git config --global user.Name "name"
git config --global user.email "xxx@outlook.com"
```

查看

```sh
git config user.name
git config user.email
```

### 初始化Git仓库 git init

```sh
git init fileName
# or 不指定路径，默认为当前路径
git init
```

![image-20200826014410519](git_stage_repo/image-20200826014410519.png)

**建立空仓库**



切换分支



切换commit



多次commit合并为一个commit



rebase和merge的区别









> 需要解决的问题
>
> 1. git stash 是保存在了哪里
> 2. git reset & git revert
> 3. git rebase
> 4. git init & git init -bare、
> 5. 解决冲突