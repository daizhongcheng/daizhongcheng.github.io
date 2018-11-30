---
title: github
comments: true
mathjax: true
date: 2018-11-17 14:51:58
long:
tags:
categories: python
---
### 知识点
- ssh 公私钥的使用
- Github 的基本使用
- Git 工具基本使用
### ssh-keygen
生成密钥
adress: .ssh
在这个文里面有id-rsa和id-rsa.pub,打id_rsa.pub,复制内容到github.
### 安装git 工具
sudo apt-get install git -y
配置用户名与邮箱
git config --global user.name "用户名“
git config --global user.email "邮箱“
git clone 地址
push [-u] origin <分支名>
u是绑定你这一次的仓库名
以后不用再从新输入
首先我们可以通过 git fetch 命令查看有哪一些新改动，用法是在仓库目录下敲入 git fetch origin
确认好更新的内容后，下一步就是把更新给同步到本地仓库中了，通过 git pull 命令来实现，具体用法是 git pull origin <分支名>，分支名默认是 master，再查看一下目录，可以看到已经同步好了 
