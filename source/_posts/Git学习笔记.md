title: Git学习笔记
date: 2014-12-16 14:35:56
tags:
- Git
- Note
categories:
- Git
---
### Git is a distributed version control system(DVCS).[More](http://git-scm.com/)
## 基本用法 ##

<!--more-->
1. git help/git help xxx

   查看帮助

2. git init

   创建本地仓库，执行完该命令后将会生成.git文件

3. git status

   查看当前文件修改情况

4. git add

   添加修改完成的文件，使其处于stage状态

   * git add file...

   * git add --all 添加所有文件

5. git commit

   提交修改

   * git commit -m "xxxx"

   * git commit -am "xxx" 添加所有并提交

   * git commit --amend -m "xxx" 将新的提交信息添加到上次commit中

6. git log

   查看日志

7. git reset

   * git reset --soft HEAD^ : undo last commit ,put changes into staging

   * git reset --hard HEAD^ : undo last commit and all changes

   * git reset --hard HEAD^^ : undo last 2 commits and all changes

8. git checkout

   * git checkout xxxbranch : switched to branch xxxbranch

   * git checkout xxxfile : 将file恢复到上次commit后的状态

   * git checkout -b xxxbranch : create new branch and switched to new branch

9. git remote

   * git remote add origin URL

   * git remote -v : show remote repositories

   * git remote rm <name> : remove remotes

10. git clone URL [name]

11. git branch

    * git branch : 列出所有分支并指出当前分支

    * git branch xxx : branch created form master

    * git branch -d xxxbranch : delete branch ‘xxxbranch’

    * git checkout -b xxxbranch : switched to a new branch ‘xxxbranch’

12. git push

13. git pull

    相当于是从远程获取最新版本并merge到本地

14. git fetch

    相当于是从远程获取最新版本到本地，不会自动merge

15. git merge

    git merge upstream/master master : 将remote upstream merge到本地master

## Remote branches and tags ##
1. creating a remote branch

   * git checkout -b xxx

   * git push origin xxx

2. git branch -r

   list all remote branches

3. remote show

   git remote show origin

4. removing a branch

   * git push origin : xxxbranch
   * git branch -d xxxbranch
   * git branch -D xxxbranch : 如果此分支还未合并，需要强制删除是使用

5. clean up deleted remote branches

   git remote prune origin

6. git tag

   * git tag:list all tags

   * git checkout xxxtag

   * git tag -a v0.0.3 -m "version 0.0.3"

   * git push --tags : push new tag

## Rebase ##

1. git rebase

   当两个分支各自前进了，即他们之间分叉了，你可以用"pull"命令把"origin"分支上的修改拉下来并且和你的修改合并

## History and Configuration ##

1. git log

   * git log –oneline

   * git log -p

   * git log --oneline --stat

   * git log --oneline --graph

2. git diff

   * git diff --staged : 查看staged文件发生什么变化

   * git diff HEAD : diff between last commit and  current state

   * git diff HEAD~5 : five commits ago

   * git diff branch1 branch2

   * git diff --since=1.week.ago --until=1.minute.ago

3. git config

   * git config --global user.name "xxx"

   * git config --global user.email xxx@xxx

   * git config --global color.ui true

   * git config --list

   * git config alias.newname commandname
