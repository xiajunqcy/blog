# 零基础前端成长攻略「一」

从邻近毕业时决定转行前端，经过快整整一年，到现在，独自负责一个项目。希望借由此文记录此间经历。一来，整理自己的到目前为止的成果和思路，二来也许能给后来的同学一些参考吧。（三来也推销一下自己）

## 背景

2016年，我大五，按照我校建筑学院传统，大五上学期有半年时间给同学们，用来实习或者全力准备考研。我按照自己的兴趣所在，选择了北京一家擅长建筑参数化的工作室。

开始实习，我发现，参数化设计过程中，我对写代码的热情，远高于我对建筑设计的热情。其实大概一年前，我就有了转行的想法，但一直没有下定决心以及付诸行动。直到实习了，我终于发现，干活的时候没有热情，确实是一件很痛苦的事。所以实习完，回到学校，我就毅然决然准备转行了。

## 1 准备

在我一年前就有了想法且关注了许多行业的基础上，结合建筑学专业带给我的审美能力与设计水准，加上建筑参数化的实践，我其实有一些编程功底，我决定转向**前端**这个比较能结合这两方面能力，同时也比较火热的行业。

开始是最困难的，没有任何方向，也没有这方面的好友。一切都得自己摸索，在知乎上看了大量相关讨论，觉定先入门相对简单的 HTML 和 CSS ，用的国外的免费教程（顺便复习英语，准备大学最后一次6级考试）[30 Days to Learn HTML & CSS](https://webdesign.tutsplus.com/courses/30-days-to-learn-html-css/lessons/anchors)

实习、备考英语、自学，学完整个课程的时候，大五上学期已经完了。回家过寒假，开始准备着手 JavaScript ，这时候体验到了自学的最大困难，不知道哪个教程比较好。而且 js 涉及的东西远多于 HTML&CSS，感觉学了几天找不到重点。

最后决定报培训班（很感谢我当时参加的培训班，防止广告嫌疑就不说哪个了），看着课程目录终于觉得有了一点大概方向，但是大五下还得做毕业设。并且还拿了两个建筑的 offer，拿 offer 现在看来唯一作用就是让我可以安慰自己，就算最后转行失败了，也能轻松回去干本行养活自己吧，不过也消磨了一些转行的意志。

理论上说已经决定转行了，应该水掉毕设的，大概还是想给自己的专业一个交代吧，做的还比较认真，导致学前端的时间被无限压缩，直到临近毕业，才差不多学到我自认为可以开始找工作的水平。

**复盘**：刚开始学以及学到难点的时候其实会很慌，看着智联上职位热度，前端一直排第一，就容易怀疑自己，怎么才能从这么多转行的人里脱颖而出。比较晚的时候才开始行动，导致错过了春招和秋招，这是一个比较大的遗憾。毕设做得太认真了，其实水过就行，应该多花一点时间在前端上。

## 2 开始

毕业之后在家准备了一个月，就来到了北京，一是前端行业北京算是机会最多的，二是女朋友也在北京。

当时大概粗略的学了 HTML, CSS, JavaScript, jQuery, gulp, webPack, npm

本来想至少入门三大框架中的一个再投简历，结果刚好有熟人介绍说公司 A 缺人，我想着虽然没准备好，去体验一下面试也行。

我整理了自己当时几个作品，做了一个类似作品集的静态页，就过去了。笔试面试都特别简单，我是不喜欢伪造简历，所以直说我了是自学加培训出来的，没有工作经历。负责人觉得我基础还不错，给我发了一个 5K 的offer

第一反应肯定是觉得太低了，不过我问了一下工作时间是965，加上闭门学习这么久了，也挺迫切想体验一下实际工作的状态， 就决定先去工作三个月当做实习看看。

毕业时候大概就有了心理准备，第一年就当学习了，学东西比工资更重要。

## 3 入行

公司是个比较大的外包公司，我去的小组属于于在 B 公司驻场办公。项目组包括几个后端，我和带我的师父（后文简称**同事X**）一共两个前端，项目为 B 公司微信端的一个微店。

因为自学时候一直接触的 pc 端，所以刚开始听到自己要去做微店时候还挺失望，听起来就觉得有点 low 的感觉。不过后来完全体会到了手机端的好处，相对 pc 端，兼容方面的问题会比较少，样式和逻辑比较简单，有更多的时间深入前端工程化的一些东西。

项目是前后端分离的，后台 java，前台技术栈主要是 jQuery，gulp，webpack（后期用 vue 部分重构），还有一个很小型的 html 模板语言，版本控制用的 svn。开始的一周，基本是让我配置环境，熟悉项目代码。期间分了一些活动页给我，算是我工作的第一个活吧。

### 3.1 活动页

活动页大致分为两种类型，一种纯切图，页面上几乎没有 js，最多加上几个按钮，点击时候稍微处理一下附带的参数，一种需要实现各种功能。

纯切图没什么好说的，没有任何技术含量，基本10~20分钟一个。

第二种活动页，最重要的一点是屏幕适配，以下是几个常用的方法

- **媒体查询**  
  在 pc 端，媒体查询能很好的区分不同尺寸规格的屏幕，单纯借助 css ，实现布局和样式的改变。  
  在移动端，尺寸变化几乎不会影响布局，多数情况下只是页面元素的等比缩放。手机尺寸的规格之多，媒体查询显然不适合。

- **view width & view height**  
  1vw = 1/100 屏幕宽度（vh对应高度），如果页面元素都使用 vw 作为单位，可以实现屏幕尺寸改变，页面等比缩放的效果。  
  缺点一是，vw尺寸和设计尺寸需要换算，不够直观，二是在很多活动页，需要切图当做背景，此时背景高度需要手动换算。

为了解决这些痛点，也为了当做练习，我写了一个 js 插件，思路是：

通过等比缩放页面元素，适配不同尺寸的移动端设备

> [插件 AutoRem](https://github.com/xiajunqcy/Qiu-AutoRem)

配合插件，高效的完成了几个复杂的活动页，带我的**同事X**也初步了解我的水平，逐渐开始分配项目中的页面给我。

**复盘**：简单的活一般量相对大，一定不能机械化的完成，要尽可能的抽象成标准流程。写出高复用性的代码。
刚入职的简单活，一定要认真做好，我后期也带新人，最开始安排的几个任务，大致就能看出新人的能力和态度，也决定了后期的任务分配。

### 3.2 功能页

我做的第一个项目相关需求，是写一个合同签署页，功能点涉及到

- 展示合同
- 带出的信息，渲染到合同中
- 手写签名
- ajax 提交

头一次在项目中写页面，和自己写过的练习项目、活动页其实差别不太大，无非是需要引用一些公共样式和脚本。

当然，有几个点虽然了解，但却是头一次在实战中接触

- 文件每次保存都需要 gulp，webpack 处理
- 前后端分离，使用 ajax 处理数据
- 使用版本控制工具「SVN」

这大概是初级前端工作上的两个层面，业务逻辑这一块，展示合同，带出信息都是基本操作。手写签名是个难点，但这只是项目中一个很小的功能点，自己实现所需要的时间和必要性不成正比，所以使用插件是最合适的。

>[插件 signature_pad](https://github.com/szimek/signature_pad)

ajax 提交在这个页面中，也不涉及同步异步的处理，不过签名生成的图片需要传给后台。插件可以生成 base64 格式的图片，可以直接往回传。

业务逻辑方面可以是说完全解决了。

剩下的几点，宽泛说来算前端工程化的问题。由我所处的部门和项目所定，业务逻辑和产品功能几乎没有什么难点，性能优化也比较鸡肋。

所以贴合项目，又能够快速提升自己的部分，无外乎 gulp，webpack。当然，改动、优化什么的都是之后的事，毕竟才是自己写的第一个页面，所以熟悉为主，按照已有配置来。

版本控制方面，之前接触过 git，用来提交、更新代码的话，svn 其实差不多。

开发以及上线，基本没有碰到什么难点，顺利的完成了这个页面。

**复盘**：这是接触项目的第一步，虽然之前预先看过一部分代码。只能说不抱目的的看代码，基本没有什么效率，还是得结合实际需求

### 3.3 VUE

除开我所在的，主要技术栈为 gulp + jQuery 的微店项目组。我们这个前端团队还有两个 vue 框架的项目处于开发中，偶尔也会分页面给我做。

之前提到过，我还没来得及学 vue，就过来实习了。做这些分配的页面，相当于从零开始学一遍 vue。

简单列举一下我的学习路线

- [看官方文档](https://cn.vuejs.org/v2/guide/)
  从头到尾粗看一遍，大概知道 vue 怎么用，有什么功能。完全看不懂的部分就记几个关键词。

- 跟着网上的例子写一个 todos 练习
  实际上断断续续写了一半不到，加上写分配的页面，vue 就基本算入门了

- 从项目入口开始，在整体上学习项目代码
  从 main.js 开始看，路由，vuex，全局变量，插件，项目结构，mock，代理。看完照着现有项目，搭一个相同的框架。（个人认为这一步最重要）

- 再从头到尾看一遍文档

**复盘**：vue （或者 react，angler）现在已经相当于前端基础了，总得会一个。入门之后，用着也比 jQuery 更简单。但更要学会项目的构建，以及任何比单独写页面更深层的东西。