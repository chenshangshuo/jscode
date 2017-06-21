
### HTML（HyperText Markup Language）：一种用于创建网页的标准标记语言。
#### HTMLvsXMLvsXHTML
>- HTML：超文本标记语言，语法较为松散的、不严格的web语言
- XML：可扩展标记语言，主要用于储存数据和结构参考
- XTHML：可扩展超文本标记语言，基于XML，作用与HTML类似，但语法更严格参考

小结：HTML中语法不严格主要体现在：没有报错提示，标签不闭合也可以显示页面内容等；XML用于传输数据，允许创造者定义自己的标签和文档结构；XTHML一种更严谨的HTML版本，体现在：标签字母要小写，标签要闭合等。

---
#### HTML语义化
**含义**：选择合适的标签及合理的代码结构，结构划分合理，有利于网络爬虫的搜索和浏览器解析。
从代码的本身就可以判断包含内容的作用，HTML5中新增加的很多标签（如：`<article>、<nav>、<header>、<footer>`等）就是基于这样的设计原则。

---
#### 内容和样式分离的原则
组成网页三部分：结构层（html）、表现层（css）、行为层（js）
原则：先写html，着重html的代码结构和语义化，体现页面内容的结构、内容，后用css进行样式设置。

**分离的优势**
>- 浏览器加载网页页面速度变快。分离原则下，大部分页面代码写在了CSS当中，页面体积容量变得更小。
- 网页修改设计时，效率、省时。根据html标签内ID或class的标记，到CSS里找到相应的ID或class，可以快速替换指定位置的样式，不会破坏页面架构和其他部分的样式。
- 更好地被搜索引擎收录。基于内容与样式分离的原则，html的语义化就是首要考虑的,网页中语义化的标签代码就会更加适合搜索引擎。
- css样式的分离，它可以根据不同的浏览器，达到显示效果的统一。保证网页架构不变形的前提下，放心在不同浏览器渲染显示样式。

#### meta标签
**作用**：<meta> 元素可提供有关页面的元信息（meta-information），比如针对搜索引擎和更新频度的描述和关键词。
两种属性：name属性和http-equiv属性
name属性语法格式是：＜meta name="参数" content="具体的参数值"＞ 
http-equiv属性语法格式是：＜meta http-equiv="参数" content="参数变量值"＞ 
**name属性主要有以下几种参数**
- keywords（告诉搜索引擎你网页的关键字是什么）
>示例：＜meta name ="keywords" content="science,education,culture,politics,ecnomics，relationships, entertaiment, human"＞
- description(告诉搜索引擎你的网站主要内容)
>举例：＜meta name="description" content="This page is about the meaning of science, education,culture."＞
- robots(告诉搜索机器人哪些页面需要索引，哪些页面不需要索引)
>content的参数有all,none,index,noindex,follow,nofollow。默认是all。
举例：＜meta name="robots" content="none"＞
- author(标注网页的作者)
>举例：＜meta name="author" content="root,root@21cn.com"＞

 **http-equiv属性主要有以下几种参数**
- Expires（用于设定网页的到期时间。一旦网页过期，必须到服务器上重新传输）
- Pragma(cache模式)
*禁止浏览器从本地计算机的缓存中访问页面内容*
- Refresh(自动刷新并指向新页面)
- author(标注网页的作者)
---
**文档声明的作用**：声明该文档的类型，是html、xml还是xhtml等，让浏览器按正确的类型去解析该文档。

**严格模式（ Standards 模式）**：用于呈现遵循最新标准的网页

**混乱模式（Quirks 模式）**：用于呈现为传统浏览器而设计的网页，一种比较宽松的向后兼容的模式

**<!doctype html>的作用**：让浏览器进入标准模式，使用HTML5的标准来解析渲染页面

---
**浏览器乱码的原因**：保存的编码格式和浏览器解码格式不一致所致

**解决办法**：保存的编码格式和浏览器解码格式应一致，设置`<meta charset="utf-8">`

---
**常见的浏览器和与之相对应的内核**

浏览器 | 渲染引擎
--- | ---
Chrome | Blink
Firefox | Gecko
 Safari | Webkit
IE | Trident

**常见标签和与之应用的场景**

标签 | 场景
--- | ---
head | 定义文档的头部，描述文档的属性和信息
body | 定义文档的主体
h1 | 标题1
p | 段落
a | 定义超链接
table | 表格
ul | 无序列表
ol | 有序列表
button | 按钮
img |插入图像
