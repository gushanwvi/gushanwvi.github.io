---
layout:     post
title:      Operating System Notes
subtitle:   Class Notes of Operating System
date:       2020-03-12
author:     Eric
header-img: post-bg-ios9-web.jpg
catalog: true
tags:
    - Class Notes
    - Notes
---





* 系统 向下提供管理(管理资源 硬件资源加软件资源) 向上提供服务

* 操作系统是资源分配器 是控制程序 是内核程序

* ![image-20200303085534147](http://q7266277k.bkt.clouddn.com/image-20200303085534147.jpg)

* 批处理 简单批处理 -> 多道程序批处理程序
  
  * 多道程序批处理程序 提高了资源利用率 但是缺少人机交互性  solution: Time-Sharing System
  
* 分时系统的并发 如 qq 微信同时运行

* 分时发展方向: 分布 分时 并行

* ![image-20200303093207334](http://q7266277k.bkt.clouddn.com/image-20200303093207334.jpg)

* DMA 中断两次 开始传 和 传结束 中间CPU不参与

* 字符设备 适合 中断 块设备 适合 DMA

* 内存保护：基址寄存器 界限寄存器 

* 进程内部是一条指令接一条指令顺序执行; 进程之间是并发执行。

* 线程是进程内部的并发。

* 并发体现在各个进程竞争一个CPU

* 一个进程处于运行状态; 一队进程处于就绪状态

* ![](http://q7266277k.bkt.clouddn.com/20200317084224.png)

* ![](http://q7266277k.bkt.clouddn.com/20200317085630.png)

  ①进程调度

  ②时间片完

  ③发生了I/O请求或等待某件事发生
  ④进程等待的事件发生，进入就绪队列

  新进程创建处于就绪态

* PCB表大小决定了最多可同时存在的进程个数，称为系统的并发度

* ![](http://q7266277k.bkt.clouddn.com/20200324081245.png)

* ![](http://q7266277k.bkt.clouddn.com/20200324081316.png)

* 剥夺方式 : 时间片原则  优先级原则

* 进程创建
  ![](http://q7266277k.bkt.clouddn.com/20200324083111.png)

* 进程间联系 - 间接作用(由第三方引起) - 互斥 : 资源的互斥 排他 

* 进程 两个基本特性: 资源分配的独立单位  调度的基本单位

* 将进程资源分配和调度分开，引入线程

* ![](http://q7266277k.bkt.clouddn.com/20200326091114.png)

* 

