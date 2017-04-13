在电脑上写作，已经是每个人都会做的事情，但大多数无非是用word或者记事本
前者功能齐全，要精通的话甚是复杂，一般写作都用不到大多数功能，显得太过笨重
后者简单到极致，但是由于太简单，写出来的内容没法排版，阅读性极差
所以如果有一个能兼顾易读性与简便的计算机写作方法，就再完美不过了
刚好，MarkDown能满足上述条件，它甚至不是一个软件，只是一种语法，通过极为简便的几个命令，就能够满足日常大多数格式与排版需求

在此，简单的介绍一下它的常用语法
#1. 标题
在文字前面加上不同个数的\#，会生成相应级别的标题
# 一级标题      
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题

    # 一级标题      
    ## 二级标题
    ### 三级标题
    #### 四级标题
    ##### 五级标题

#2 .引用
在文字前加上\>符号
>就会出现简约美观的引用效果
>>并且还可以嵌套

```
    >就会出现简约美观的引用效果
    >>并且还可以嵌套
```

#3. 列表
支持有序列表「内容前输入 数组+.]
1. 内容1
2. 内容2
3. 内容3

```
1. 内容1
2. 内容2
3. 内容3
```

无序列表  「内容前输入 \-+空格]
- 内容1   
- 内容2
- 内容3

```
- 内容1   
- 内容2
- 内容3
```

#4. 分隔线
可以简单的用三个以及以上的星号*，减号-，下划线_来生成如下分隔线
***
```
***
---
___
```
#5. 链接
只需要按照如下格式就能生成超链接
This is [an example](http://example.com/ "Title") inline link.
```
This is [an example](http://example.com/) inline link.
```

#6. 图片
![图片名](http://img0.imgtn.bdimg.com/it/u=2200879002,3430342992&fm=214&gp=0.jpg)

    ![图片名](http://img0.imgtn.bdimg.com/it/u=2200879002,3430342992&fm=214&gp=0.jpg)
#7. 强调
在文字两边加\*号以及\_生成斜体以及粗体效果
*single asterisks*

_single underscores_

**double asterisks**

__double underscores__
```
*single asterisks*

_single underscores_

**double asterisks**

__double underscores__
```

#8. 表格
| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |
```
| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |
```
---
（更多详细用法可参考[Markdown 语法说明](http://wowubuntu.com/markdown/#list)）
