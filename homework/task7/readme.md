#### 问题1 ：id和class的应用场景
1. id：指定标签的唯一标识，每个ID在文档中必须是唯一的
2. class：指定标签的类名，文档中的多个元素可以拥有同一个类名
---
#### 问题2：哪些常见的css选择器
1.基础选择器：*、#id属性值、.class属性值、标签
2.组合选择器：多元素选择器、后代选择器、子元素选择器等
3.属性选择器：如`input[type=text] {width: 100px;}`
4.伪类选择器：用来给选择器添加些效果，如`a:hover {color: red;}`
5.伪元素选择器：如`.wrap::before {content: "aa";}`

---
#### 问题3-1：选择器优先级
1.在属性后面使用!important会覆盖页面内任何位置定义的元素样式
2.作为style属性写在元素标签上的内联样式
3.id选择器
4.class选择器
5.伪类选择器
6.属性选择器
7.标签选择器
8.通配符（*）选择器
9.浏览器自定义

**问题3-2：复杂场景如何计算优先级**
**方法**：对选择器进行权重计算
- 行内样式等于a
- id选择器等于b
- class、伪类及属性选择器等于c
- 标签选择器、伪元素等于d
a>b>c>d，如果上级相等，对比同级值的大小
---
#### 问题4：a:link, a:hover, a:active, a:visited 的顺序是怎样的？ 为什么？
**顺序**：a:link、a:visited 、a:hover、a:active*（“爱恨原则”（LoVe/HAte））*
**原因**：浏览器是按照就近原则来解释的，也就是从下到上。
一个未被访问过的a标签在鼠标经过时同时具有link,hover 两个属性，而如果link标签在后面，那么就仍然显示link的效果，忽略hover。同理，如果hover 在 visisted 前，那么hover仍然会被忽略。

****
#### 问题5

选择器 | 含义
--- | ---
#header | id=header的元素
.header .logo | class=header元素下class=ogo的子元素
.header.mobile | 同时拥有class=header和class=mobile的元素
.header p, .header h3| class=header下p标签的子元素和class=header下h3标签的子元素
#header .nav>li | id=header元素下class=nav的子元素下直接拥有li标签的元素
#header a:hover | id=header元素下满足a:hover属性的子元素
#header .logo~p| id=header元素下class为logo之后的同级p元素
#header input[type="text"] | id=header元素下满足input[type="text"]属性的子元素

#### 问题6:熟知的伪类选择器
- a:link、a:visited、a:active、a:hover	
- a:checked、a:selected
- a:first-child、a:nth-child(n)	
---
#### 问题7
div:first-child、div:first-of-type、div :first-child和div :first-of-type

![first-child.png](http://upload-images.jianshu.io/upload_images/6470442-797d9a4998c25813.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![first-of-type.png](http://upload-images.jianshu.io/upload_images/6470442-72c020023db0d644.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
**div:first-chlid匹配的是div父元素的第一个子元素**，在上图中，第一个子元素为h4标签内的元素，与div标签不符，故样式无显示。
**div:first-of-type匹配的div父元素下第一个标签为div的子元素。**
**div :first-child**：div下的第一个子元素
**div :first-of-type**：div子元素中，相同类型的第一个

---
#### 问题8
- aa颜色为红：class="item1"的第一个子元素
- aa、bb背景为蓝色：class="item1"中相同类型的第一个
