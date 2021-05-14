# 介绍

## 功能

+ 协调修改
+ 数据备份
+ 版本管理
+ 权限控制
+ 历史记录
+ 分支管理

## 结构

本地库，暂存区，工作区

`git add,git commit`

## git和GitHub

代码托管中心，维护远程库

### 本地库和远程库的交互

团队和跨团队

# 命令操作

## 本地库初始化

`git -init `

会创建一个。git文件夹，存放的是本地库的相关目录和文件

## 设置签名

形式

用户名，地址

用于区分开发人员的身份

+ 项目级别

  `git config user.name 名字`

  `git config user.email 邮件地址`

本地仓库有效，优先

+ 系统用户级别

  `git config --global 。。。。`

登入当前系统用户

## 添加提交操作

`git status` 查看工作区状态

`git add +文件` 将工作区的文件放到缓存区

`git commit ` 将暂存区提交到本地库

## git 版本

`git log` 显示提交历史

`git reflog` 一行显示

head 指针指向提交的版本

## 前进后退

`git reset --hard +索引值` 后退

前进 `git reset --hard +索引` 

^ 只能后退 `git reset --hard HEAD^`

一个就往后退一次

~ 只能后退  `git reset --hard HEAD~n`

表示后退n步

--soft 只在本地库移动指针

--mixed 本地库指针，重置暂存区

--hard 本 地库指针，重置暂存区，重置工作区

## 回复文件

删除文件相当于一次普通的工作区修改

修改后将他可以add commit 到本地库形成一次记录和普通记录一样可以前进后退进行回复文件

## 文件比较

`git diff[HEAD^] 文件名` 

## 分支

并行开发

`git branch -v` 查看已有分支

`git branch 分支名称` 创建分支

`git checkout 分支名称` 切换分支

`git merge 分支名字 ` 再master分支上做合并分支的操作

如果不同分支修改了同一行，者合并时会产生冲突

# github

![屏幕截图 2021-05-13 213420](..\git\屏幕截图 2021-05-13 213420.png)

`git remote add +别名 +远程库地址`给远程库的地址取别名方便操作

`git push 别名 master` 将本地库push上远程库

pull = fetch + merge 表示将远程库抓取下来 然后和master分支合并

`git pull [远程库地址别名] +远程库分支名` 

`git clone 远程库地址` 克隆远程库到本地库，会自动创建本地库和初始化

如果是要push进远程库就需要和库主人在同一个团队

由库主人邀请进入同一个团队就可以一起修改工程

