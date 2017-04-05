---
categories:
  - 技术教程
tags:
  - coding.net
  - github
date: 2017-04-04 23:14:25
title: 如何将本地项目与coding.net/github上的项目绑定?
---
# 目录 #

## 在本地生成公钥 ##

输入 ssh-keygen -t rsa -C “username@example.com”,( 注册的邮箱)，不需要密码就按3次回车！

## 在coding.net/github项目设置中添加公钥 ##

本地打开 id_rsa.pub 文件（或执行 $cat id_rsa.pub ），复制其中全部内容，添加到账户 “SSH 公钥” 页面 中，公钥名称可以随意起名字。 
完成后点击 “添加”，然后输入密码或动态码即可添加完成。
<!-- more -->

## 在命令行测试，首次建立链接会要求信任主机 ##

`$ ssh -T git@git.coding.net // 注意 git.coding.net 接入到 CDN 上所以会解析多个不同的 host ip The authenticity of host ‘git.coding.net (61.146.73.68)’ can not be established. RSA key fingerprint is 98:ab:2b:30:60:00:82:86:bb:85:db:87:22:c4:4f:b1. Are you sure you want to continue connecting (yes/no)? yes Warning: Permanently added ‘git.coding.net,61.146.73.68’ (RSA) to the list of kn own hosts.
Enter passphrase for key ‘/c/Users/Yuankai/.ssh/id_rsa’:Coding.net Tips:[HelloKyle_lyk!You have connected to Coding.net by SSH successfully!]`

## 在本地绑定 ##

  `git remote add origin git@git.coding.net:wzw/leave-a-    message.git    
  git add file  
  git commit -m "xxx"  
  git push`   
