# 机器视觉+机械臂控制开发指南

**Author**：Jerry Peng   &nbsp; &nbsp; &nbsp; **Date**：Dec. 30th, 2021
 <br>
 <br>

 ## 总述

 机器人智能化控制是机器视觉的重点和热点应用方向之一，通过视觉识别、检测实现机器人的自主运行，在智能制造（工业4.0）、无人驾驶、智能安防、智慧农业、智慧康养领域都有着很广泛的应用需求。

 作为本科生毕业设计课题，更多的是通过实验案例开发，掌握开发技能和学习理论基础，因此构思了以下两个实验：
 * 1.基于颜色和形状特征的物体识别与抓取（模拟工业4.0）；
 * 2.基于手势姿态检测的机械臂运动控制（人机交互或远程运动复现概念）两个实验。

为了实现实验内容开发，首先需要掌握基础开发工具的使用和必要的软件编程技能；其次对于视觉理论知识有一定的要求需要学习掌握；鉴于无论工业机器人还是开发类机器人产品都提供有完善的API供二次开发使用，且机器人本体自身的开发技术专业性很高，不建议自行DIY开发，直接使用成熟产品即可。

 <br>
 <br>

 ## 基础学习内容
 为了具备实验开发的基础能力，大致有以下几个方面内容需要学习掌握，分类整理如下：
 
  <br>

 ### 软件开发基础与环境
 此处软件开发基于JavaScript进行，JS开发最显著的优势有三点：1.无需安装配置IDE或编译环境，代码文件可直接通过网页浏览器运行，简单易学且具有良好的跨OS、平台兼容性； 2.JS起初是前端开发语言，UI功能完善；3.近年来基于node.js，在chrome V8内核框架下可以实现性能强大的后端系统开发，且对人工智能方面开发支持完善，执行效率优于Python。`需要注意的是，编程开发的语言及软件都只是一种工具，它与理论知识学习掌握方式过程很不一样，切勿先系统性学习而后再动手开发。具有编程基础的前提下，基础入门后便可开始着手开发，通过实战不断完善学习。`

 | 序号 | 内容 | 简介 | 参考 | 备注 |
 | ------------- |:-------------|:-------------|:-------------| :-------------|
 | 1 | 程序编辑器（推荐VScode） | 是一款当前最主流的程序开发编辑器，支持各种语言和系统，功能强大且易用 | [VScode官网](https://code.visualstudio.com/) | 无需系统学习，很多开发课程都是基于VScode，学习编程时顺带熟悉会用即可 |
 | 2 | HTML/CSS/JS开发入门 | 经典的前端JS开发流程，HTML负责写网页格式，CSS进行网页效果定义，JS实现程序的调度运行 | [概念入门](https://www.cnblogs.com/shiyanlou/p/12304522.html) | 建议很快的入门概念，HTML/CSS能看懂即可，具体熟悉要通过开发过程中不断查询使用来完善。 <br> 当然网上有很多HTML/CSS/JS主题的教程，十几分钟到几十小时不等，大多是针对某一应用领域，不建议花过多深入无关方向； <br> 建议学习时长1~2小时。 |
 | 3 | JS语言基础 | JS语法跟C++/Python有一定差异 | [JS基础语法教程](https://www.bilibili.com/video/BV1P741147CT?from=search&seid=17142994675239237100&spm_id_from=333.337.0.0) | 建议学习时长5小时内，了解基础即可，开发过程中再不断查询深入； <br> 当前JS开发具有很多专业的框架和流程、系统庞大，暂时不用深入，掌握最基本的HTML/CSS/JS开发流程即可。 |
 | 4 | HTML 查询 | 开发过程中不断查询HTML语法、元素及功能 | [W3School](https://www.w3school.com.cn/html/index.asp) | 作为工具书使用即可 |
 | 5 | CSS 查询 | 开发过程中不断查询CSS语法、元素及功能 | [W3School](https://www.w3school.com.cn/css/index.asp) | 作为工具书使用即可 |
 | 5 | JS 查询 | 开发过程中不断查询JS语法、元素及功能 | [W3School](https://www.w3school.com.cn/js/index.asp) | 作为工具书使用即可 |
 <br>

 ### 机器视觉理论实践
 机器视觉的知识体系和开发技能树都非常庞大，学习过程很容易迷失其中，建议围绕以下核心点进行学习，基本入门后再根据自身兴趣扩展。

 | 序号 | 内容 | 简介 | 参考 | 备注 |
 | ------------- |:-------------|:-------------|:-------------| :-------------|
 | 1 | 数字图像处理 | 视觉图像处理基础理论知识 | 《数字图像处理》(冈萨雷斯版) | 学过课程的前提下无需重新看，开发时有不清楚的地方再翻看即可 |
 | 2 | OpenCV(JS版) | 计算机视觉开源库 | [OpenCV官方JS教程](https://docs.opencv.org/3.3.1/d5/d10/tutorial_js_root.html) | 建议系统学习官方案例，了解各类算法函数的使用和特性； <br>网上能找到很多OpenCV书籍，但基本都是官方文档的翻译和改编且多为Python语言，不建议使用。 |


 <br>

 ### 机械臂运动控制
 机械臂可使用7Bot桌面机械臂产品，支持Python/JS/C++多种语言二次开发，学习起来方便快捷。

 | 序号 | 内容 | 简介 | 参考 | 备注 |
 | ------------- |:-------------|:-------------|:-------------| :-------------|
 | 1 | 7Bot机械臂使用 | 机械臂性能、参数、使用开发简介 | 《7Bot桌面机械臂使用说明书》（见附件文档） | 作为了解机械臂特性的文档参阅即可 |
 | 2 | 7Bot JS 开发 | 机械臂开发JS教学案例 | 《7Bot机械臂编程开发指南 （JS版）》（待整理上传） | 目前产品只提供Python教学案例，JS API仅作为内部文档使用，待整理发布 |
 | 3 | 7Bot GUI软件 | Windows版 |  | 百度云盘临时下载地址： 链接:https://pan.baidu.com/s/1lL_LeVtsDFufa0ssx12S3Q  密码:s55c |


 <br>

 ## 实验开发简介
 该部分主要说明实验案例开发过程具体涉及到的技术点和开发解决方案。

 <br>

 ### 实验一：物体识别与抓取
 TBD...

 <br>

 ### 实验二：手势姿态检测与运动复现
 TBD...
