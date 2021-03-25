
---
title: "springboot启动失败常见问题"
date: 2021-03-24T19:36:38+08:00
draft: true
---

<!-- - 刚开始使用springboot连接mysql数据库，项目启动的时候报了一个错误 -->

```bash
Loading class `com.mysql.jdbc.Driver'. This is deprecated. The new driver class is `com.mysql.cj.jdbc.Driver'. The driver is automatically registered via the SPI and manual loading of the driver class is generally unnecessary.
```
原因：现在很多定的教学视频都比较老，教学使用的mysql版本和你自己本地使用的版本不一致，新版本的mysql需要设置成  “com.mysql.cj.jdbc.Driver”，另外还需要增加一个参数 serverTimezone=UTC
参考文档：https://blog.csdn.net/weixin_43770545/article/details/90486809

- 项目启动的时候报错，很显然数据库没有正常连接
```bash
java.sql.SQLException: Access denied for user ''@'localhost' (using password: NO)
```
我当时写的配置是，写的时候IDEA直接提示选了一个，单词没选对data-username 和 data-password，实际应该使用 username 和 password，主要还是没有记清楚配置。当作是一个教训吧。
错误的配置：
```yaml
spring:
  datasource:
    driver-class-name: com.mysql.cj.jdbc.Driver
    url: jdbc:mysql://localhost:3306/blog?useUnicode=true&charseterEncoding=utf-8&serverTimezone=UTC
    data-username: root
    data-password: root
```
正确的配置
```yaml
spring:
  datasource:
    driver-class-name: com.mysql.cj.jdbc.Driver
    url: jdbc:mysql://localhost:3306/blog?useUnicode=true&charseterEncoding=utf-8&serverTimezone=UTC
    username: root
    password: root
    
```