---
title: PHP服务间调用
date: 2021-04-11 15:58:22
---

### 背景
    
后端业务是使用微服务的，微服务的底层是使用Golang编写的。业务逻辑使用的是PHP编写的，某次开发的时候，PHP某个服务A提供了一个控制器叫做`UnitController`，composer打包之后提供给其他业务B，C，D使用，但是B服务调用A服务`UnitController`中的某个方法的时候，报错`UnitController`不存在。后面排查composer包里面`UnitController`的确是存在的。

### 解决
每种编程语言都有自己的一套保留字，在PHP层面`unit`
