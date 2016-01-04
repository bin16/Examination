#妈妈再也不用担心我的期末考试计划

> 此计划用于解决期末备考阶段考点, 历年考试资源等资料共享问题.


目前本书支持科目列表:

+ 生物特征识别 / 指纹识别
+ 数据与计算机通信 / 计网


##众人拾柴火焰高 计划
> 加入妈妈计划开发，各种资源的收集整理非常耗时耗力, Arco同学一个人确实是搞不过来. 所以如果你觉得妈妈计划不错，想帮助妈妈计划做的更好，恳请您加入*众人拾柴火焰高*计划。
> 
> [Github链接](https://github.com/rebornzeroj/Examination)

###搭建本地环境

[具体查看这里](https://github.com/GitbookIO/gitbook)

需要本地环境: `npm` `gitbook`

安装npm: [点这里](https://github.com/npm/npm)

安装gitbook: `$ npm install gitbook-cli -g ` 

clone到本地后执行: `$ gitbook serve`

本地启动的httpServer默认为 [http://localhost:4000](http://localhost:4000)

那么本地环境就搭建好了, 在浏览器中可以进行预览.

###开发说明

改动的话, 直接改动相应的Markdown文件即可  

新建科目需要在目录中新建一个以.md结尾的文件, 在SUMMARY中加入你新建的科目. 

###举个例子🌰
我们要新建一个 `数据库` 的科目

在目录下创建 Database.md 文件。

在Summary.md中添加 `* [Database](Database.md)`