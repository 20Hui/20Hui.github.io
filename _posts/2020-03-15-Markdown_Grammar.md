---
layout: post
title:  "MarkDown文章语法"
date:   2020-03-15 15:15:00 +0800
categories: [markdown]
---
* any list
{:toc}

### Who is  Markdown

　　Markdown 是一种方便记忆、书写的纯文本标记语言，用户可以使用这些标记符号以最小的输入代价生成极富表现力的文档：如您正在阅读的这篇文章。它使用简单的符号标记不同的标题，分割不同的段落，**粗体** 或者 *斜体* 某些文字。    
　　很多产品的文档也是用markdown编写的，并且以“README.MD”的文件名保存在软件的目录下面。               
　　

### 基本语法

标题            
一级标题 :# Header 1            
二级标题 :## Header 2           
三级标题 :### Header 3   
引用链接到标题位置：
[标题1](#title_01)
### <a name="title_01"></a>标题1
```html
[标题1](#title_01)
### <a name="title_01"></a>标题1
```     
链接 :[Title](URL)`[Title](URL)`    
加粗 :**Bold**`**Bold**`        
斜体字 :*Italics* `*Italics*`        
删除线 :~~text~~`~~text~~`          
段落 : 段落之间空一行(回车即可换行)

换行符 : 一行结束时输入两个空格或者使用`<br />` 标签插入简单的换行符             
列表 : 添加星号*或者-加空格成为一个新的列表项。`* 列表01`
* 列表01          
引用 :> 引用内容
> 内容01

内嵌代码 : `alert('Hello World');`  ``符号内添加字符即可有左侧文字效果  
代码高亮(``````符合中间加入代码即可，也可在```后申明代码语言,如：```python)：
```java
echo "hell World"
```
画水平线 (HR) :--------`-------`  
行内修饰文字颜色： <span style="color:red">显示红色</span> `<span style="color:red">显示红色</span>`   
插入图片方式1(不指定图片大小)：`![](/images/posts/markdown/image1.png)`  
插入图片方式2(指定图片大小)：`<img src="/images/posts/codeless/image03.png" height="300" width="500"> `  
插入图片方式3(指定图片大小并居中)：  
```html
<div align="center">
　　<img src="/images/posts/tfimg/wq.jpg" height="320" width="240" />  
</div>
```
引用：-- 引用自`《[引用](https://book.douban.com/subject/3072490/)》`  
《[引用](https://book.douban.com/subject/3072490/)》<br />
css 的大部分语法同样可以在 markdown 上使用，但不同的渲染器渲染出来的 markdown 内容样式也不一样.
###  推荐Markdown编辑器
![](https://raw.githubusercontent.com/20hui/20hui.github.io/master/static/img/_posts/markdown/markdown01.png)
<br />

[Cmd Markdown](https://www.zybuluo.com/cmd/?utm_source=mindstore.io) 作业部落在线 Markdown 编辑器并且有客户端  
![](/images/posts/markdown/image01.png)          
<br>
转载请注明：[20.Cent的博客](https://www.20cent.cn) » [MarkDown文章语法](https://www.20cent.cn/markdown/2020/03/15/Markdown_Grammar.html)                   
