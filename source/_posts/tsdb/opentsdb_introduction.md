---
title: 时序数据&时序数据库
subtitle: ''
author: Airren
catalog: true
header-img: ''
tags:
  - TSDB
  - OpenTSDB
p: tsdb/opentsdb_introduction
date: 2020-08-06 00:24:42、
---

> 什么是时序数据？
>
> 时序数据的应用场景和特征？
>
> 时序数据库？

## 时序数据

时序数据，就是与时间强相关度的一系列数据。关注的是某一时刻的数据值，而不是最终的数据。是一个过程而不是一个结果。时序数据描述的是一个数据（指标）在时间维度上的变化。例如： 股票K线、环境监测。

时序数据的特征：

- 数据以一定的时间间隔产生，生产速率稳定。
- 写入多，查询少
- 时序数据不允许更新
- 时序数据主要是按时间范围查询

## 时序数据库

传统的数据库并不适合存储时序数据，针对时序数据的特征，时序数据库的基本要求如下：

- 支持高并发、高吞吐量的写入
- 支持海量数据存储
- 高可用（时序数据在互联网公司常用作报警数据源）
- 支持复杂的多维度的查询
- 易于横向扩展

[常见的时序数据库](https://db-engines.com/en/ranking/time+series+dbms) 

![image-20200806004226361](/Users/airren/Desktop/ByteGopher/airren_blog/source/_posts/tsdb/opentsdb_introduction/image-20200806004226361.png)

