---
title: ETS
date: 2019-9-29 22:45:39
categories:
  - Erlang
tags: 
  - erlang
  - ets
---

### ETS



键值存储，查找时间为常量。



#### 四种不同的类型



- 集合（set)

  相同的key-value元组只能出现一次。

- 包（bag)

  每种key-value元组组合只能出现一次，但是同一个key可以出现多次。

- 重复包(duplicate bag)

  允许重复的元组。

- 有序集合（ordered set)

  相同的key-value元组只能出现一次，但是可以按key的顺序访问各个元组。



> 访问有序集合（ordered set)类型中的元素需要消耗表长度的对数级别的时间（oLog n),访问其余类型的元素只需要消耗常量级别的时间。



#### 表权限



- public

  允许任何进程访问（读写）。

- private

  只有拥有该表的进程才能访问。

- protected

  任何进程都可以读，只有拥有该表的进程才能写入。



#### 其它参数



- {keypos, N}

  创建表的时候可以通过 {keypos, N} 指定键取自那个位置，对存储记录record非常的有用。



- named_table

  如果存在此选项，则以表的名称注册该表，然后在后续的操作使用该表名称而不是表的标识符。要获取指定标的标识符，可以使用 whereis/1。



- {write_concurrency, boolean()}

  默认为false。这种情况下，对表的写入修改的操作获得独占访问，阻塞对同一表的任何并发访问。如果设置为true，则表将优化为并发写访问。

- {read_concurrency, boolean()}

  默认为false。如果设置为true，则该表将优化为并发读访问。

- compressed

  压缩，如果存在此选项，那么将以更紧凑的格式存储表数据，以消耗更少的内存。但是，这会使表操作变慢。特别是需要查找整个对象（如match，select)这种操作，速度会慢很多，关键元素不会被压缩。

  