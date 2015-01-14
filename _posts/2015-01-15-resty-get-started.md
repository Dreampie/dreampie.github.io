---
layout: post
title: Resty 开发指南
description: "秉持不让开发人员多写一行代码的理念，所有设计都是最简洁的，restful，最轻便，最精简，入门低的框架Resty."
tags: [极简,Restful,框架,java,Resty]
image:
  feature: abstract-3.jpg
  credit: dargadgetz
  creditlink: http://www.dargadgetz.com/ios-7-abstract-wallpaper-pack-for-iphone-5-and-ipod-touch-retina/
---

Resty的相关特性，这里就不介绍了，我们直接用Resty+MVVM来开发一个简单的单页应用 [Resty简介](http://resty.dreampie.cn)

推荐使用的开发工具 [IntelliJ IDEA](http://www.jetbrains.com/idea/download/) + [Git](http://www.git-scm.com/downloads) + [Maven](http://maven.apache.org/download.cgi)


* [使用Resty创建一个Restful的服务端api](#server)

* [使用MVVM实现客户端对接服务端的api](#client)

<span id="server"></span>

###设计服务端Api

* Api规范，url中带上api版本号，使用复数名词作为接口，使用httpMethod作为操作标识

 * ```GET /users - 获取 users 列表```
 * ```GET /users/12 - 获取一个单独的 user```
 * ```GET /users/12/bugs/1 - 获取一个单独的 user #12 下的bug #1```
 * ```POST /users - 创建一个新的 user```
 * ```PUT /users/12 - 更新 user #12```
 * ```PATCH /users/12 - 部分更新 user #12```
 * ```DELETE /users/12 - 删除 user #12```

* 首先定义api版本为v1.0，其次根据客户端请求设计接口

* sessions api:
 * ```GET /api/v1.0/sessions 退出```
 * ```POST /api/v1.0/sessions 登录```

* users api:
 * ```GET /api/v1.0/users 获取用户列表```
 * ```POST /api/v1.0/users 注册用户```
 * ```PATCH /api/v1.0/users 更新用户信息```

* bugs api:
 * ```GET /api/v1.0/bugs 获取```
 * ```POST /api/v1.0/bugs 提交一个新的bug```
 * ```PATCH /api/v1.0/bugs 修改一个bug的信息```
 * ```DELETE /api/v1.0/bugs/#id 删除一个bug信息```

###创建一个Restful的服务端程序



<span id="client"></span>



