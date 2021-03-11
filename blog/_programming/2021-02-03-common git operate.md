---
title: 经常用到的 Git 命令
summary: Git 的一些常见命令使用与记录
date: 2021-02-03
author: Wooden Kite
location: HuaiNan.AnHui
---

## 分区概念简述

```sh
  （ 写代码 ）           （ 文件池 ）        （ git log 查看 ）    （ github 等平台 ）
Working Directory        Stage             Commit History          Remote
    工作区   ==========>  暂存区   ==========>   版本库   ==========> 远程仓库

            git add              git commit             git push
```

## 基本操作

```sh
# 初始化，使项目使用版本控制
~/project :  git init
# Initialized empty Git repository in /github/ii/xxx/xxx/.git/

# 关联远程仓库
~/project [master ±] : git remote add origin git@github.com:kite/test.git

# 在工作区新建两个文件
~/project [master ±] : touch index.js utils.js

# 查看仓库状态（修改情况）
~/project [master ±] : git status

# 添加需要添加的文件到暂存区
~/project [master ±] : git add -A # 添加所有修改的文件
~/project [master ±] : git add * # 添加所有修改的文件
~/project [master ±] : git add . # 添加所有修改的文件
~/project [master ±] : git add utils.js # 添加指定的文件到暂存区

# 将文件从 暂存区 中移除
~/project [master ±] : git reset HEAD -- utils.js # 将之前添加的暂存区的文件 utils 移除暂存区
~/project [master ±] : git reset HEAD -- # 将 暂存区 中的所有文件移除

# 提交修改的代码
~/project [master ±] : git commit -m 'feat: add utils file.'

[master (root-commit) 6769de1] feat: add utils file.
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 utils.js

# 查看提交日志
~/project [master ±] : git log --graph

# 与远程分支建立连接，并推送代码到远程仓库（之后推送代码使用 git push 即可）
~/project [master ±] : git push --set-upstream origin master

# 下次开发前，拉取远程代码，使本地代码与远程保持一致（保持拉代码的习惯😯）
~/project [master ±] : git pull
```

## Git 配置

### 本地项目配置

```sh
# 查看本地项目 git 仓库的配置列表
~/project [master ±] : git config --local -l

# 添加一些配置
~/project [master ±] : git config --local  user.name "kite_special"

# 或者更直接点： 编辑本地 git 仓库的配置文件 添加一些 “常用配置”
~/project [master ±] : vi .git/config

[core]
        ...

[remote "origin"]
        ...

[branch "master"]
        ...

[user]
        name = kite_special
        email = kite.special@gmail.com
```

### 全局配置

```sh
# 查看全局配置
~/project [master ±] : git config --global -l

# 添加一些全局配置
~/project [master ±] : git config --local  user.name "kite"

# 或直接编辑 ~/.gitconfig (👇 下面配置一些常用配置 👇)
~/project [master ±] : vi ~/.gitconfig

[core]
        editor = vim
[user]
        name = kite
        email = hnx.lemon@gmail.com

[alias]
        a = add .
        s = status
        l = log --graph
        ct = commit -m
```

## 多人开发

```sh
####################################################################
##    多个人开发同一个项目，最终将修改的代码 合并 到同一个主分支 master     ##
####################################################################

****************
*   基本操作     *
****************

# 在开发新功能前，首先拉代码，保持本地和远程仓库代码同步
~/project [master ±] : git pull

# 创建一个自己的开发分支 (从当前最新的节点开始) 并切过去
~/project [master ±] : git checkout -b kite_dev
Switched to a new branch 'kite_dev'

------------------------------------------------------------------------------------
# 或者 从某一次提交开始创建新的分支（若需要的话）
~/project [master ±] : git log --graph # 查看提交历史，选取所需开始的 commit ID
~/project [master ±] : git checkout 45b904 -b kite_dev
------------------------------------------------------------------------------------

# 同步本地分支到远程仓库
~/project [kite_dev ±] : git push origin kite_dev:kite_dev
# 建立与上游分支的联系
~/project [kite_dev ±] : git push --set-upstream origin kite_dev

# balala 开始开发一个功能模块，过程中可能在本地提交了多次小的改动，比如这样
~/project [kite_dev ±] : git ct 'feat: 完成功能模块 -- 子功能1'
~/project [kite_dev ±] : git ct 'feat: 完成功能模块 -- 子功能2'
~/project [kite_dev ±] : git ct 'feat: 完成功能模块 -- 子功能3'
~/project [kite_dev ±] : git ct 'feat: 完成功能模块 -- 子功能4'
~/project [kite_dev ±] : git ct 'feat: 完成功能模块全部完成'

# 终于，完成了功能模块的开发，开始提交代码到远程仓库
# 老规矩，在提交代码前先拉代码（保证本地与远程同步）

# 先切回本地分支 master 分支 并 拉取远程最新的代码 (可能没有最新)
~/project [kite_dev ±] : git checkout master
~/project [master ±] : git pull

--------------------------------------------------------------------------------
# 如果有更新，拉下来可能会有冲突，如果有冲突，解决冲突（有些时候你可能需要询问修改者，如何合并）
# 若有冲突，解决流程如下 👇
~/project [master ±] : git add . # 解决完冲突后，将存在的文件变更添加到暂存区
~/project [master ±] : git ct 'fix xxx conflict'
--------------------------------------------------------------------------------

# 将主分支 master 上的内容合并到 kite_dev 分支上
# 首先，切换回 kite_dev 分支
~/project [master ±] :git checkout kite_dev

~/project [kite_dev ±] :git merge master

--------------------------------------------------------------------------------
# 合并可能会有冲突，如果有冲突，解决冲突解决流程如下 👇
~/project [kite_dev ±] : git add . # 解决完冲突后，将存在的文件变更添加到暂存区
~/project [kite_dev ±] : git ct 'Merge master to kite_dev'
--------------------------------------------------------------------------------

# 保持同步之后，将 kite_dev 分支上开发的功能（提交了多次 commit）合并到远程 master 分支
# 合并之前，由于之前提交了很多零散的 commit，但实际上这部分代码提交，只是某个功能模块，
# 为了保证提交日志历史干净，我们将 kite_dev 分支的 commit 进行合并
# 如这里是：将 “feat: 完成功能模块 -- 子功能1、子功能2、子功能3、子功能4、全部完成 ”
#         合并为一条日志信息 “xxx功能模块开发完成”
# 合并多条 commit
~/project [kite_dev ±] : git rebase -i

--------------------------------------------------------------------------------
# 将 pick -> s
# 若有冲突，解决冲突，然后添加到暂存区
--------------------------------------------------------------------------------

~/project [kite_dev ±] : git rebase --continue

# 取消 rebase
~/project [kite_dev ±] :git rebase --abort

# 合并操作
~/project [kite_dev ±] : git checkout master

~/project [master ±]: git merge kite

~/project [master ±]: git status

On branch master
Your branch is ahead of 'origin/master' by 6 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

~/project [master ±]: git push
```

## 参考

- [猴子老師 git tutorial](https://backlog.com/git-tutorial/tw/intro/intro1_1.html)
- [git tutorial](https://zlargon.gitbooks.io/git-tutorial/content/)
<!-- - [使用 git rebase 合并多次 commit](https://juejin.cn/post/6844903600976576519) -->
